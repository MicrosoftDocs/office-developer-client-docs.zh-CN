---
title: 在枚举文件夹中的项时筛选并显示多值属性
TOCTitle: Filter and display multivalued properties when enumerating items in a folder
ms:assetid: 62dd2120-5c85-44b3-89ec-c4ca85aa2964
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184613(v=office.15)
ms:contentKeyID: 55119887
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: acb6f6807f956ee6d468d3fcefc2cdd27732ab9b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320319"
---
# <a name="filter-and-display-multivalued-properties-when-enumerating-items-in-a-folder"></a>在枚举文件夹中的项时筛选并显示多值属性

此代码示例展示了如何在枚举文件夹中的项时筛选并显示多值属性。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象表示 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 或 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象中的一组项目数据。首次将二进制、日期或多值属性添加到 **Table** 对象时，此类属性的引用方式将影响其类型和格式。因为内置名称引用有时会返回与命名空间引用不同的列值，所以您应确定属性是由其显式内置名称（如果具有这样一个名称）引用，还是由命名空间引用（无论是否存在显式内置名称）。下表显示了每个原始属性类型的属性值表示形式（类型和格式方面）的差异。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>类型</p></th>
<th><p>指定的属性使用内置名称时的返回类型</p></th>
<th><p>指定属性使用命名空间时的返回类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>二进制 <b>(PT_BINARY)</b></p></td>
<td><p>字符串</p></td>
<td><p>字节数组</p></td>
</tr>
<tr class="even">
<td><p>日期 <b>(PT_SYSTIME)</b></p></td>
<td><p>本地 <b>DateTime</b></p></td>
<td><p>UTC <b>DateTime</b></p></td>
</tr>
<tr class="odd">
<td><p>多值类型（亦称为“关键字类型”），如 <b>Categories</b> 属性 <b>(PT_MV_STRING8)</b></p></td>
<td><p>包含逗号分隔值的字符串</p></td>
<td><p>所含每个关键字对应一个元素的一维数组</p></td>
</tr>
</tbody>
</table>


下面的代码示例阐释如何将 MAPI 字符串命名空间属性添加到 **Table** 对象，以及多值属性如何影响 [Column](https://msdn.microsoft.com/library/bb609646\(v=office.15\)) 对象中返回的值。 TableMultiValuedProperties 过程从 **Table** 对象中筛选出 [Categories](https://msdn.microsoft.com/library/bb646607\(v=office.15\)) 属性不是空引用的行。 **Categories** 属性由使用 MAPI 字符串命名空间的属性表示。 DAV 搜索和定位 (DASL) 筛选器是针对具有类别的项目而构造的（实际筛选器返回不具有 null 引用的类别）。 然后，通过连接类型说明符 0000001f 和 categoriesProperty 常量，将 **Categories** 列添加到 **Table** 对象中。 表示 **Categories** 属性的 **Column** 对象最后会包含一个一维字符串数组，其中数组的每个元素都表示一个分配给相应项目的类别。 项的 **Categories** 和 **Subject** 属性均被写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void TableMultiValuedProperties()
{
    const string categoriesProperty =
        "https://schemas.microsoft.com/mapi/string/"
        + "{00020329-0000-0000-C000-000000000046}/Keywords";
    // Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Call GetTable with filter for categories
    string filter = "@SQL="
        + "Not(" + "\"" + categoriesProperty
        + "\"" + " Is Null)";
    Outlook.Table table =
        folder.GetTable(filter,
        Outlook.OlTableContents.olUserItems);
    // Add categories column and append type specifier
    table.Columns.Add(categoriesProperty + "/0000001F");
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        string[] categories =
            (string[])nextRow[categoriesProperty + "/0000001F"];
        Debug.WriteLine("Subject: " + nextRow["Subject"]);
        Debug.Write("Categories: ");
        foreach (string category in categories)
        {
            Debug.Write("\t" + category);
        }
        Debug.WriteLine("\n");
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

