---
title: 为基于当前文件夹的特定帐户创建可发送项
TOCTitle: Create a sendable item for a specific account based on the current folder
ms:assetid: 665ebdc5-2912-4d85-ac40-835c9ef9a439
ms:contentKeyID: 55119796
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ccbbaab10dc88d50c1fad3c1eefeb5c222bc8446
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702157"
---
# <a name="create-a-sendable-item-for-a-specific-account-based-on-the-current-folder"></a><span data-ttu-id="1447e-102">为基于当前文件夹的特定帐户创建可发送项</span><span class="sxs-lookup"><span data-stu-id="1447e-102">Create a sendable item for a specific account based on the current folder</span></span>

<span data-ttu-id="1447e-103">此主题包含两个代码示例，用来演示如何创建可发送的电子邮件项和会议请求，然后演示如何使用基于当前文件夹的特定帐户发送它们。</span><span class="sxs-lookup"><span data-stu-id="1447e-103">This topic contains two code examples that show how to create a sendable email item and meeting request, and then how to send them by using a specific account that is based on the current folder.</span></span>

## <a name="example"></a><span data-ttu-id="1447e-104">示例</span><span class="sxs-lookup"><span data-stu-id="1447e-104">Example</span></span>

<span data-ttu-id="1447e-105">当使用 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象的 [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) 方法创建 Outlook 项时，系统会为该会话的主帐户创建该项目。</span><span class="sxs-lookup"><span data-stu-id="1447e-105">When you use the [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) method of the [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) object to create an Outlook item, the item is created for the primary account for that session.</span></span> <span data-ttu-id="1447e-106">在个人资料定义了多个帐户的会话中，可以为特定 IMAP、POP 或 Exchange 帐户创建项目。</span><span class="sxs-lookup"><span data-stu-id="1447e-106">In a session where multiple accounts are defined in the profile, you can create an item for a specific IMAP, POP, or Exchange account.</span></span> 

<span data-ttu-id="1447e-107">如果当前配置文件中存在多个帐户且你在用户界面中创建了可发送项目，例如，通过单击“**新建电子邮件**”或“**新建会议**”，检查器会显示撰写模式的新邮件项目或会议请求，那么你便可以选择要用于发送该项目的帐户。</span><span class="sxs-lookup"><span data-stu-id="1447e-107">If there are multiple accounts in the current profile and you create a sendable item in the user interface, for example, by clicking **New Email** or **New Meeting**, an inspector displays a new mail item or meeting request in compose mode, and then you can select the account from which to send the item.</span></span> 

<span data-ttu-id="1447e-108">本主题介绍如何以编程方式创建可发送项目和使用特定发送帐户发送该项目。</span><span class="sxs-lookup"><span data-stu-id="1447e-108">This topic shows how to programmatically create a sendable item and send it by using a specific sending account.</span></span> <span data-ttu-id="1447e-109">该主题有两个代码示例，用来演示如何为由活跃资源管理器中的当前文件夹确定的特定帐户创建 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 和 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="1447e-109">The topic has two code examples that show how to create a [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) and an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) for a specific account that is determined by the current folder in the active explorer.</span></span>

<span data-ttu-id="1447e-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="1447e-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="1447e-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="1447e-111">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="1447e-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="1447e-112">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

<span data-ttu-id="1447e-113">在第一个方法中，CreateMailItemFromAccount 首先通过将当前文件夹的存储位置（从 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获得）与会话的 [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) 集合中定义的各个帐户的默认送达存储位置（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获得）进行匹配来确定适当的帐户。</span><span class="sxs-lookup"><span data-stu-id="1447e-113">In the first method, CreateMailItemFromAccount first identifies the appropriate account by matching the store of the current folder (obtained from the [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) property) with the default delivery store of each account (obtained with the [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) property) that is defined in the [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) collection for the session.</span></span> <span data-ttu-id="1447e-114">然后，CreateMailItemFromAccount 会创建 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="1447e-114">CreateMailItemFromAccount then creates the **MailItem**.</span></span> 

