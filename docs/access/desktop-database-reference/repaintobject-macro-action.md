---
title: RepaintObject 宏操作
TOCTitle: RepaintObject macro action
ms:assetid: e8fa7d0b-578c-5071-2bd5-b772b48637a5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836055(v=office.15)
ms:contentKeyID: 48548431
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm195788
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a2ef6c5f38064ae3253cd7e0e58732f63294ceb3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306683"
---
# <a name="repaintobject-macro-action"></a>RepaintObject 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **RepaintObject** 操作完成指定数据库对象或活动数据库对象（如果未指定数据库对象）的所有尚未完成的屏幕更新。这类更新包括对象的控件的所有尚未完成的重新计算。

## <a name="setting"></a>Setting

**RepaintObject** 操作具有下列参数。

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
<td><p>要重画的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。如果将此参数留空，则会选择活动对象。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要重画的对象的名称。<strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。如果将“对象类型”<strong></strong>参数留空，则也要将此参数留空。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

Microsoft Access 需等到完成其他尚未完成的任务后才完成尚未完成的屏幕更新。利用此操作，可以立即强制重画指定对象中的控件。在下列情况下，可以使用此操作：

- 使用 **SetValue** 操作更改很多控件中的值时。Access 可能不会立刻显示所做的更改，尤其是其他控件（如计算控件）依靠更改的控件中的值时更是如此。

- 想要确保您正在查看的窗体显示其所有控件中的数据时。例如，在您打开一个窗体后，包含 OLE 对象的控件不会立即显示它们的数据。

> [!NOTE]
> - 此操作不会导致对数据库的重新查询，因此它不会显示新的或更改过的记录，也不会从对象的基础表或查询中删除已删除的对象。使用 **Requery** 操作可以重新查询对象的数据源或对象的控件之一。使用 **ShowAllRecords** 操作可以显示最新记录并删除所有已经应用的筛选。
> - **RepaintObject** 操作的效果不同于单击 **"开始"** 选项卡上 **"记录"** 组中的 **"刷新"**，后一种操作会显示您或其他用户已对窗体和数据表中当前显示的记录所做的所有更改。

要在 Visual Basic for Applications (VBA) 模块中运行 **RepaintObject** 操作，请使用 **DoCmd** 对象的 **RepaintObject** 方法。

