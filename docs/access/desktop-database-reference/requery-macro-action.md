---
title: Requery 宏操作
TOCTitle: Requery Macro Action
ms:assetid: 6dbdcae5-81b6-9925-4cad-64b178c23060
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195544(v=office.15)
ms:contentKeyID: 48545499
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm30402
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e8e5a25b8770f3542fade53d206ff20400ebf350
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885939"
---
# <a name="requery-macro-action"></a>Requery 宏操作


**适用于**： Access 2013、 Office 2013

可以使用 **Requery** 操作通过重新查询控件的数据源来更新活动数据库对象上指定控件中的数据。如果未指定任何控件，此操作将重新查询对象的数据源本身。使用此操作可以确保活动对象或它的其中一个控件显示的是最新数据。

## <a name="setting"></a>设置

**Requery** 操作具有以下参数。

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
<td><p><strong>控件名称</strong></p></td>
<td><p>要更新的控件的名称。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“控件名称”</strong>框中输入控件名称。只应使用控件的名称，而不是完全限定的标识符（例如，<strong>Forms</strong>!<em>窗体名称</em>!<em>控件名称</em>）。将此参数留空可重新查询活动对象的数据源。如果活动对象是数据表或查询结果集，则必须将此参数留空。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

**Requery** 操作执行下列操作之一：

  - 返回控件或对象所基于的查询。

  - 显示所有新的或更改的记录，并从控件或对象所基于的表中删除所有已删除的记录。


> [!NOTE]
> <P>[!注释] <STRONG>Requery</STRONG> 操作不影响记录指针的位置。</P>



基于查询或表的控件包括：

  - 列表框和组合框。

  - 子窗体/子报表控件。

  - OLE 对象，如图表。

  - 包含域聚合函数的控件，如 **DSum** 。

如果指定的控件并不基于查询或表，此操作将强行对该控件进行重新计算。

如果将**控件名称**参数留空，则**Requery**操作具有对象具有焦点时按 SHIFT + F9 相同的效果。 如果子窗体控件具有焦点，该操作将只重新查询子窗体的数据源（就像按 Shift+F9 一样）。


> [!NOTE]
> <P>[!注释] <STRONG>Requery</STRONG> 操作重新查询控件或对象的数据源。而 <STRONG>RepaintObject</STRONG> 操作重画则指定对象中的控件，但不重新查询数据库或者显示新记录。 <STRONG>ShowAllRecords</STRONG> 操作不仅重新查询活动对象，它还删除所有已应用的筛选，而 <STRONG>Requery</STRONG> 操作不这么做。</P>



如果要重新查询的控件不在活动对象上，则必须在 Visual Basic for Applications (VBA) 模块中使用 **Requery** 方法，而不是使用 **Requery** 操作或者与之对应的 **DoCmd** 对象的 **Requery** 方法。VBA 中的 **Requery** 方法比 **Requery** 操作或 **DoCmd.Requery** 方法更快。此外，在使用 **Requery** 操作或 **DoCmd.Requery** 方法时，Microsoft Access 会关闭查询并从数据库中重新加载它，但在使用 **Requery** 方法时，Access 会重新运行查询，而不关闭并重新加载它。请注意，ActiveX 数据对象 (ADO) **Requery** 方法与 Access **Requery** 方法的工作方式相同。