<span data-ttu-id="1447e-115">为了将项目与该帐户关联，CreateMailItemFromAccount 通过将 account.CurrentUser.AddressEntry 属性设置为 **MailItem** 的 [Sender](https://msdn.microsoft.com/library/ff184720\(v=office.15\)) 属性，来将该帐户的用户分配为项目的发送者。</span><span class="sxs-lookup"><span data-stu-id="1447e-115">To associate the item with the account, CreateMailItemFromAccount assigns the user of the account as the sender of the item by setting the account.CurrentUser.AddressEntry property to the [Sender](https://msdn.microsoft.com/library/ff184720\(v=office.15\)) property of the **MailItem**.</span></span> <span data-ttu-id="1447e-116">分配 Sender 属性是重要的一步；如果不指定发送者，那么默认情况下将为主帐户创建 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="1447e-116">Assigning the Sender property is the important step; if you do not specify the sender, the **MailItem** is created for the primary account by default.</span></span> <span data-ttu-id="1447e-117">在该方法结束时，CreateMailItemFromAccount 会显示 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="1447e-117">At the end of the method, CreateMailItemFromAccount displays the **MailItem**.</span></span> <span data-ttu-id="1447e-118">请注意，如果当前文件夹不在送达存储位置，CreateMailItemFromAccount 将为会话的主帐户创建 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="1447e-118">Note that if the current folder is not on a delivery store, CreateMailItemFromAccount creates the **MailItem** for the primary account for the session.</span></span>

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

<span data-ttu-id="1447e-119">下一个方法 (CreateMeetingRequestFromAccount) 与 CreateMailItemFromAccount 类似，只是它将创建 AppointmentItem 而不是 MailItem。</span><span class="sxs-lookup"><span data-stu-id="1447e-119">The next method, CreateMeetingRequestFromAccount, is similar to CreateMailItemFromAccount except that it creates an AppointmentItem instead of a MailItem.</span></span> <span data-ttu-id="1447e-120">CreateMeetingRequestFromAccount 首先通过将当前文件夹的存储位置（从 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获得）与会话的 Accounts 集合中定义的各个帐户的默认送达存储位置（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获得）进行匹配来确定适当的帐户。</span><span class="sxs-lookup"><span data-stu-id="1447e-120">CreateMeetingRequestFromAccount first identifies the appropriate account by matching the store of the current folder (obtained from the [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) property) with the default delivery store of each account (obtained from the [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) property) that is defined in the Accounts collection for the session.</span></span> <span data-ttu-id="1447e-121">然后，CreateMeetingRequestFromAccount 会创建 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="1447e-121">CreateMeetingRequestFromAccount then creates the AppointmentItem.</span></span> 

<span data-ttu-id="1447e-122">为了将项目与该帐户关联，CreateMeetingRequestFromAccount 通过将 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象设置为 AppointmentItem 的 [SendUsingAccount](https://msdn.microsoft.com/library/bb610680\(v=office.15\)) 属性，来将该帐户分配为项目的发送帐户。</span><span class="sxs-lookup"><span data-stu-id="1447e-122">To associate the item with the account, CreateMeetingRequestFromAccount assigns that account as the item's sending account by setting the [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object to the [SendUsingAccount](https://msdn.microsoft.com/library/bb610680\(v=office.15\)) property of the AppointmentItem.</span></span> <span data-ttu-id="1447e-123">分配 SendUsingAccount 属性是重要的一步；如果不指定帐户，那么默认情况下将为主帐户创建 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="1447e-123">Assigning the SendUsingAccount property is the important step; if you do not specify the account, the AppointmentItem is created for the primary account by default.</span></span> <span data-ttu-id="1447e-124">在该方法结束时，CreateMeetingRequestFromAccount 会显示 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="1447e-124">At the end of the method, CreateMeetingRequestFromAccount displays the AppointmentItem.</span></span> <span data-ttu-id="1447e-125">请注意，如果当前文件夹不在送达存储位置，CreateMeetingRequestFromAccount 将为会话的主帐户创建 AppointmentItem。</span><span class="sxs-lookup"><span data-stu-id="1447e-125">Note that if the current folder is not on a delivery store, CreateMeetingRequestFromAccount creates the AppointmentItem for the primary account for the session.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1447e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1447e-126">See also</span></span>

- [<span data-ttu-id="1447e-127">帐户</span><span class="sxs-lookup"><span data-stu-id="1447e-127">Accounts</span></span>](accounts.md)

