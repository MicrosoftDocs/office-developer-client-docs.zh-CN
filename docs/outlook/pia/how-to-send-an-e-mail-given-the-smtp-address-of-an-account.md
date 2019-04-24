---
title: 在帐户 SMTP 地址给定的情况下发送电子邮件
TOCTitle: Send an email given the SMTP address of an account
ms:assetid: 4ff4aaac-54ba-45c7-8b2e-aeba35af1e56
ms:mtpsurl: https://msdn.microsoft.com/library/Ff462095(v=office.15)
ms:contentKeyID: 55119865
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0771941581d0edaab1660790582cfb22bef48dc6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332093"
---
# <a name="send-an-email-given-the-smtp-address-of-an-account"></a>在帐户 SMTP 地址给定的情况下发送电子邮件

本主题介绍了如何创建电子邮件并通过 Microsoft Outlook 帐户发送它，前提是此帐户的简单邮件传输协议 (SMTP) 地址给定。

## <a name="example"></a>示例

> [!NOTE] 
> Helmut Obertanner 提供了下面的代码示例。 Helmut 拥有 Visual Studio Office 开发人员工具和 Outlook 方面的专业知识。 


下面的代码示例包含 Sample 类的 SendEmailFromAccount 和 GetAccountForEmailAddress 方法（作为 Outlook 加载项项目的一部分实现）。 每个项目都添加对基于 [Microsoft.Office.Interop.Outlook](https://msdn.microsoft.com/library/bb610835\(v=office.15\)) 命名空间的 Outlook 主互操作程序集的引用。 SendEmailFromAccount 方法接受作为受信任 [Application](https://msdn.microsoft.com/library/bb646615\(v=office.15\)) 对象的输入参数，以及表示主题、正文、收件人分号分隔列表和电子邮件帐户 SMTP 地址的字符串。 SendEmailFromAccount 创建 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象，并使用给定参数初始化 [To](https://msdn.microsoft.com/library/bb624372\(v=office.15\))、[Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) 和 [Body](https://msdn.microsoft.com/library/bb646600\(v=office.15\)) 属性。 为了查找要从哪个 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象中发送电子邮件，SendEmailFromAccount 调用 GetAccountForEmailAddress 方法，这种方法将给定 SMTP 地址与当前配置文件的每个帐户的 [SmtpAddress](https://msdn.microsoft.com/library/bb623516\(v=office.15\)) 属性进行匹配。 SendEmailFromAccount 收到返回的匹配 **Account** 对象，然后使用此 **Account** 对象初始化 **MailItem** 的 [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) 属性，并发送 **MailItem**。

下面先展示了 Visual Basic 代码示例，后展示了 C\# 代码示例。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Imports Outlook = Microsoft.Office.Interop.Outlook

Namespace OutlookAddIn2
    Class Sample
        
        Shared Sub SendEmailFromAccount(ByVal application As Outlook.Application, _
            ByVal subject As String, ByVal body As String, ByVal recipients As String, ByVal smtpAddress As String)

            ' Create a new MailItem and set the To, Subject, and Body properties.
            Dim newMail As Outlook.MailItem = DirectCast(application.CreateItem(Outlook.OlItemType.olMailItem), Outlook.MailItem)
            newMail.To = recipients
            newMail.Subject = subject
            newMail.Body = body

            ' Retrieve the account that has the specific SMTP address.
            Dim account As Outlook.Account = GetAccountForEmailAddress(application, smtpAddress)
            ' Use this account to send the email.
            newMail.SendUsingAccount = account
            newMail.Send()
        End Sub

        Shared Function GetAccountForEmailAddress(ByVal application As Outlook.Application, ByVal smtpAddress As String) As Outlook.Account

            ' Loop over the Accounts collection of the current Outlook session.
            Dim accounts As Outlook.Accounts = application.Session.Accounts
            Dim account As Outlook.Account
            For Each account In accounts
                ' When the email address matches, return the account.
                If account.SmtpAddress = smtpAddress Then
                    Return account
                End If
            Next
            Throw New System.Exception(String.Format("No Account with SmtpAddress: {0} exists!", smtpAddress))
        End Function

    End Class
End Namespace
```


```csharp
using System;
using System.Text;
using Outlook = Microsoft.Office.Interop.Outlook;

namespace OutlookAddIn1
{
    class Sample
    {
        public static void SendEmailFromAccount(Outlook.Application application, string subject, string body, string to, string smtpAddress)
        {

            // Create a new MailItem and set the To, Subject, and Body properties.
            Outlook.MailItem newMail = (Outlook.MailItem)application.CreateItem(Outlook.OlItemType.olMailItem);
            newMail.To = to;
            newMail.Subject = subject;
            newMail.Body = body;

            // Retrieve the account that has the specific SMTP address.
            Outlook.Account account = GetAccountForEmailAddress(application, smtpAddress);
            // Use this account to send the email.
            newMail.SendUsingAccount = account;
            newMail.Send();
        }


        public static Outlook.Account GetAccountForEmailAddress(Outlook.Application application, string smtpAddress)
        {

            // Loop over the Accounts collection of the current Outlook session.
            Outlook.Accounts accounts = application.Session.Accounts;
            foreach (Outlook.Account account in accounts)
            {
                // When the email address matches, return the account.
                if (account.SmtpAddress == smtpAddress)
                {
                    return account;
                }
            }
            throw new System.Exception(string.Format("No Account with SmtpAddress: {0} exists!", smtpAddress));
        }

    }
}
```

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

