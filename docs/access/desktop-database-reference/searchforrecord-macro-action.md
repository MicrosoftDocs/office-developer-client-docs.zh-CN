---
title: SearchForRecord 宏操作
TOCTitle: SearchForRecord macro action
ms:assetid: a3483c41-adb5-5923-55f4-1a3c4f60cb2f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821023(v=office.15)
ms:contentKeyID: 48546781
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm118713
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: efa763a77250e1d5c617358f31421804c772468b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314642"
---
# <a name="searchforrecord-macro-action"></a>SearchForRecord 宏操作


**适用于**：Access 2013、Office 2013

可以使用 **SearchForRecord** 操作在表、查询、窗体或报表中搜索特定记录。

## <a name="setting"></a>Setting

**SearchForRecord** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>请输入或选择要在其中进行搜索的数据库对象的类型。 可以选择“表”<strong></strong>、“查询”<strong></strong>、“窗体”<strong></strong>或“报表”<strong></strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>请输入或选择包含要搜索的记录的特定对象。下拉列表会显示属于您为“对象类型”<strong></strong>参数选择的类型的所有数据库对象。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Record</strong></p></td>
<td><p>指定搜索操作的起点和方向。</p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Setting</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Previous</strong></p></td>
<td><p>从当前记录往上搜索。</p></td>
</tr>
<tr class="even">
<td><p><strong>Next</strong></p></td>
<td><p>从当前记录往下搜索。</p></td>
</tr>
<tr class="odd">
<td><p><strong>第一</strong></p></td>
<td><p>从第一条记录往下搜索。 这是此参数的默认值。</p></td>
</tr>
<tr class="even">
<td><p><strong>最后一个</strong></p></td>
<td><p>从最后一条记录往上搜索。</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><strong>Where 条件</strong></p></td>
<td><p>使用与 SQL WHERE 子句相同的语法输入搜索条件, 而不是在其中包含单词&quot;where。&quot; For example,</p>
<p>`Description = "Beverages"`</p>
<p>若要创建包含来自窗体上的文本框的值的条件, 必须创建一个表达式, 将条件的第一部分与包含要搜索的值的文本框的名称相连接。 例如，下面的条件将在“说明”字段中搜索名为 frmCategories 的窗体上的名为 txtDescription 的文本框中的值。 请注意, 表达式开头<strong>=</strong>的等号 () 以及文本框引用两侧使用单引号 (<strong>'</strong>) 的情况如下所示:</p>
<p>`="Description = ' " & Forms![frmCategories]![txtDescription] & "'"`</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

- 如果有多条记录符合“Where 条件”**** 参数中的条件，则最终会找到哪一条记录将由下列因素决定：
    
  - **Record 参数设置**有关**Record**参数的详细信息, 请参阅 "设置" 部分中的表。
    
  - **记录的排序顺序**例如, 如果**Record**参数设置为**First**, 则更改记录的排序顺序可能会更改找到的记录。

- The object specified in the **Object Name** argument must be open before this action is run. Otherwise, an error occurs.

- If the criteria in the **Where Condition** argument are not met, no error occurs and the focus remains on the current record.

- When searching for the previous or next record, the search does not "wrap" when it reaches the end of the data. If there are no further records that match the criteria, no error occurs and the focus remains on the current record. To confirm that a match was found, you can enter a condition for the next action, and make the condition the same as the criteria in the **Where Condition** argument.

- 要在 VBA 模块中运行 **SearchForRecord** 操作，请使用 **DoCmd** 对象的 **SearchForRecord** 方法。

- **SearchForRecord** 操作类似于 **[FindRecord](findrecord-macro-action.md)** 操作，但 **SearchForRecord** 的搜索功能更加强大。 **FindRecord** 操作主要用于查找字符串，其功能与 **"查找"** 对话框相同。 **SearchForRecord** 操作使用的条件更像是筛选或 SQL 查询的条件。下面的列表显示了可以通过 **SearchForRecord** 操作执行的一些操作：
    
  - 可以在“Where 条件”**** 参数中使用复杂条件，例如
        
    `Description = "Beverages" and CategoryID = 11`
    
  - 可以引用位于窗体或报表的记录源中但没有在窗体或报表上显示的字段。 在上面的示例中, 说明和类别 id 都必须显示在窗体或报表上, 条件才有效。
    
  - 可以使用逻辑运算符，例如 **\<** 、 **\>** 、 **AND** 、 **OR** 和 **BETWEEN** 。 **FindRecord** 操作仅匹配与被搜索字符串相同、以被搜索的字符串开头或者包含被搜索的字符串的字符串。

## <a name="example"></a>示例

下面的宏先使用 **OpenTable** 操作打开“类别”表，然后使用 **SearchForRecord** 操作找到表中的第一条记录，其中“说明”字段中为“饮料”。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作</p></th>
<th><p>参数</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>OpenTable</strong></p></td>
<td><p><strong>表名称</strong>: 类别<strong>视图</strong>: <strong>DatasheetData 模式</strong>:<strong>编辑</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>SearchForRecord</strong></p></td>
<td><p><strong>对象类型</strong>: <strong>TableObject 名称</strong>: 类别<strong>记录</strong>: <strong>FirstWhere 条件</strong>: Description = &quot;饮料&quot;</p></td>
</tr>
</tbody>
</table>

