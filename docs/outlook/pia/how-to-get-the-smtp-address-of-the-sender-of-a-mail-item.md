---
title: 获取邮件项发件人的 SMTP 地址
TOCTitle: Get the SMTP address of the sender of a mail item
ms:assetid: 86e0c0aa-1696-4415-b25f-f9c1c29d88a9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184624(v=office.15)
ms:contentKeyID: 55119869
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 05d52f24262f08a6326d464a2dc0d57d6d0510d7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542546"
---
# <a name="get-the-smtp-address-of-the-sender-of-a-mail-item"></a>获取邮件项发件人的 SMTP 地址

此代码示例获取邮件项发件人的简单邮件传输协议 (SMTP) 地址。

## <a name="example"></a>示例

若要确定已接收邮件项的 SMTP 地址，请使用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的 [SenderEmailAddress](https://msdn.microsoft.com/library/bb622746\(v=office.15\)) 属性。 不过，如果发件人位于组织内部，**SenderEmailAddress** 不会返回 SMTP 地址。在这种情况下，必须使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象，才能返回发件人的 SMTP 地址。

在下面的代码示例中，GetSenderSMTPAddress 使用 **PropertyAccessor** 对象，获取未直接在 Outlook 对象模型中公开的值。 GetSenderSMTPAddress 需要使用 **MailItem**。 如果已接收 [MailItem](https://msdn.microsoft.com/library/bb624136\(v=office.15\)) 的 **SenderEmailType** 属性值为"EX"，则表示邮件的发件人驻留在您组织内的 Exchange 服务器上。 GetSenderSMTPAddress 使用 **MailItem** 对象的 [Sender](https://msdn.microsoft.com/library/ff184720\(v=office.15\)) 属性，获取由 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象表示的发件人。 如果 **AddressEntry** 对象表示一个 Exchange 用户，则该示例将调用 [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) 方法以返回 [AddressEntry](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象的 **ExchangeUser** 对象。 然后，GetSenderSMTPAddress 使用 **ExchangeUser** 对象的 [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)) 属性，返回发件人的 SMTP 地址。 如果发件人的 **AddressEntry** 对象不表示 **ExchangeUser** 对象，此代码示例使用 **PropertyAccessor** 对象的 [GetProperty(String)](https://msdn.microsoft.com/library/bb645726\(v=office.15\)) 方法来返回发件人的 SMTP 地址，其中参数为 **PR\_SMTP\_ADDRESS** ([PidTagSmtpAddress](https://msdn.microsoft.com/library/cc842421\(v=office.15\)))。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private string GetSenderSMTPAddress(Outlook.MailItem mail)
{
    string PR_SMTP_ADDRESS =
        @"http://schemas.microsoft.com/mapi/proptag/0x39FE001E";
    if (mail == null)
    {
        throw new ArgumentNullException();
    }
    if (mail.SenderEmailType == "EX")
    {
        Outlook.AddressEntry sender =
            mail.Sender;
        if (sender != null)
        {
            //Now we have an AddressEntry representing the Sender
            if (sender.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeUserAddressEntry
                || sender.AddressEntryUserType ==
                Outlook.OlAddressEntryUserType.
                olExchangeRemoteUserAddressEntry)
            {
                //Use the ExchangeUser object PrimarySMTPAddress
                Outlook.ExchangeUser exchUser =
                    sender.GetExchangeUser();
                if (exchUser != null)
                {
                    return exchUser.PrimarySmtpAddress;
                }
                else
                {
                    return null;
                }
            }
            else
            {
                return sender.PropertyAccessor.GetProperty(
                    PR_SMTP_ADDRESS) as string;
            }
        }
        else
        {
            return null;
        }
    }
    else
    {
        return mail.SenderEmailAddress;
    }
}
```

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

