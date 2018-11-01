---
title: SearchForRecord 宏操作
TOCTitle: SearchForRecord Macro Action
ms:assetid: a3483c41-adb5-5923-55f4-1a3c4f60cb2f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821023(v=office.15)
ms:contentKeyID: 48546781
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm118713
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9bb498771e5a1ac3a8e6eb19b3b1ec2886867214
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876489"
---
# <a name="searchforrecord-macro-action"></a>SearchForRecord 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **SearchForRecord** 操作在表、查询、窗体或报表中搜索特定记录。

## <a name="setting"></a>设置

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
<td><p>输入或选择要搜索中的数据库对象的类型。 您可以选择<strong>表</strong>、<strong>查询</strong>、<strong>窗体</strong>或<strong>报表</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>输入或选择包含要搜索的记录的特定对象。 下拉列表显示所选的<strong>对象类型</strong>参数类型的所有数据库对象。</p></td>
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
<th><p>设置</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Previous</strong></p></td>
<td><p>从当前记录往上搜索。</p></td>
</tr>
<tr class="even">
<td><p><strong>下一步</strong></p></td>
<td><p>从当前记录往下搜索。</p></td>
</tr>
<tr class="odd">
<td><p><strong>第一</strong></p></td>
<td><p>从第一条记录往下搜索。这是此参数的默认值。</p></td>
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
<td><p>输入作为 SQL WHERE 子句，只是不 word 使用相同的语法的搜索条件&quot;其中&quot;。 例如，</p>
<p>`Description = "Beverages"`</p>
<p>若要创建包含中窗体上的文本框的值的条件，必须创建组合条件的第一部分包含要搜索的值的文本框同名的表达式。 例如，以下条件将名为 txtDescription 名为 frmCategories 窗体上的文本框中搜索说明字段值。 请注意等号 (<strong>=</strong>) 的表达式，并使用单引号 （<strong>'</strong>） 在文本框引用任意一侧开头：</p>
<p>`="Description = ' " & Forms![frmCategories]![txtDescription] & "'"`</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

- 在多个记录与**Where Condition**参数中的条件相匹配的情况下，以下因素将确定找到哪个记录：
    
  - **Record 参数设置**请参阅有关**记录**参数的详细信息设置部分中的表。
    
  - **记录的排序顺序**例如，如果**记录**参数设置为**第一个**，更改的记录的排序顺序可能会更改找到哪个记录。

- 在运行此操作之前，必须打开**对象名称**参数中指定的对象。 否则，就会出错。

- 如果不满足**Where Condition**参数中的条件，不会发生错误，焦点仍保留在当前记录。

- 搜索时的上一个或下一条记录，搜索不"换行"时到达数据的结尾。 如果没有进一步记录符合条件，不会发生错误，焦点仍保留在当前记录。 若要确认已找到匹配项，可以为下一个操作中，输入一个条件和**Where Condition**参数中的条件相同使该条件。

- 要在 VBA 模块中运行 **SearchForRecord** 操作，请使用 **DoCmd** 对象的 **SearchForRecord** 方法。

- **SearchForRecord** 操作类似于 **[FindRecord](findrecord-macro-action.md)** 操作，但 **SearchForRecord** 的搜索功能更加强大。 **FindRecord** 操作主要用于查找字符串，其功能与 **"查找"** 对话框相同。 **SearchForRecord** 操作使用的条件更像是筛选或 SQL 查询的条件。下面的列表显示了可以通过 **SearchForRecord** 操作执行的一些操作：
    
  - 您可以使用复杂条件中的**Where Condition**参数如
        
    `Description = "Beverages" and CategoryID = 11`
    
  - 可以引用位于窗体或报表的记录源中但没有在窗体或报表上显示的字段。 在上述示例中，说明和 CategoryID 都不必须显示在窗体或报表的条件来处理。
    
  - 可以使用逻辑运算符，例如 **\<** 、 **\>** 、 **AND** 、 **OR** 和 **BETWEEN** 。 **FindRecord** 操作仅匹配与被搜索字符串相同、以被搜索的字符串开头或者包含被搜索的字符串的字符串。

## <a name="example"></a>示例

下面的宏先使用 **OpenTable** 操作打开"类别"表，然后使用 **SearchForRecord** 操作找到表中的第一条记录，其中"说明"字段中为"饮料"。

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
<td><p><strong>表名称</strong>： 类别<strong>视图</strong>： <strong>DatasheetData 模式</strong>：<strong>编辑</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>SearchForRecord</strong></p></td>
<td><p><strong>对象类型</strong>： <strong>TableObject 名称</strong>： 类别<strong>记录</strong>： <strong>FirstWhere 条件</strong>： 说明 =&quot;饮料&quot;</p></td>
</tr>
</tbody>
</table>

