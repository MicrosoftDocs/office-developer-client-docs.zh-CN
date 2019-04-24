---
title: 创建联系人项
TOCTitle: Create a Contact item
ms:assetid: b316294a-7f70-4e54-9375-4dc515e9fd11
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184633(v=office.15)
ms:contentKeyID: 55119823
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 11bfe40d29832577186712e269f9c0971e1e2be6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359673"
---
# <a name="create-a-contact-item"></a><span data-ttu-id="8cdd7-102">创建联系人项</span><span class="sxs-lookup"><span data-stu-id="8cdd7-102">Create a Contact item</span></span>

<span data-ttu-id="8cdd7-103">此代码示例展示了如何创建联系人项，并设置联系人的各种属性。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-103">This example shows how to create a contact item and set various properties for the contact.</span></span>

## <a name="example"></a><span data-ttu-id="8cdd7-104">示例</span><span class="sxs-lookup"><span data-stu-id="8cdd7-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="8cdd7-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="8cdd7-106">Outlook [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象内置有超过 100 个属性，如 [Department](https://msdn.microsoft.com/library/bb610564\(v=office.15\))、[CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\))、[OfficeLocation](https://msdn.microsoft.com/library/bb647145\(v=office.15\)) 和 [JobTitle](https://msdn.microsoft.com/library/bb609294\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-106">An Outlook [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) object has more than 100 built-in properties such as [Department](https://msdn.microsoft.com/library/bb610564\(v=office.15\)), [CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)), [OfficeLocation](https://msdn.microsoft.com/library/bb647145\(v=office.15\)), and [JobTitle](https://msdn.microsoft.com/library/bb609294\(v=office.15\)).</span></span> <span data-ttu-id="8cdd7-107">如果内置属性不可用，可使用 [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) 集合添加自定义属性。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-107">You can add custom properties, if a built-in property is not available, by using the [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) collection.</span></span> <span data-ttu-id="8cdd7-108">创建 **ContactItem** 后，便能设置它的属性。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-108">Once you create a **ContactItem**, you can set its properties.</span></span>

<span data-ttu-id="8cdd7-109">在下面的代码示例中，CreateContactExample 创建 **ContactItem**，并设置此对象的常用属性。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-109">In the following code example, CreateContactExample creates a **ContactItem** and sets commonly used properties for that object.</span></span> <span data-ttu-id="8cdd7-110">然后，它对 **ContactItem** 对象调用 [ShowCheckPhoneDialog(OlContactPhoneNumber)](https://msdn.microsoft.com/library/bb646168\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-110">It then calls the [ShowCheckPhoneDialog(OlContactPhoneNumber)](https://msdn.microsoft.com/library/bb646168\(v=office.15\)) method on the **ContactItem** object.</span></span> <span data-ttu-id="8cdd7-111">借助 **ShowCheckPhoneDialog** 方法，用户可以根据本地拨号约定解析电话号码。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-111">The **ShowCheckPhoneDialog** method allows the user to resolve a phone number based on local dialing conventions.</span></span>

<span data-ttu-id="8cdd7-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="8cdd7-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-113">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="8cdd7-114">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="8cdd7-114">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateContactExample()
{
    Outlook.ContactItem contact = Application.CreateItem(
        Outlook.OlItemType.olContactItem) as Outlook.ContactItem;
    contact.FirstName = "Mellissa";
    contact.LastName = "MacBeth";
    contact.JobTitle = "Account Representative";
    contact.CompanyName = "Contoso Ltd.";
    contact.OfficeLocation = "36/2529";
    contact.BusinessTelephoneNumber = "4255551212 x432";
    contact.WebPage = "https://www.contoso.com";
    contact.BusinessAddressStreet = "1 Microsoft Way";
    contact.BusinessAddressCity = "Redmond";
    contact.BusinessAddressState = "WA";
    contact.BusinessAddressPostalCode = "98052";
    contact.BusinessAddressCountry =
        "United States of America";
    contact.Email1Address = "melissa@contoso.com";
    contact.Email1AddressType = "SMTP";
    contact.Email1DisplayName =
        "Melissa MacBeth (mellissa@contoso.com)";
    contact.Display(false);
    contact.ShowCheckPhoneDialog(
        Outlook.OlContactPhoneNumber.
        olContactPhoneBusiness);
}
```

## <a name="see-also"></a><span data-ttu-id="8cdd7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cdd7-115">See also</span></span>

- [<span data-ttu-id="8cdd7-116">联系人</span><span class="sxs-lookup"><span data-stu-id="8cdd7-116">Contacts</span></span>](contacts.md)

