---
title: 为基于当前文件夹的特定帐户创建可发送项
TOCTitle: Create a sendable item for a specific account based on the current folder
ms:assetid: 665ebdc5-2912-4d85-ac40-835c9ef9a439
ms:contentKeyID: 55119796
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ccbbaab10dc88d50c1fad3c1eefeb5c222bc8446
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349530"
---
# <a name="create-a-sendable-item-for-a-specific-account-based-on-the-current-folder"></a>为基于当前文件夹的特定帐户创建可发送项

此主题包含两个代码示例，用来演示如何创建可发送的电子邮件项和会议请求，然后演示如何使用基于当前文件夹的特定帐户发送它们。

## <a name="example"></a>示例

当使用 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象的 [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) 方法创建 Outlook 项时，系统会为该会话的主帐户创建该项目。 在个人资料定义了多个帐户的会话中，可以为特定 IMAP、POP 或 Exchange 帐户创建项目。 

如果当前配置文件中存在多个帐户且你在用户界面中创建了可发送项目，例如，通过单击“**新建电子邮件**”或“**新建会议**”，检查器会显示撰写模式的新邮件项目或会议请求，那么你便可以选择要用于发送该项目的帐户。 

本主题介绍如何以编程方式创建可发送项目和使用特定发送帐户发送该项目。 该主题有两个代码示例，用来演示如何为由活跃资源管理器中的当前文件夹确定的特定帐户创建 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 和 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\))。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

在第一个方法中，CreateMailItemFromAccount 首先通过将当前文件夹的存储位置（从 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获得）与会话的 [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) 集合中定义的各个帐户的默认送达存储位置（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获得）进行匹配来确定适当的帐户。 然后，CreateMailItemFromAccount 会创建 **MailItem**。 

为了将项目与该帐户关联，CreateMailItemFromAccount 通过将 account.CurrentUser.AddressEntry 属性设置为 **MailItem** 的 [Sender](https://msdn.microsoft.com/library/ff184720\(v=office.15\)) 属性，来将该帐户的用户分配为项目的发送者。 分配 Sender 属性是重要的一步；如果不指定发送者，那么默认情况下将为主帐户创建 **MailItem**。 在该方法结束时，CreateMailItemFromAccount 会显示 **MailItem**。 请注意，如果当前文件夹不在送达存储位置，CreateMailItemFromAccount 将为会话的主帐户创建 **MailItem**。

```csharp
private void CreateMailItemFromAccount()
{
    Outlook.AddressEntry addrEntry = null;
    // Get the Store for CurrentFolder.
    Outlook.Folder folder =
        Application.ActiveExplorer().CurrentFolder 
        as Outlook.Folder;
    Outlook.Store store = folder.Store;
    Outlook.Accounts accounts =
        Application.Session.Accounts;
    // Enumerate accounts to find
    // account.DeliveryStore for store.
    foreach (Outlook.Account account in accounts)
    {
        if (account.DeliveryStore.StoreID == 
            store.StoreID)
        {
            addrEntry =
                account.CurrentUser.AddressEntry;
            break;
        }
    }
    // Create MailItem.
    Outlook.MailItem mail =
        Application.CreateItem(
        Outlook.OlItemType.olMailItem)
        as Outlook.MailItem;
    if (addrEntry != null)
    {
        // Set Sender property.
        mail.Sender = addrEntry;
        mail.Display(false);
    }
}
```

下一个方法 (CreateMeetingRequestFromAccount) 与 CreateMailItemFromAccount 类似，只是它将创建 AppointmentItem 而不是 MailItem。 CreateMeetingRequestFromAccount 首先通过将当前文件夹的存储位置（从 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获得）与会话的 Accounts 集合中定义的各个帐户的默认送达存储位置（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获得）进行匹配来确定适当的帐户。 然后，CreateMeetingRequestFromAccount 会创建 AppointmentItem。 

为了将项目与该帐户关联，CreateMeetingRequestFromAccount 通过将 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象设置为 AppointmentItem 的 [SendUsingAccount](https://msdn.microsoft.com/library/bb610680\(v=office.15\)) 属性，来将该帐户分配为项目的发送帐户。 分配 SendUsingAccount 属性是重要的一步；如果不指定帐户，那么默认情况下将为主帐户创建 AppointmentItem。 在该方法结束时，CreateMeetingRequestFromAccount 会显示 AppointmentItem。 请注意，如果当前文件夹不在送达存储位置，CreateMeetingRequestFromAccount 将为会话的主帐户创建 AppointmentItem。

```csharp
private void CreateMeetingRequestFromAccount()
{
    Outlook.Account acct = null;
    Outlook.Folder folder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.Store store = folder.Store;
    Outlook.Accounts accounts =
        Application.Session.Accounts;
    foreach (Outlook.Account account in accounts)
    {
        if (account.DeliveryStore.StoreID ==
            store.StoreID)
        {
            acct = account;
            break;
        }
    }
    Outlook.AppointmentItem appt =
        Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.MeetingStatus = 
        Outlook.OlMeetingStatus.olMeeting;
    if (acct != null)
    {
        // Set SendUsingAccount property.
        appt.SendUsingAccount=acct;
        appt.Display(false);
    }
}
```

## <a name="see-also"></a>另请参阅

- [帐户](accounts.md)

