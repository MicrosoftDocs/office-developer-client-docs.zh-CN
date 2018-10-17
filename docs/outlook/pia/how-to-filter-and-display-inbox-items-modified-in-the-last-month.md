---
title: 筛选并显示上月修改的收件箱项目
TOCTitle: Filter and display Inbox items modified in the last month
ms:assetid: ef6004dc-0b5a-4d1f-8937-1384d1dfc1ca
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424482(v=office.15)
ms:contentKeyID: 55119886
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 952d28cc64ffa3638f8147b665e88a372dc81848
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406874"
---
# <a name="filter-and-display-inbox-items-modified-in-the-last-month"></a>筛选并显示上月修改的收件箱项目

此示例展示如何筛选并显示上月修改的收件箱项目。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

DAV 搜索和定位 (DASL) 查询语言基于 Outlook 中 DASL 的 Microsoft Exchange 实现。 它可用于在对文件夹数据的项目级搜索中返回基于属性的结果，例如使用 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象代表的结果。 通过使用等号 (=) 运算符，DASL 筛选器支持字符串比较，其中包括等价、前缀、短语和子字符串匹配。 DASL 查询可用于执行日期/时间比较和筛选。

由于 DASL 查询始终采用协调世界时 (UTC) 形式执行 **DateTime** 比较，因此如果希望查询能够正确运行，则必须将本地时间值转换为 UTC。因 DASL 筛选器支持字符串比较的缘故，还必须将 **DateTime** 值转换成字符串表现形式。可以通过两种方式进行 **DateTime** 转换：使用 [Row](https://msdn.microsoft.com/library/bb645832\(v=office.15\)) 对象的 [LocalTimeToUTC(Object)](https://msdn.microsoft.com/library/bb610126\(v=office.15\)) 方法，或使用 Outlook **DateTime** 宏进行转换。

下面的代码行演示如何使用 **LocalTimeToUTC** 方法将 **LastModificationTime** 属性（所有 **Item** 对象中的默认列）的值转换为 UTC。

```csharp
DateTime modified = nextRow.LocalTimeUTC(“LastModificationTime”);
```

下表列出了可用来返回筛选后的字符串的 **DateTime** 宏，这些字符串是将给定的 **DateTime** 属性值与 UTC 中指定的相对日期或时间范围加以比较的结果。 SchemaName 属性值表示由命名空间引用的任何有效的 **DateTime** 属性。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>宏</p></th>
<th><p>语法</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>今天</p></td>
<td><p>%today(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值等于今天的项目。</p></td>
</tr>
<tr class="even">
<td><p>tomorrow</p></td>
<td><p>%tomorrow(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值等于明天的项目。</p></td>
</tr>
<tr class="odd">
<td><p>yesterday</p></td>
<td><p>%yesterday(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值等于昨天的项目。</p></td>
</tr>
<tr class="even">
<td><p>next7days</p></td>
<td><p>%next7days(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在接下来七天范围内的项目。</p></td>
</tr>
<tr class="odd">
<td><p>last7days</p></td>
<td><p>%last7days(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在过去七天范围内的项目。</p></td>
</tr>
<tr class="even">
<td><p>nextweek</p></td>
<td><p>%nextweek(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在下一周范围内的项目。</p></td>
</tr>
<tr class="odd">
<td><p>thisweek</p></td>
<td><p>%thisweek(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在当周范围内的项目。</p></td>
</tr>
<tr class="even">
<td><p>lastweek</p></td>
<td><p>%lastweek(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在上一周范围内的项目。</p></td>
</tr>
<tr class="odd">
<td><p>nextmonth</p></td>
<td><p>%nextmonth(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在下个月范围内的项目。</p></td>
</tr>
<tr class="even">
<td><p>thismonth</p></td>
<td><p>%thismonth(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在当月范围内的项目。</p></td>
</tr>
<tr class="odd">
<td><p>lastmonth</p></td>
<td><p>%lastmonth(“SchemaName”)%</p></td>
<td><p>限制为 SchemaName 属性值在上个月范围内的项目。</p></td>
</tr>
</tbody>
</table>


在下面的示例中，DemoDASLDateMacro 会创建一个 DASL 查询，该查询使用 **lastmonthDateTime** 宏在用户的收件箱中筛选上个月修改的项目。 然后，它会使用该筛选器创建 **Table**，并枚举和显示受限 **Table** 对象中的各行。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoDASLDateMacro()
{
    string filter = "@SQL=" + "%lastmonth(" + "\"" +
        "DAV:getlastmodified" + "\"" + ")%";
    Outlook.Table table = Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).GetTable(
        filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row row = table.GetNextRow();
        Debug.WriteLine(row["Subject"]);
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

