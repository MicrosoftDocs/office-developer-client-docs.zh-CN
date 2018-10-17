---
title: 枚举和添加类别
TOCTitle: Enumerate and add categories
ms:assetid: 17a94a01-c463-4332-851e-7d280c66d8c2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424467(v=office.15)
ms:contentKeyID: 55119829
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 27fc8630c8e2eb0b491dbb5075f4c58aacec7f93
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406244"
---
# <a name="enumerate-and-add-categories"></a><span data-ttu-id="e2be6-102">枚举和添加类别</span><span class="sxs-lookup"><span data-stu-id="e2be6-102">Enumerate and add categories</span></span>

<span data-ttu-id="e2be6-103">此示例演示如何枚举类别并将一个类别添加到主类别列表。</span><span class="sxs-lookup"><span data-stu-id="e2be6-103">This example shows how to enumerate categories and add a category to the main category list.</span></span>

## <a name="example"></a><span data-ttu-id="e2be6-104">示例</span><span class="sxs-lookup"><span data-stu-id="e2be6-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="e2be6-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="e2be6-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="e2be6-106">Outlook 对象模型支持可帮助分类用户收件箱中的项目的类别。</span><span class="sxs-lookup"><span data-stu-id="e2be6-106">The Microsoft Outlook object model supports categories that help organize items in a user's Inbox.</span></span> <span data-ttu-id="e2be6-107">为了保持较高的分类级别，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e2be6-107">To maintain a higher level of organization, you can do the following:</span></span>

- <span data-ttu-id="e2be6-108">对 Outlook 项目进行分类并按类别显示它们。</span><span class="sxs-lookup"><span data-stu-id="e2be6-108">Categorize Outlook items and display them by category.</span></span>
- <span data-ttu-id="e2be6-109">将多个颜色类别应用到单个 Outlook 项目。</span><span class="sxs-lookup"><span data-stu-id="e2be6-109">Apply multiple color categories to a single Outlook item.</span></span>
- <span data-ttu-id="e2be6-110">按颜色类别对 Outlook 项目进行分组和排序。</span><span class="sxs-lookup"><span data-stu-id="e2be6-110">Group and sort Outlook items by color category.</span></span>
- <span data-ttu-id="e2be6-111">为每个颜色类别分配快捷键，使用户能够更轻松地分类项目。</span><span class="sxs-lookup"><span data-stu-id="e2be6-111">Assign shortcut keys to each color category, enabling users to more easily categorize items.</span></span>
- <span data-ttu-id="e2be6-112">通过编程方式或通过 Outlook 用户界面内的用户操作创建、删除和更改颜色类别。</span><span class="sxs-lookup"><span data-stu-id="e2be6-112">Create, delete, and change color categories either programmatically, or by user action within the Outlook user interface.</span></span>

