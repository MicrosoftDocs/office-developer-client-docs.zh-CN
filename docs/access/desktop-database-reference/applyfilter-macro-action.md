---
title: ApplyFilter 宏操作
TOCTitle: ApplyFilter macro action
ms:assetid: c63988c4-4506-cc51-98f7-478d1f3fe668
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823130(v=office.15)
ms:contentKeyID: 48547623
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm79035
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: e79ab56778f9429e7f1a985f0f81864ae4363606
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296995"
---
# <a name="applyfilter-macro-action"></a>ApplyFilter 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **ApplyFilter** 操作对表、窗体或报表应用筛选、查询或 SQL WHERE 子句，以便对表、基础表或是窗体或报表查询中的记录进行限制或排序。对于报表，只能在由报表的 **OnOpen** 事件属性所指定的宏中使用此操作。

> [!NOTE]
> [!注释] 只有在应用服务器筛选时，才可以使用该操作以应用 SQL WHERE 子句。服务器筛选不能应用于存储过程记录源。

## <a name="setting"></a>Setting

**ApplyFilter** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Filter Name</p></td>
<td><p>用于对表、窗体或报表中的记录进行限制或排序的筛选或查询的名称。 可以在 "<strong>宏生成器</strong>" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>筛选名称</strong>" 框中输入已作为查询保存的现有查询或筛选器的名称。</p><p><strong>注意</strong>: 使用此操作应用服务器筛选器时, 筛选器名称参数必须为空。</p></td>
</tr>
<tr class="even">
<td><p>Where 条件</p></td>
<td><p>用于限制表、窗体或报表中的记录的有效 SQL WHERE 子句（不含单词 WHERE）或表达式。</p>
<p><b>注意</b>: 在 Where 条件参数表达式中, 表达式的左侧通常包含来自窗体或报表的基础表或查询中的字段名称。 表达式的右侧则通常包含要向此字段应用以对记录进行限制或排序的条件。 例如，条件可以是另一个窗体上某个控件的名称，该控件包含要让第一个窗体中的记录与之匹配的值。 该控件的名称应完全限定，例如：</p>
<p><strong>Forms</strong>!<em>formname</em>!<em>controlname</em>字段名应括在双引号中, 而字符串文本应括在单引号中。 “Where 条件”参数的最大长度为 255 个字符。 如果需要输入更长的 SQL WHERE 子句，请使用 Visual Basic for Applications (VBA) 模块中 <strong>DoCmd</strong> 对象的 <strong>ApplyFilter</strong> 方法。 在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> You can use the Filter Name argument if you have already defined a filter that provides the appropriate data. 也可以直接使用“Where 条件”参数来输入限制条件。 If you use both arguments, Microsoft Office Access 2007 applies the WHERE clause to the results of the filter. 必须使用这两个参数之一，或同时使用它们。

## <a name="remarks"></a>注解

可以对窗体视图或数据表视图中的窗体应用筛选或查询。

所应用的筛选和 WHERE 条件将成为窗体或报表的 **"Filter"** 或 **"ServerFilter"** 属性设置。

对于表和窗体，此操作类似于单击 **"记录"** 菜单上的 **"应用筛选/排序"** 或 **"应用服务器筛选"**。菜单命令会向表或窗体应用最近创建的筛选，而 **ApplyFilter** 操作则应用指定的筛选或查询。

在数据库中，如果在运行 **ApplyFilter** 操作后指向 **"记录"** 菜单上的 **"筛选"** 并单击 **"高级筛选/排序"**，"高级筛选/排序"窗口将显示您使用此操作选择的筛选条件。

要在 Office Access 2007 数据库中删除筛选并显示表或窗体的所有记录，可以使用 **ShowAllRecords** 操作或 **"记录"** 菜单上的 **"取消筛选/排序"** 命令。要在 Microsoft Access 项目 (.adp) 中删除筛选，可以返回到"按窗体服务器筛选"窗口并删除所有的筛选条件，然后在工具栏的 **"记录"** 菜单上单击 **"应用服务器筛选"**，也可以将 **"ServerFilterByForm"** 属性设置为 **"False"**(0)。

在保存表或窗体时，Access 会保存当前在该对象中定义的任何筛选，但不会在下次打开该对象时自动应用筛选（不过，它会自动应用保存该对象之前应用的任何排序）。如果要在首次打开某个窗体时自动应用筛选，请指定一个包含 **ApplyFilter** 操作的宏，或指定一个包含 **DoCmd** 对象的 **ApplyFilter** 方法的事件过程，并将其作为该窗体的 **OnOpen** 事件属性设置。您也可以使用 **OpenForm** 操作、 **OpenReport** 操作或与它们相对应的方法应用筛选。要在首次打开某个表时自动应用筛选，可以使用接连包含 **OpenTable** 操作和 **ApplyFilter** 操作的宏打开该表。

## <a name="example"></a>示例

下面的示例演示如何使用 ApplyFilter 操作在 frmFoods 表单打开时对其进行筛选。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    OpenForm
        Form Name sfrmFoods
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    ApplyFilter
        Filter Name
        Where Condition=[display_name] Link "*cheese*"
        Control Name
```



