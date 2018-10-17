---
title: 创建邮件项、附加报表并将邮件项发送给用户的经理
TOCTitle: Create a mail item, attach a report, and send the mail item to the user's manager
ms:assetid: 15c26c3b-5e86-4e28-92c5-7389572521da
ms:mtpsurl: https://msdn.microsoft.com/library/Bb644320(v=office.15)
ms:contentKeyID: 55119866
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 5d07424635959fec41c266592da15214eace8b3e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407280"
---
# <a name="create-a-mail-item-attach-a-report-and-send-the-mail-item-to-the-users-manager"></a><span data-ttu-id="602dc-102">创建邮件项、附加报表并将邮件项发送给用户的经理</span><span class="sxs-lookup"><span data-stu-id="602dc-102">Create a mail item, attach a report, and send the mail item to the user's manager</span></span>

<span data-ttu-id="602dc-103">此代码示例先创建有附件的邮件项，再将邮件项发送给用户的经理。</span><span class="sxs-lookup"><span data-stu-id="602dc-103">This example creates a mail item that has an attachment, and then sends the mail item to the user's manager.</span></span>

## <a name="example"></a><span data-ttu-id="602dc-104">示例</span><span class="sxs-lookup"><span data-stu-id="602dc-104">Example</span></span>

<span data-ttu-id="602dc-p101">该示例仅对 Microsoft Exchange Server 帐户正常运行。必须在 Active Directory 目录服务中为用户建立经理关系。该示例使用 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象通过调用 [GetExchangeUserManager](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法确定当前用户的经理。</span><span class="sxs-lookup"><span data-stu-id="602dc-p101">This example runs correctly only against a Microsoft Exchange Server account. A manager relationship for users must be established in the Active Directory directory service. The example uses the [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object to determine the current user's manager by calling the [GetExchangeUserManager](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) method.</span></span>

<span data-ttu-id="602dc-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="602dc-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="602dc-109">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="602dc-109">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="602dc-110">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="602dc-110">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub SendSalesReport()
    Dim mail As Outlook.MailItem = CType(Application.CreateItem( _
        Outlook.OlItemType.olMailItem), Outlook.MailItem)
    mail.Subject = "Quarterly Sales Report FY06 Q4"
    Dim currentUser As Outlook.AddressEntry = _
        Application.Session.CurrentUser.AddressEntry
    If currentUser.Type = "EX" Then
        Dim manager As Outlook.ExchangeUser = _
            currentUser.GetExchangeUser().GetExchangeUserManager()
        ' Add recipient using display name, alias, or smtp address
        mail.Recipients.Add(manager.PrimarySmtpAddress)
        mail.Recipients.ResolveAll()
        mail.Attachments.Add("c:\sales reports\fy06q4.xlsx", _
            Outlook.OlAttachmentType.olByValue)
        mail.Send()
    End If
End Sub
```


```csharp
private void SendSalesReport()
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.Subject = "Quarterly Sales Report FY06 Q4";
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            currentUser.GetExchangeUser().GetExchangeUserManager();
        // Add recipient using display name, alias, or smtp address
        mail.Recipients.Add(manager.PrimarySmtpAddress);
        mail.Recipients.ResolveAll();
        mail.Attachments.Add(@"c:\sales reports\fy06q4.xlsx",
            Outlook.OlAttachmentType.olByValue, Type.Missing,
            Type.Missing);
        mail.Send();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="602dc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="602dc-111">See also</span></span>

- [<span data-ttu-id="602dc-112">邮件</span><span class="sxs-lookup"><span data-stu-id="602dc-112">Mail</span></span>](mail.md)

