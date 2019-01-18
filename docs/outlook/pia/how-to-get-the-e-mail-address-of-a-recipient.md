---
title: 获取收件人的电子邮件地址
TOCTitle: Get the email address of a recipient
ms:assetid: e585811b-a298-496f-ba79-df7d46526169
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184647(v=office.15)
ms:contentKeyID: 55119879
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 030908f7202301ec7849e655d5ff7cc1d7cffc13
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28719327"
---
# <a name="get-the-email-address-of-a-recipient"></a>获取收件人的电子邮件地址

此代码示例展示了如何获取收件人的简单邮件传输协议 (SMTP) 地址。

## <a name="example"></a>示例

在下面的代码示例中，GetSMTPAddressForRecipients 方法将 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象用作输入参数，然后显示邮件项的每个收件人的 SMTP 地址。 此方法先检索表示邮件项的指定收件人集的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。 然后，对于 **Recipients** 集合中的每个 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\))，此方法 都会获取与 **Recipient** 对象对应的 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象。 最后，该方法使用[PropertyAccessor](https://msdn.microsoft.com/library/bb623797\(v=office.15\))属性来获取 MAPI 属性的值https://schemas.microsoft.com/mapi/proptag/0x39FE001E，它映射到**PR\_SMTP\_地址** 收件人 ([PidTagSmtpAddress](https://msdn.microsoft.com/library/cc842421\(v=office.15\))) 属性。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetSMTPAddressForRecipients(Outlook.MailItem mail)
{
    const string PR_SMTP_ADDRESS =
        "https://schemas.microsoft.com/mapi/proptag/0x39FE001E";
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

