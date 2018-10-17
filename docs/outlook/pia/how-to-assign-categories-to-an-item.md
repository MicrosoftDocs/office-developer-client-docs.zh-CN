---
title: 向项分配类别
TOCTitle: Assign categories to an item
ms:assetid: 4070801b-994a-46df-91fe-4efca834886e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424469(v=office.15)
ms:contentKeyID: 55119828
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 762fd5954e6ec47aed24a9c91b41839f6d292cd9
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407189"
---
# <a name="assign-categories-to-an-item"></a><span data-ttu-id="304c1-102">向项分配类别</span><span class="sxs-lookup"><span data-stu-id="304c1-102">Assign categories to an item</span></span>

<span data-ttu-id="304c1-103">此代码示例展示了如何使用 **Categories** 属性向项分配类别。</span><span class="sxs-lookup"><span data-stu-id="304c1-103">This example shows how to assign categories to an item by using its **Categories** property.</span></span>

## <a name="example"></a><span data-ttu-id="304c1-104">示例</span><span class="sxs-lookup"><span data-stu-id="304c1-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="304c1-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="304c1-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="304c1-106">若要向项分配类别，请使用特定项的 **Categories** 属性。</span><span class="sxs-lookup"><span data-stu-id="304c1-106">To assign categories to an item, use the particular item's **Categories** property.</span></span> <span data-ttu-id="304c1-107">此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.**Categories** 属性，无需先强制转换项。</span><span class="sxs-lookup"><span data-stu-id="304c1-107">This code sample makes use of the OutlookItem helper class, defined in [Create a Helper Class to Access Common Outlook Item Members](how-to-create-a-helper-class-to-access-common-outlook-item-members.md), to conveniently call the OutlookItem.**Categories** property without having to first cast the item.</span></span> <span data-ttu-id="304c1-108">**Categories** 属性用于获取或设置以逗号分隔的字符串（最多可包含 255 个字符）表示的类别。</span><span class="sxs-lookup"><span data-stu-id="304c1-108">This property gets or sets categories that are represented by a comma-delimited string that can contain a maximum of 255 characters.</span></span> <span data-ttu-id="304c1-109">类别值是以逗号和空格分隔。</span><span class="sxs-lookup"><span data-stu-id="304c1-109">The commas and spaces are used to separate the category values.</span></span> <span data-ttu-id="304c1-110">分配 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) 集合中没有的类别会导致类别不显示颜色。</span><span class="sxs-lookup"><span data-stu-id="304c1-110">Assigning a category that is not in the [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) collection of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object will result in the category not displaying a color.</span></span>

<span data-ttu-id="304c1-p102">在下面的代码示例中，AssignCategories 创建一个用于主题中包含“ISV”的项目的限制，方法是首先使用 DAV 搜索和定位 (DASL) 查询来筛选收件箱中主题中包含“ISV”的项目，然后 AssignCategories 通过使用 **OutlookItem** 类循环访问筛选出的项目，如果 **item.Categories** 返回的字符串不是 null 引用或已分配给 ISV，则 ISV 类别将被分配给相应项目。</span><span class="sxs-lookup"><span data-stu-id="304c1-p102">In the following code example, AssignCategories creates a restriction for items that contain “ISV” in the subject by first using a DAV Searching and Locating (DASL) query to filter items in the Inbox that contain “ISV” in the subject. AssignCategories then iterates through the filtered items by using the **OutlookItem** class and, if the string returned by **item.Categories** is not a null reference or was already assigned to the ISV, the ISV category is assigned to the item.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void AssignCategories()
{
    string filter = "@SQL=" + "\"" + "urn:schemas:httpmail:subject"
        + "\"" + " ci_phrasematch 'ISV'";
    Outlook.Items items =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).Items.Restrict(filter);
    for (int i = 1; i <= items.Count; i++)
    {
        OutlookItem item = new OutlookItem(items[i]);
        string existingCategories = item.Categories;
        if (String.IsNullOrEmpty(existingCategories))
        {
            item.Categories = "ISV";
        }
        else
        {
            if (item.Categories.Contains("ISV") == false)
            {
                item.Categories = existingCategories + ", ISV";
            }
        }
        item.Save();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="304c1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="304c1-113">See also</span></span>

- [<span data-ttu-id="304c1-114">颜色类别</span><span class="sxs-lookup"><span data-stu-id="304c1-114">Color Categories</span></span>](color-categories.md)

