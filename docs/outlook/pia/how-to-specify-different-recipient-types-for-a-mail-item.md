---
title: 为邮件项指定不同的收件人类型
TOCTitle: Specify different recipient types for a mail item
ms:assetid: 2a3ace9f-627c-4fdd-b182-afc1b53af85b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184598(v=office.15)
ms:contentKeyID: 55119871
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bf61a7fbb470291eae448a93c80866112c41407a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335509"
---
# <a name="specify-different-recipient-types-for-a-mail-item"></a><span data-ttu-id="3dbf5-102">为邮件项指定不同的收件人类型</span><span class="sxs-lookup"><span data-stu-id="3dbf5-102">Specify different recipient types for a mail item</span></span>

<span data-ttu-id="3dbf5-103">此代码示例展示了如何以编程方式为邮件项设置不同的收件人类型（To、Cc 或 Bcc）。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-103">This example shows how to programmatically set different recipient types (To, Cc, or Bcc) for a mail item.</span></span>

## <a name="example"></a><span data-ttu-id="3dbf5-104">示例</span><span class="sxs-lookup"><span data-stu-id="3dbf5-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3dbf5-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="3dbf5-106">下面的代码示例展示了如何指定 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的收件人类型是 To、Cc 还是 Bcc。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-106">The following code example illustrates how to specify whether a recipient of a [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object is a To, Cc, or Bcc recipient.</span></span> <span data-ttu-id="3dbf5-107">SetRecipientTypeForMail 先创建 **MailItem** 对象，并向 **MailItem** 的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合添加三个 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象，再将每个 **Recipient** 对象的 [Type](https://msdn.microsoft.com/library/bb611841\(v=office.15\)) 属性设置为 [OlMailRecipientType](https://msdn.microsoft.com/library/bb647641\(v=office.15\)) 枚举中的值。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-107">SetRecipientTypeForMail creates a **MailItem** object, adds three [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) objects to the [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) collection of the **MailItem**, and then sets the [Type](https://msdn.microsoft.com/library/bb611841\(v=office.15\)) property of each **Recipient** object to a value from the [OlMailRecipientType](https://msdn.microsoft.com/library/bb647641\(v=office.15\)) enumeration.</span></span>


> [!NOTE]
> <span data-ttu-id="3dbf5-108">**Recipient** 对象的 **Type** 属性是 int 类型，与特定收件人类型枚举无关。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-108">The **Type** property of the **Recipient** object is an int type and does not correlate to a specific recipient type enumeration.</span></span>

<span data-ttu-id="3dbf5-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="3dbf5-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-110">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="3dbf5-111">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="3dbf5-111">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void SetRecipientTypeForMail()
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.Subject = "Sample Message";
    Outlook.Recipient recipTo =
        mail.Recipients.Add("someone@example.com");
    recipTo.Type = (int)Outlook.OlMailRecipientType.olTo;
    Outlook.Recipient recipCc =
        mail.Recipients.Add("someonecc@example.com");
    recipCc.Type = (int)Outlook.OlMailRecipientType.olCC;
    Outlook.Recipient recipBcc =
        mail.Recipients.Add("someonebcc@example.com");
    recipBcc.Type = (int)Outlook.OlMailRecipientType.olBCC;
    mail.Recipients.ResolveAll();
    mail.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="3dbf5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dbf5-112">See also</span></span>

- [<span data-ttu-id="3dbf5-113">邮件</span><span class="sxs-lookup"><span data-stu-id="3dbf5-113">Mail</span></span>](mail.md)

