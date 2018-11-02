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
ms.openlocfilehash: a6166f8da8597e5b0672ba0d5fdfdd3745cfd159
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927765"
---
# <a name="openreport-macro-action"></a>OpenReport 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **OpenReport** 操作在设计视图或打印预览中打开报表，或者将报表直接发送到打印机。此外还可以限制要从报表中打印的记录。

## <a name="setting"></a>设置

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
<td><p>要打开的报表的名称。 <strong>宏生成器</strong>窗格的<strong>报告名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有报表。 这是必需参数。 如果在类库数据库中运行包含 OpenReport 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的报表，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p>视图</p></td>
<td><p>打开报表时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“打印”</strong>（立即打印报表）、<strong>“设计”</strong>或<strong>“打印预览”</strong>。默认值为<strong>“打印”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p>Filter Name</p></td>
<td><p>限制报表的记录的筛选器。 您可以输入现有查询或筛选器已保存为查询的名称。 但是，查询必须包含要打开或将它<strong>OutputAllFields</strong>属性设置为<strong>是</strong>报表中的所有字段。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>关键字的有效 SQL WHERE 子句 (不带有单词其中) 或 Access 使用从报表中选择记录的表达式的基础表或查询。 如果选择筛选器名称参数的筛选器，Access 会将此 WHERE 子句于筛选结果。 要打开报表并将其记录限制为由某个窗体控件的值指定的记录，请使用以下表达式：<br />
<strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on form</em><strong>]</strong><br />
<em>Fieldname</em>替换基础表或查询您要打开的报表中字段的名称。 <em>Formname</em>和<em>窗体上的控件名称</em>替换窗体和包含要匹配的报告中的记录的值的窗体上的控件的名称。</p>
<p><b>注意</b>： Where Condition 参数的最大长度为 255 个字符。 如果您需要输入一个更复杂 SQL WHERE 子句多于此，请改用<b>DoCmd</b>对象的<b>OpenReport</b>方法在 Visual Basic for Applications (VBA) 模块。 您可以在 VBA 中输入 SQL WHERE 子句语句的最多为 32,768 个字符。</p>
</td>
</tr>
<tr class="odd">
<td><p>窗口模式</p></td>
<td><p>报表将在其中打开模式。 单击<strong>普通</strong>、<strong>隐藏</strong>、<strong>图标</strong>或<strong>对话框</strong>中<strong>窗口模式</strong>框。 默认值为<strong>Normal</strong>。</p>
<p><b>注意</b>： 某些窗口模式参数设置不适用时使用选项卡式文档。 若要切换到重叠窗口：
<ol>
<li><p>单击 <strong>"选项"</strong>。</p></li>
<li><p>在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</p></li>
<li><p>在<strong>“应用程序选项”</strong>部分中的<strong>“文档窗口选项”</strong>下，单击<strong>“重叠窗口”</strong>。</p></li>
<li><p>单击<strong>确定</strong>，然后关闭并重新打开数据库。</p></li>
</ol>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**视图**参数的**打印**设置打印报表立即使用当前的打印机设置，不显示**打印**对话框的情况。 您还可以使用**OpenReport**操作打开和设置报表，然后使用 PrintOut 操作打印。 例如，您可能想要修改报表或使用**PrintOut**操作来更改打印机设置打印之前。

所应用的筛选和 WHERE 条件将成为报表的 **Filter** 属性设置。

**OpenReport** 操作类似于在导航窗格中双击报表，或是在导航窗格中右键单击报表并选择视图或 **"打印"** 命令。

> [!TIP] 
> - 要在类似的报表中打印几组不同的数据，请使用筛选或 WHERE 子句限制要在报表中打印的记录，再通过编辑该宏来应用不同的筛选或更改“Where 条件”参数。
> 
> - 您可以将报表从导航窗格拖至宏操作行。这会自动创建一个在"报表"视图中打开该报表的 **OpenReport** 操作。

## <a name="example"></a>示例

下面的示例演示如何使用 OpenReport 操作将传递参数筛选报告，因为没有打开它。 **RptChapters**报告通过传递给 SelectedAuthor 参数**cboAuthors**组合框中选定项为指定的作者显示的记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

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
