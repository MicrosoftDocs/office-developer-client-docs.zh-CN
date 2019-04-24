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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320228"
---
# <a name="get-the-email-address-of-a-recipient"></a><span data-ttu-id="a8c7b-102">获取收件人的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="a8c7b-102">Get the email address of a recipient</span></span>

<span data-ttu-id="a8c7b-103">此代码示例展示了如何获取收件人的简单邮件传输协议 (SMTP) 地址。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-103">This example shows how to get the Simple Mail Transfer Protocol (SMTP) address of a recipient.</span></span>

## <a name="example"></a><span data-ttu-id="a8c7b-104">示例</span><span class="sxs-lookup"><span data-stu-id="a8c7b-104">Example</span></span>

<span data-ttu-id="a8c7b-105">在下面的代码示例中，GetSMTPAddressForRecipients 方法将 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象用作输入参数，然后显示邮件项的每个收件人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-105">In the following the code example, the GetSMTPAddressForRecipients method takes a [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object as an input argument and then displays the SMTP address of each recipient for that mail item.</span></span> <span data-ttu-id="a8c7b-106">此方法先检索表示邮件项的指定收件人集的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-106">The method first retrieves the [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) collection that represents the set of recipients specified for the mail item.</span></span> <span data-ttu-id="a8c7b-107">对于该 [Recipients](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 集合中的每个 **Recipient** ，此方法然后获取与该 [Recipient](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象相对应的 **PropertyAccessor** 对象。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-107">For each [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) in that **Recipients** collection, the method then obtains the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object that corresponds to that **Recipient** object.</span></span> <span data-ttu-id="a8c7b-108">最后, 该方法使用[PropertyAccessor](https://msdn.microsoft.com/library/bb623797\(v=office.15\))属性来获取 MAPI 属性的值, 该属性https://schemas.microsoft.com/mapi/proptag/0x39FE001E映射到收件人的 " **PR\_SMTP\_地址** ([PidTagSmtpAddress](https://msdn.microsoft.com/library/cc842421\(v=office.15\)))" 属性。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-108">Finally, the method uses the [PropertyAccessor](https://msdn.microsoft.com/library/bb623797\(v=office.15\)) property to get the value of the MAPI property https://schemas.microsoft.com/mapi/proptag/0x39FE001E, which maps to the **PR\_SMTP\_ADDRESS** ([PidTagSmtpAddress](https://msdn.microsoft.com/library/cc842421\(v=office.15\))) property of the recipient.</span></span>

<span data-ttu-id="a8c7b-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="a8c7b-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-110">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="a8c7b-111">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a8c7b-111">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a8c7b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8c7b-112">See also</span></span>

- [<span data-ttu-id="a8c7b-113">收件人</span><span class="sxs-lookup"><span data-stu-id="a8c7b-113">Recipients</span></span>](recipients.md)

