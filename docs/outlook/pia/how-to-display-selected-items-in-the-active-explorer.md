---
title: 显示有效资源管理器中的选定项
TOCTitle: Display selected items in the active Explorer
ms:assetid: 31bb217b-8b45-4b50-942e-b6c2a7f13c83
ms:mtpsurl: https://msdn.microsoft.com/library/Dn292517(v=office.15)
ms:contentKeyID: 55119844
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b722bcb404f987a6f07a9fe305046ea6673dc231
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356383"
---
# <a name="display-selected-items-in-the-active-explorer"></a>显示有效资源管理器中的选定项

此代码示例展示了如何使用 OutlookItem 帮助程序类，便捷地显示有效资源管理器窗口中的所有选定项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) 对象包含有效 Outlook 资源管理器中的一组当前选定 Outlook 项。 [ActiveExplorer()](https://msdn.microsoft.com/library/bb647410\(v=office.15\)) 表示的有效资源管理器和一组选定项都未指明选定项的类型。 通常情况下，必须先标识项类型，然后调用相应类型的专用 **Display** 方法。 因为 **Display** 方法对所有 Outlook 项对象都是通用的，且 OutlookItem 帮助程序类包含此方法，所以可利用帮助程序类，具体方法是声明 OutlookItem 对象 myItem 的实例，并使用 myItem.Display 显示所有选定项。 若要了解如何实现 OutlookItem 帮助程序类，可访问[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DisplaySelectedItems()
{
    Outlook.Selection selection =
        Application.ActiveExplorer().Selection;
    for (int i = 1; i <= selection.Count; i++)
    {
        OutlookItem myItem = new OutlookItem(selection[i]);
        myItem.Display();
    }
}
```

## <a name="see-also"></a>另请参阅

- [创建用于访问常见 Outlook 项成员的帮助程序类员](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)
- [常规 Outlook 项](general-outlook-items.md)

