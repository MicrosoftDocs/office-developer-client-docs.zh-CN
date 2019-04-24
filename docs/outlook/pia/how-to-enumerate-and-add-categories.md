---
title: 枚举和添加类别
TOCTitle: Enumerate and add categories
ms:assetid: 17a94a01-c463-4332-851e-7d280c66d8c2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424467(v=office.15)
ms:contentKeyID: 55119829
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 488e00971adb1f2fa38555039478ac830d3c9f7a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320410"
---
# <a name="enumerate-and-add-categories"></a>枚举和添加类别

此示例演示如何枚举类别并将一个类别添加到主类别列表。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

Outlook 对象模型支持可帮助分类用户收件箱中的项目的类别。 为了保持较高的分类级别，请执行下列操作：

- 对 Outlook 项目进行分类并按类别显示它们。
- 将多个颜色类别应用到单个 Outlook 项目。
- 按颜色类别对 Outlook 项目进行分组和排序。
- 为每个颜色类别分配快捷键，使用户能够更轻松地分类项目。
- 通过编程方式或通过 Outlook 用户界面内的用户操作创建、删除和更改颜色类别。

为了公开类别的功能，Outlook 对象模型提供了一个 [Category](https://msdn.microsoft.com/library/bb623480\(v=office.15\)) 对象，该对象表示主类别列表中的单个用户定义颜色类别。 主类别列表包含 Outlook 用户界面中显示的颜色类别。 该列表由 [NameSpace](https://msdn.microsoft.com/library/bb623535\(v=office.15\)) 对象的 [Categories](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 集合表示。 若要创建 **Category** 对象，请使用 [Categories](https://msdn.microsoft.com/library/bb623093\(v=office.15\)) 集合的 **Add(String, Object, Object)** 方法。 当创建 **Category** 对象时，会创建一个全局唯一标识符 (GUID)，此标识符无法更改。 此标识符通过 [CategoryID](https://msdn.microsoft.com/library/bb647100\(v=office.15\)) 属性表示。 但是，你可以通过分别设置 **Category** 对象的 [Name](https://msdn.microsoft.com/library/bb645577\(v=office.15\))、[Color](https://msdn.microsoft.com/library/bb612316\(v=office.15\)) 和 [ShortcutKey](https://msdn.microsoft.com/library/bb644944\(v=office.15\)) 属性，来更改与某个颜色类别关联的名称、颜色和快捷键。 你可以通过设置或获取 **Color** 属性的 [OlCategoryColor](https://msdn.microsoft.com/library/bb608974\(v=office.15\)) 常量来更改该属性。 若要在自定义控件中重现该颜色，请使用 **Category** 属性的下列只读属性：

  - [CategoryBorderColor](https://msdn.microsoft.com/library/bb610083\(v=office.15\))

  - [CategoryGradientBottomColor](https://msdn.microsoft.com/library/bb647357\(v=office.15\))

  - [CategoryGradientTopColor](https://msdn.microsoft.com/library/bb623975\(v=office.15\))

这些属性会返回一个 **OLE\_COLOR** 值，具体取决于 **Category** 对象的 **Color** 属性。

Outlook 项目是基于类别名称显示的。每个项目对象都具有一个 **Categories** 属性，用于存储表示类别名称的逗号分隔的字符串。（例如，对于 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象，您将会使用 **MailItem** [Categories](https://msdn.microsoft.com/library/bb646442\(v=office.15\)) 属性）。这样，您就可以将某一类别添加到项目中，即使主类别列表中不存在该类别。


> [!NOTE]
> [!注释] 如果某个项目的 **Categories** 属性包含的类别名称不在 **NameSpace** 对象的 **Categories** 集合中，则将显示与该 Outlook 项目关联的类别名称，但是不会显示关联的颜色。 **Item** 对象的 **Categories** 属性不会返回 **Categories** 集合。

在以下代码示例中，第一个过程 EnumerateCategories 会获取当前用户的主类别列表（由 **Categories** 集合表示）。 然后，它会枚举该集合中的 **Category** 对象，并将 **Name** 和 **CategoryID** 属性写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。 第二个过程 AddACategory 会获取当前用户的主类别列表并使用 CategoryExists 方法来检查集合中是否存在名为“ISV”的类别。 如果没有名为“ISV”的类别，AddACategory 将会使用 **Categories** 集合的 **Add** 方法向主类别列表添加一个名为“ISV”的类别并为其分配深蓝色的颜色。 它还会为该类别分配 CTRL+F11 这一快捷键。

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

## <a name="see-also"></a>另请参阅

- [颜色类别](color-categories.md)

