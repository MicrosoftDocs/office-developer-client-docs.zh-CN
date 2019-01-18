---
title: 创建自定义联系人项
TOCTitle: Create a custom Contact item
ms:assetid: 24b2a104-a0a7-469b-9676-a07cab613f59
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184596(v=office.15)
ms:contentKeyID: 55119831
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4261fffef0934e01cbfbcc7068377cc392af178c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716423"
---
# <a name="create-a-custom-contact-item"></a><span data-ttu-id="77303-102">创建自定义联系人项</span><span class="sxs-lookup"><span data-stu-id="77303-102">Create a custom Contact item</span></span>

<span data-ttu-id="77303-103">此代码示例展示了如何创建自定义联系人项，并设置预定义属性和用户定义的属性。</span><span class="sxs-lookup"><span data-stu-id="77303-103">This example shows how to create a custom contact item and set both predefined and user-defined properties.</span></span>

## <a name="example"></a><span data-ttu-id="77303-104">示例</span><span class="sxs-lookup"><span data-stu-id="77303-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="77303-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="77303-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="77303-106">[ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象表示“联系人”文件夹中的联系人，内置有 [FirstName](https://msdn.microsoft.com/library/bb652965\(v=office.15\)) 和 [LastName](https://msdn.microsoft.com/library/bb609750\(v=office.15\)) 等超过 100 个属性。</span><span class="sxs-lookup"><span data-stu-id="77303-106">A [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) object represents a contact in the Contacts folder, and has more than 100 built-in properties such as [FirstName](https://msdn.microsoft.com/library/bb652965\(v=office.15\)) and [LastName](https://msdn.microsoft.com/library/bb609750\(v=office.15\)).</span></span> <span data-ttu-id="77303-107">有时，内置属性不足，需要添加自定义属性，为此可使用 [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) 集合。</span><span class="sxs-lookup"><span data-stu-id="77303-107">Sometimes, the built-in properties are not sufficient and you need to add custom properties, which you can do by using the [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) collection.</span></span>

<span data-ttu-id="77303-108">在下面的代码示例中，CreateCustomItem 先创建自定义 **ContactItem** 对象并命名为“鞋店”，再调用 [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) 方法，将对象添加到“鞋店”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="77303-108">In the following code example, CreateCustomItem creates a custom **ContactItem** object, names it "Shoe Store", and calls the [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) method to add it to a folder named "Shoe Store".</span></span> <span data-ttu-id="77303-109">首先，CreateCustomItem 使用 [GetDefaultFolder(OlDefaultFolders)](https://msdn.microsoft.com/library/bb646473\(v=office.15\)) 方法，以获取“鞋店”文件夹。</span><span class="sxs-lookup"><span data-stu-id="77303-109">CreateCustomItem first gets the "Shoe Store" folder by using the [GetDefaultFolder(OlDefaultFolders)](https://msdn.microsoft.com/library/bb646473\(v=office.15\)) method.</span></span> <span data-ttu-id="77303-110">“鞋店”文件夹是默认“联系人”文件夹的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="77303-110">The "Shoe Store" folder is a subfolder of the default Contacts folder.</span></span> <span data-ttu-id="77303-111">然后，CreateCustomItem 设置 **FirstName** 和 **LastName** 属性，并使用 **UserProperties** 集合创建用户定义的属性（“鞋码”）。</span><span class="sxs-lookup"><span data-stu-id="77303-111">CreateCustomItem then sets the **FirstName** and **LastName** properties, and creates a user-defined property ("Shoe Size") by using the **UserProperties** collection.</span></span>

<span data-ttu-id="77303-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="77303-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="77303-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="77303-113">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="77303-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="77303-114">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateCustomItem()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts).Folders[
        "Shoe Store"] as Outlook.Folder;
    Outlook.ContactItem contact =
        folder.Items.Add(
        "IPM.Contact.Shoe Store") as Outlook.ContactItem;
    contact.FirstName = "Michael";
    contact.LastName = "Affronti";
    contact.UserProperties["Shoe Size"].Value = "9";
    contact.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="77303-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77303-115">See also</span></span>

- [<span data-ttu-id="77303-116">联系人</span><span class="sxs-lookup"><span data-stu-id="77303-116">Contacts</span></span>](contacts.md)

