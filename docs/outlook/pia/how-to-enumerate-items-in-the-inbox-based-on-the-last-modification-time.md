---
title: 根据上次修改时间枚举收件箱中的项
TOCTitle: Enumerate items in the Inbox based on the last modification time
ms:assetid: 93a25143-def6-4832-bac2-3744558c2736
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184626(v=office.15)
ms:contentKeyID: 55119920
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0a568209caf172fbab26af1441ba7c208562ae19
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698391"
---
# <a name="enumerate-items-in-the-inbox-based-on-the-last-modification-time"></a>根据上次修改时间枚举收件箱中的项

此代码示例展示了如何根据上次修改时间枚举“收件箱”文件夹中的项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项。 若要获取 **Table**，请对 **Folder** 或 **Search** 对象调用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法。 返回的 **Table** 中的每一项都只包含项属性的默认子集。 可以将每个 [Row](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 对象视为文件夹中的项，并将每个 [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) 对象视为项属性。 **Table** 中不支持删除、添加或更改行。 若要枚举 **Table** 中的各项目，需首先使用 [EndOfTable](https://msdn.microsoft.com/library/bb647715\(v=office.15\)) 属性来查看您的当前位置是否位于表结尾处。 如果 **EndOfTable** 返回 **false**，则使用 [GetNextRow()](https://msdn.microsoft.com/library/bb609740\(v=office.15\)) 方法来返回包含默认数量的 **Column** 对象的 **Row**。 通过调用 **GetNextRow**，继续直接循环访问 **Table**，直至 **EndOfTable** 返回 **true**。

在下面的代码示例中，DemoTableForInbox 获取“收件箱”文件夹的 **Table** 对象，使用 **LastModificationTime** 属性和 [Sort(String, Object)](https://msdn.microsoft.com/library/bb652667\(v=office.15\)) 方法对 **Table** 对象进行排序，并循环访问表，以将每一项的主题写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoTableForInbox()
{
    //Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    //Obtain Table using defaults
    Outlook.Table table =
        folder.GetTable(Type.Missing, Type.Missing);
    table.Sort("LastModificationTime",
        Outlook.OlSortOrder.olDescending);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        Debug.WriteLine(nextRow["Subject"]);
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

