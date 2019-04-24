---
title: 使用 Hotmail 帐户发送邮件项
TOCTitle: Send a mail item by using a Hotmail account
ms:assetid: f25853a7-67c0-46a3-a298-5cdf72ebc53f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184652(v=office.15)
ms:contentKeyID: 55119797
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 008f66ff1a43f90e756900c467ba6c086829b769
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331162"
---
# <a name="send-a-mail-item-by-using-a-hotmail-account"></a>使用 Hotmail 帐户发送邮件项

此代码示例使用 [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) 属性，通过 Windows Live Hotmail 帐户发送邮件项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

配置文件定义一个或多个电子邮件帐户，每个电子邮件帐户都与特定类型的服务器（如 Microsoft Exchange Server 或邮局协议 3 (POP3)）关联。 由于配置文件中可能有多个帐户，因此必须先指定要用来发送项的电子邮件帐户，再获取表示帐户的 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象。

在下面的代码示例中，创建的邮件中附加了行程，然后通过 Windows Live Hotmail 帐户进行发送。 Hotmail 电子邮件帐户用作用户配置文件中的 **Account** 对象。 然后，此代码示例将 SendUsingAccount 属性设置为这个 Account 对象，并调用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象中的 [Send()](https://msdn.microsoft.com/library/bb644139\(v=office.15\)) 方法。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SendUsingAccountExample()
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.Subject = "Our itinerary";
    mail.Attachments.Add(@"c:\travel\itinerary.doc",
        Outlook.OlAttachmentType.olByValue,
        Type.Missing, Type.Missing);
    Outlook.Account account =
        Application.Session.Accounts["Hotmail"];
    mail.SendUsingAccount = account;
    mail.Send();
}
```

## <a name="see-also"></a>另请参阅

- [帐户](accounts.md)

