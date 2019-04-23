---
title: OpenTable 宏操作
TOCTitle: OpenTable macro action
ms:assetid: 4220ad3a-d064-0034-2806-ec1a447cebac
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192909(v=office.15)
ms:contentKeyID: 48544469
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm149011
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 48a3797c2008f261eda8acc3391b39561fec05f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288292"
---
# <a name="opentable-macro-action"></a>OpenTable 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **OpenTable** 操作在数据表视图、设计视图或打印预览中打开表。您还可以为表选择数据输入模式。

## <a name="setting"></a>Setting

**OpenTable** 操作具有下列参数。

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
<td><p><strong>表名称</strong></p></td>
<td><p>要打开的表的名称。 “宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“表名称”</strong>框会显示当前数据库中的所有表。 这是一个必选参数。 如果在类库数据库中运行包含 <strong>OpenTable</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的表，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>View</strong></p></td>
<td><p>打开表时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据模式</strong></p></td>
<td><p>表的数据输入模式。此参数仅适用于在数据表视图中打开的表。请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注解

此操作类似于在导航窗格中双击表，或在导航窗格中右键单击表并选择视图。

> [!TIP]
> [!提示] 您可以将表从导航窗格拖至某个宏操作行。这会自动创建在数据表视图中打开该表的 **OpenTable** 操作。

要在 Visual Basic for Applications (VBA) 模块中运行 **OpenTable** 操作，请使用 **DoCmd** 对象的 **OpenTable** 方法。