<span data-ttu-id="e2be6-113">为了公开类别的功能，Outlook 对象模型提供了一个 [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) 对象，该对象表示主类别列表中的单个用户定义颜色类别。</span><span class="sxs-lookup"><span data-stu-id="e2be6-113">To expose the functionality of categories, the Outlook object model provides a [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) object that represents a single user-defined color category in the main category list.</span></span> <span data-ttu-id="e2be6-114">主类别列表包含 Outlook 用户界面中显示的颜色类别。</span><span class="sxs-lookup"><span data-stu-id="e2be6-114">The main category list contains color categories that are presented in the Outlook user interface.</span></span> <span data-ttu-id="e2be6-115">该列表由 [NameSpace](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) 对象的 [Categories](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 集合表示。</span><span class="sxs-lookup"><span data-stu-id="e2be6-115">The list is represented by the [Categories](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) collection of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span> <span data-ttu-id="e2be6-116">若要创建 **Category** 对象，请使用 [Categories](https://msdn.microsoft.com/library/bb623093\(v=office.15\)) 集合的 **Add(String, Object, Object)** 方法。</span><span class="sxs-lookup"><span data-stu-id="e2be6-116">To create a **Category** object, use the [Add(String, Object, Object)](https://msdn.microsoft.com/library/bb623093\(v=office.15\)) method of the **Categories** collection.</span></span> <span data-ttu-id="e2be6-117">当创建 **Category** 对象时，会创建一个全局唯一标识符 (GUID)，此标识符无法更改。</span><span class="sxs-lookup"><span data-stu-id="e2be6-117">When you create a **Category** object, a globally unique identifier (GUID) is created, and this identifier cannot be changed.</span></span> <span data-ttu-id="e2be6-118">此标识符通过 [CategoryID](https://msdn.microsoft.com/library/bb647100\(v=office.15\)) 属性表示。</span><span class="sxs-lookup"><span data-stu-id="e2be6-118">It is represented by the [CategoryID](https://msdn.microsoft.com/library/bb647100\(v=office.15\)) property.</span></span> <span data-ttu-id="e2be6-119">但是，你可以通过分别设置 **Category** 对象的 [Name](https://msdn.microsoft.com/library/bb645577\(v=office.15\))、[Color](https://msdn.microsoft.com/library/bb612316\(v=office.15\)) 和 [ShortcutKey](https://msdn.microsoft.com/library/bb644944\(v=office.15\)) 属性，来更改与某个颜色类别关联的名称、颜色和快捷键。</span><span class="sxs-lookup"><span data-stu-id="e2be6-119">You can, however, change the name, color, and shortcut key associated with a color category by setting the [Name](https://msdn.microsoft.com/library/bb645577\(v=office.15\)) , [Color](https://msdn.microsoft.com/library/bb612316\(v=office.15\)) , and [ShortcutKey](https://msdn.microsoft.com/library/bb644944\(v=office.15\)) properties, respectively, of the **Category** object.</span></span> <span data-ttu-id="e2be6-120">你可以通过设置或获取 **Color** 属性的 [OlCategoryColor](https://msdn.microsoft.com/library/bb608974\(v=office.15\)) 常量来更改该属性。</span><span class="sxs-lookup"><span data-stu-id="e2be6-120">You can change the **Color** property by setting or getting its [OlCategoryColor](https://msdn.microsoft.com/library/bb608974\(v=office.15\)) constant.</span></span> <span data-ttu-id="e2be6-121">若要在自定义控件中重现该颜色，请使用 **Category** 属性的下列只读属性：</span><span class="sxs-lookup"><span data-stu-id="e2be6-121">To reproduce the color in a custom control, use the following read-only properties of the **Category** object:</span></span>

  - <span data-ttu-id="e2be6-122">[CategoryBorderColor](https://msdn.microsoft.com/library/bb610083\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="e2be6-122">[expression  . CategoryBorderColor](https://msdn.microsoft.com/library/bb610083\(v=office.15\))</span></span>

  - <span data-ttu-id="e2be6-123">[CategoryGradientBottomColor](https://msdn.microsoft.com/library/bb647357\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="e2be6-123">[expression  . CategoryGradientBottomColor](https://msdn.microsoft.com/library/bb647357\(v=office.15\))</span></span>

  - <span data-ttu-id="e2be6-124">[CategoryGradientTopColor](https://msdn.microsoft.com/library/bb623975\(v=office.15\))</span><span class="sxs-lookup"><span data-stu-id="e2be6-124">[expression  . CategoryGradientTopColor](https://msdn.microsoft.com/library/bb623975\(v=office.15\))</span></span>

<span data-ttu-id="e2be6-125">这些属性会返回一个 **OLE\_COLOR** 值，具体取决于 **Category** 对象的 **Color** 属性。</span><span class="sxs-lookup"><span data-stu-id="e2be6-125">These properties return an OLE_COLOR value, which is dependent on the Color property of the Category object.</span></span>

<span data-ttu-id="e2be6-126">系统会基于类别名称显示 Outlook 项。</span><span class="sxs-lookup"><span data-stu-id="e2be6-126">Outlook items are displayed based on the category name.</span></span> <span data-ttu-id="e2be6-127">每个项对象都具有 **Categories** 属性，该属性会存储表示类别名称的字符串，这些字符串均以逗号分隔</span><span class="sxs-lookup"><span data-stu-id="e2be6-127">Each item object has a **Categories** property that stores a comma-delimited string that represents category names.</span></span> <span data-ttu-id="e2be6-128">（例如，对于 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象，你将会使用 **MailItem** [Categories](https://msdn.microsoft.com/library/bb646442\(v=office.15\)) 属性）。</span><span class="sxs-lookup"><span data-stu-id="e2be6-128">(For example, for the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object, you would use the **MailItem**[Categories](https://msdn.microsoft.com/library/bb646442\(v=office.15\)) property).</span></span> <span data-ttu-id="e2be6-129">这样，你便可以向项目添加某个类别，即使该类别未显示在主类别列表中。</span><span class="sxs-lookup"><span data-stu-id="e2be6-129">This enables you to add a category to the item, even if the category is not present in the main category list.</span></span>


> [!NOTE]
> <span data-ttu-id="e2be6-p104">[!注释] 如果某个项目的 **Categories** 属性包含的类别名称不在 **NameSpace** 对象的 **Categories** 集合中，则将显示与该 Outlook 项目关联的类别名称，但是不会显示关联的颜色。 **Item** 对象的 **Categories** 属性不会返回 **Categories** 集合。</span><span class="sxs-lookup"><span data-stu-id="e2be6-p104">If the **Categories** property of an item contains a category name that is not in the **Categories** collection of the **NameSpace** object, the category name associated with that Outlook item is displayed, but without an associated color. The **Categories** property on an **Item** object does not return a **Categories** collection.</span></span>

<span data-ttu-id="e2be6-132">在以下代码示例中，第一个过程 EnumerateCategories 会获取当前用户的主类别列表（由 **Categories** 集合表示）。</span><span class="sxs-lookup"><span data-stu-id="e2be6-132">In the following code example, the first procedure, EnumerateCategories, gets the current user’s main list of categories, represented by the **Categories** collection.</span></span> <span data-ttu-id="e2be6-133">然后，它会枚举该集合中的 **Category** 对象，并将 **Name** 和 **CategoryID** 属性写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="e2be6-133">It then enumerates the **Category** objects in that collection, and writes the **Name** and **CategoryID** properties to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span> <span data-ttu-id="e2be6-134">第二个过程 AddACategory 会获取当前用户的主类别列表并使用 CategoryExists 方法来检查集合中是否存在名为“ISV”的类别。</span><span class="sxs-lookup"><span data-stu-id="e2be6-134">The second procedure, AddACategory, gets the current user’s main list of categories and uses the CategoryExists method to check whether a category named “ISV” exists in the collection.</span></span> <span data-ttu-id="e2be6-135">如果没有名为“ISV”的类别，AddACategory 将会使用 **Categories** 集合的 **Add** 方法向主类别列表添加一个名为“ISV”的类别并为其分配深蓝色的颜色。</span><span class="sxs-lookup"><span data-stu-id="e2be6-135">If no category with the name “ISV” exists, AddACategory adds a category named “ISV” to the main category list and assigns it a dark blue color by using the **Add** method of the **Categories** collection.</span></span> <span data-ttu-id="e2be6-136">它还会为该类别分配 CTRL+F11 这一快捷键。</span><span class="sxs-lookup"><span data-stu-id="e2be6-136">It also assigns CTRL+F11 as the shortcut key for the category.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void EnumerateCategories()
{
    Outlook.Categories categories =
        Application.Session.Categories;
    foreach (Outlook.Category category in categories)
    {
        Debug.WriteLine(category.Name);
        Debug.WriteLine(category.CategoryID);
    }
}

private void AddACategory()
{
    Outlook.Categories categories =
        Application.Session.Categories;
    if (!CategoryExists("ISV"))
    {
        Outlook.Category category = categories.Add("ISV",
            Outlook.OlCategoryColor.olCategoryColorDarkBlue,
            Outlook.OlCategoryShortcutKey.olCategoryShortcutKeyCtrlF11);
    }
}

private bool CategoryExists(string categoryName)
{
    try
    {
        Outlook.Category category = 
            Application.Session.Categories[categoryName];
        if(category != null)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
    catch { return false; }
}
```

## <a name="see-also"></a><span data-ttu-id="e2be6-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2be6-137">See also</span></span>

- [<span data-ttu-id="e2be6-138">颜色类别</span><span class="sxs-lookup"><span data-stu-id="e2be6-138">Color Categories</span></span>](color-categories.md)

