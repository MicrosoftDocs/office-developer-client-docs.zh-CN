---
title: Requery 宏操作
TOCTitle: Requery macro action
ms:assetid: 6dbdcae5-81b6-9925-4cad-64b178c23060
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195544(v=office.15)
ms:contentKeyID: 48545499
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm30402
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 8b90af8d1cda073ffa37022bb5db5e8cf8e3b978
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306704"
---
# <a name="requery-macro-action"></a>Requery 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **Requery** 操作通过重新查询控件的数据源来更新活动数据库对象上指定控件中的数据。如果未指定任何控件，此操作将重新查询对象的数据源本身。使用此操作可以确保活动对象或它的其中一个控件显示的是最新数据。

## <a name="setting"></a>Setting

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


## <a name="remarks"></a>注解

**Requery** 操作执行下列操作之一：

- 返回控件或对象所基于的查询。

- 显示所有新的或更改的记录，并从控件或对象所基于的表中删除所有已删除的记录。

> [!NOTE]
> **Requery** 操作不影响记录指针的位置。

基于查询或表的控件包括：

- 列表框和组合框。

- 子窗体控件。

- OLE 对象，如图表。

- 包含域聚合函数的控件，如 **DSum**。

如果指定的控件并不基于查询或表，此操作将强行对该控件进行重新计算。

If you leave the **Control Name** argument blank, the **Requery** action has the same effect as pressing SHIFT+F9 when the object has the focus. If a subform control has the focus, this action requeries only the source of the subform (just as pressing SHIFT+F9 does).

> [!NOTE]
> [!注释] **Requery** 操作重新查询控件或对象的数据源。而 **RepaintObject** 操作重画则指定对象中的控件，但不重新查询数据库或者显示新记录。 **ShowAllRecords** 操作不仅重新查询活动对象，它还删除所有已应用的筛选，而 **Requery** 操作不这么做。

如果要重新查询的控件不在活动对象上，则必须在 Visual Basic for Applications (VBA) 模块中使用 **Requery** 方法，而不是使用 **Requery** 操作或者与之对应的 **DoCmd** 对象的 **Requery** 方法。 VBA 中的 **Requery** 方法比 **Requery** 操作或 **DoCmd.Requery** 方法更快。 此外，在使用 **Requery** 操作或 **DoCmd.Requery** 方法时，Microsoft Access 会关闭查询并从数据库中重新加载它，但在使用 **Requery** 方法时，Access 会重新运行查询，而不关闭并重新加载它。 请注意, ActiveX 数据对象 (ADO) **Requery**方法的工作方式与 Access **Requery**方法的工作方式相同。

