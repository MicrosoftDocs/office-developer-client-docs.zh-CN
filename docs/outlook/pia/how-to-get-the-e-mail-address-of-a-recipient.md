---
title: 获取收件人的电子邮件地址
TOCTitle: Get the email address of a recipient
ms:assetid: e585811b-a298-496f-ba79-df7d46526169
ms:mtpsurl: https://docs.microsoft.com/office/client-developer/outlook/pia/how-to-get-the-e-mail-address-of-a-recipient?redirectedfrom=MSDN
ms:contentKeyID: 55119879
ms.date: 12/03/2019
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8957cbc92414b0cdac442167a5c9ea025ce318cb
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819334"
---
# <a name="get-the-email-address-of-a-recipient"></a>获取收件人的电子邮件地址

此代码示例展示了如何获取收件人的简单邮件传输协议 (SMTP) 地址。

## <a name="example"></a>示例

在下面的代码示例中，GetSMTPAddressForRecipients 方法将 [MailItem](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.mailitem?redirectedfrom=MSDN&view=outlook-pia) 对象用作输入参数，然后显示邮件项的每个收件人的 SMTP 地址。 此方法先检索表示邮件项的指定收件人集的 [Recipients](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.recipients?redirectedfrom=MSDN&view=outlook-pia) 集合。 对于该**收件人**集合中的每个[收件人](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.recipient?redirectedfrom=MSDN&view=outlook-pia)，该方法将获取与该**收件人**对象对应的[PropertyAccessor](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.propertyaccessor?redirectedfrom=MSDN&view=outlook-pia)）对象。 最后，该方法使用[PropertyAccessor](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.recipient.propertyaccessor?redirectedfrom=MSDN&view=outlook-pia#Microsoft_Office_Interop_Outlook_Recipient_PropertyAccessor)属性来获取 MAPI 属性的值，该属性https://schemas.microsoft.com/mapi/proptag/0x39FE001E映射到收件人的 " **PR\_SMTP\_地址** （[PidTagSmtpAddress](https://docs.microsoft.com/office/client-developer/outlook/mapi/pidtagsmtpaddress-canonical-property?redirectedfrom=MSDN)）" 属性。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetSMTPAddressForRecipients(Outlook.MailItem mail)
{
    const string PR_SMTP_ADDRESS =
        "http://schemas.microsoft.com/mapi/proptag/0x39FE001E";
    Outlook.Recipients recips = mail.Recipients;
    foreach (Outlook.Recipient recip in recips)
    {
        Outlook.PropertyAccessor pa = recip.PropertyAccessor;
        string smtpAddress =
            pa.GetProperty(PR_SMTP_ADDRESS).ToString();
        Debug.WriteLine(recip.Name + " SMTP=" + smtpAddress);
    }
}
```

## <a name="see-also"></a>另请参阅

- [收件人](recipients.md)

