---
title: OpenReport 宏操作
TOCTitle: OpenReport macro action
ms:assetid: cd35faf2-190d-ac48-cf59-81c1599eb764
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834462(v=office.15)
ms:contentKeyID: 48547758
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm188079
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: cff57a185d226328792bef79072dfc46c6134f98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288348"
---
# <a name="openreport-macro-action"></a>OpenReport 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **OpenReport** 操作在设计视图或打印预览中打开报表，或者将报表直接发送到打印机。此外还可以限制要从报表中打印的记录。

## <a name="setting"></a>Setting

**OpenReport** 操作具有下列参数。

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
<td><p>报表名称</p></td>
<td><p>要打开的报表的名称。 "<strong>宏生成器</strong>" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>报告名称</strong>" 框中显示了当前数据库中的所有报告。 这是一个必选参数。 如果在类库数据库中运行包含 OpenReport 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的报表，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p>View</p></td>
<td><p>打开报表时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“打印”</strong>（立即打印报表）、<strong>“设计”</strong>或<strong>“打印预览”</strong>。默认值为<strong>“打印”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p>筛选名称</p></td>
<td><p>用于限制报表记录的筛选。您可以输入现有查询的名称，也可以输入另存为查询的筛选的名称。但是，该查询必须包括要打开的报表中的所有字段，或必须将其 <strong>OutputAllFields</strong> 属性设置为“是”<strong></strong>。</p></td>
</tr>
<tr class="even">
<td><p>Where 条件</p></td>
<td><p>Access 用于从报表的基础表或查询中选择记录的有效 SQL WHERE 子句（不含单词 WHERE）或表达式。 如果您通过“筛选名称”参数选择筛选，Access 会将此 WHERE 子句应用于筛选的结果。 要打开报表并将其记录限制为由某个窗体控件的值指定的记录，请使用以下表达式：<br />
<strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on form</em><strong>]</strong><br />
将<em>fieldname</em>替换为要打开的报表的基础表或查询中的字段的名称。 将窗体<em>上</em>的<em>formname</em>和 controlname 替换为窗体的名称和窗体上包含您希望报表中的记录匹配的值的控件。</p>
<p><b>注意</b>: Where Condition 参数的最大长度为255个字符。 如果需要输入超过此限制的更复杂的 SQL WHERE 子句，请改用 Visual Basic for Applications (VBA) 模块中 <b>DoCmd</b> 对象的 <b>OpenReport</b> 方法。 在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</p>
</td>
</tr>
<tr class="odd">
<td><p>窗口模式</p></td>
<td><p>打开报表时将使用的模式。 在<strong>窗口模式</strong>框中单击 "<strong>常规</strong>"、"<strong>隐藏</strong>"、"<strong>图标</strong>" 或 "<strong>对话框</strong>"。 默认值为<strong>“普通”</strong>。</p>
<p><b>注意</b>: 使用选项卡式文档时, 某些窗口模式参数设置不适用。 要切换到重叠窗口，请执行下列操作：
<ol>
<li><p>单击 <strong>"选项"</strong>。</p></li>
<li><p>在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</p></li>
<li><p>在<strong>“应用程序选项”</strong>部分中的<strong>“文档窗口选项”</strong>下，单击<strong>“重叠窗口”</strong>。</p></li>
<li><p>单击<strong>"确定</strong>", 然后关闭并重新打开数据库。</p></li>
</ol>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

The **Print** setting for the **View** argument prints the report immediately by using the current printer settings, without bringing up the **Print** dialog box. You can also use the **OpenReport** action to open and set up a report and then use the PrintOut action to print it. For example, you may want to modify the report or use the **PrintOut** action to change the printer settings before you print.

所应用的筛选和 WHERE 条件将成为报表的 **Filter** 属性设置。

**OpenReport** 操作类似于在导航窗格中双击报表，或是在导航窗格中右键单击报表并选择视图或 **"打印"** 命令。

> [!TIP] 
> - To print similar reports for different sets of data, use a filter or a WHERE clause to restrict the records printed in the report. Then edit the macro to apply a different filter or change the Where Condition argument.
> 
> - 您可以将报表从导航窗格拖至宏操作行。这会自动创建一个在"报表"视图中打开该报表的 **OpenReport** 操作。

## <a name="example"></a>示例

下面的示例演示如何使用 OpenReport 操作在打开时传递筛选报表的参数。 **rptChapters**报告通过将**cboAuthors**组合框中选定的项传递给 SelectedAuthor 参数, 来显示指定作者的记录。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    OpenReport
        Report Name rptChapters
        View Report
        Filter Name
        Where Condition
        Window Mode Normal
    
    Parameters
        SelectedAuthor =[cboAuthor]
```
