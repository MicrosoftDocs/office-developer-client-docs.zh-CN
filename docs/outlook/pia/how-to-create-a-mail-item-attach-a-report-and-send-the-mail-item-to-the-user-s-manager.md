---
title: 创建邮件项、附加报表并将邮件项发送给用户的经理
TOCTitle: Create a mail item, attach a report, and send the mail item to the user's manager
ms:assetid: 15c26c3b-5e86-4e28-92c5-7389572521da
ms:mtpsurl: https://msdn.microsoft.com/library/Bb644320(v=office.15)
ms:contentKeyID: 55119866
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 32c40e1fbda3f0f851b52d29c073d95a5d636620
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710291"
---
# <a name="create-a-mail-item-attach-a-report-and-send-the-mail-item-to-the-users-manager"></a>创建邮件项、附加报表并将邮件项发送给用户的经理

此代码示例先创建有附件的邮件项，再将邮件项发送给用户的经理。

## <a name="example"></a>示例

该示例仅对 Microsoft Exchange Server 帐户正常运行。必须在 Active Directory 目录服务中为用户建立经理关系。该示例使用 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象通过调用 [GetExchangeUserManager](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法确定当前用户的经理。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

