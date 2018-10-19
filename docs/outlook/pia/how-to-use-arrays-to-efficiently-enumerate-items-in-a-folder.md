---
title: 使用数组高效枚举文件夹中的项
TOCTitle: Use arrays to efficiently enumerate items in a folder
ms:assetid: 05a73225-ad0d-4d52-90b6-448d220348df
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184588(v=office.15)
ms:contentKeyID: 55119885
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d165b27da58a4e99eabb897aac3d2dc03811f588
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407504"
---
# <a name="use-arrays-to-efficiently-enumerate-items-in-a-folder"></a>使用数组高效枚举文件夹中的项

此代码示例展示了如何使用 [GetArray(Int32)](https://msdn.microsoft.com/library/bb608928\(v=office.15\)) 方法高效枚举 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象中的项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，DemoGetArrayForTable 使用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法，从 **Folder** 对象中获取 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象。 然后，DemoGetArrayForTable 使用 **GetArray** 方法，返回包含表中每行元素的 [Array](https://msdn.microsoft.com/library/system.array.aspx) 对象。 返回的 **Array** 对象是一个二维数组，表示 **Table** 中的一系列行值和列值。 此数组从 0 开始计数，与 Outlook 集合从 1 开始计数不同。 获取 **Array** 对象后，此代码便会使用 for 循环枚举整个表。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoGetArrayForTable()
{
    // Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    Outlook.Table table =
        folder.GetTable("", Outlook.OlTableContents.olUserItems);
    Array tableArray = table.GetArray(table.GetRowCount()) as Array;
    for (int i = 0; i <= tableArray.GetUpperBound(0); i++)
    {
        for (int j = 0; j <= tableArray.GetUpperBound(1); j++)
        {
            Debug.WriteLine(tableArray.GetValue(i, j));
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

