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
# <a name="assign-categories-to-an-item"></a>向项分配类别

此代码示例展示了如何使用 **Categories** 属性向项分配类别。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


若要向项分配类别，请使用特定项的 **Categories** 属性。 此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.**Categories** 属性，无需先强制转换项。 **Categories** 属性用于获取或设置以逗号分隔的字符串（最多可包含 255 个字符）表示的类别。 类别值是以逗号和空格分隔。 分配 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) 集合中没有的类别会导致类别不显示颜色。

在下面的代码示例中，AssignCategories 创建一个用于主题中包含“ISV”的项目的限制，方法是首先使用 DAV 搜索和定位 (DASL) 查询来筛选收件箱中主题中包含“ISV”的项目，然后 AssignCategories 通过使用 **OutlookItem** 类循环访问筛选出的项目，如果 **item.Categories** 返回的字符串不是 null 引用或已分配给 ISV，则 ISV 类别将被分配给相应项目。

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

## <a name="see-also"></a>另请参阅

- [颜色类别](color-categories.md)

