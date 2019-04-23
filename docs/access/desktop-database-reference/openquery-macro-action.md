---
title: OpenQuery 宏操作
TOCTitle: OpenQuery macro action
ms:assetid: 64bfce73-aeaf-9a78-895c-492e5da43ded
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195094(v=office.15)
ms:contentKeyID: 48545298
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89069
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 3294efe5ea1ab0f82be19f5c64a51287cc4df9b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288341"
---
# <a name="openquery-macro-action"></a>OpenQuery 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **OpenQuery** 操作在数据表视图、设计视图或打印预览中打开选择查询或交叉表查询。此操作运行动作查询。您还可以为查询选择数据输入模式。

> [!NOTE]
> [!注释] 此操作仅适用于 Microsoft Access 数据库环境（.mdb 或 .accdb）。如果使用的是 Microsoft Access 项目环境 (.adp)，请参阅 **OpenView**、 **OpenStoredProcedure** 或 **OpenFunction** 操作。

## <a name="setting"></a>Setting

**OpenQuery** 操作具有下列参数。

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
<td><p><strong>查询名称</strong></p></td>
<td><p>要打开的查询的名称。 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>查询名称</strong>" 框中显示了当前数据库中的所有查询。 这是必需参数。如果在类库数据库中运行包含<strong>OpenQuery</strong>操作的宏, Microsoft Access 将先在该类库数据库中查找具有此名称的查询, 然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>将在其中打开查询的视图。 请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。 默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据模式</strong></p></td>
<td><p>查询的数据输入模式。 这仅适用于在数据表视图中打开的查询。 请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。 默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

If you use **Datasheet** for the **View** argument, Access displays the result set if the query is a select, crosstab, union, or pass-through query whose **ReturnsRecords** property is set to **Yes**; and it runs the query if it is an action, data-definition, or pass-through query whose **ReturnsRecords** property is set to **No**.

**OpenQuery** 操作类似于在导航窗格中双击查询，或在导航窗格中右键单击查询并选择视图。通过此操作可以选择其他选项。

> [!TIP]
> - You can drag a query from the Navigation Pane to a macro action row. This automatically creates an **OpenQuery** action that opens the query in Datasheet view. Switching to Design view while the query is open removes the **Data Mode** argument setting for the query. This setting isn't in effect even if the user returns to Datasheet view.
> - 如果不想显示通常在运行动作查询时出现的系统消息（指示查询为动作查询并显示将受到影响的记录数），则可以使用 **SetWarnings** 操作禁止显示这些消息。

要在 Visual Basic for Applications (VBA) 模块中运行 **OpenQuery** 操作，请使用 **DoCmd** 对象的 **OpenQuery** 方法。

