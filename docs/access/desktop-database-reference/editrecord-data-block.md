---
title: EditRecord 数据块
TOCTitle: EditRecord data block
ms:assetid: fe9f55eb-d7ed-1914-65a9-fa2fcb332b98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837277(v=office.15)
ms:contentKeyID: 48548940
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 32ddfbbf21e62d5967fa1f2f31bab0222664eb39
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715751"
---
# <a name="editrecord-data-block"></a>EditRecord 数据块

**适用于**： Access 2013、 Office 2013

您可以使用 **EditRecord** 数据块更改现有记录中包含的值。

> [!NOTE]
> [!注释] **EditRecord** 数据块仅适用于数据宏。


## <a name="setting"></a>设置

**EditRecord** 数据块具有以下参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Alias</strong></p></td>
<td><p>一个用于标识要编辑的记录的字符串。如果未指定 <em>Alias</em> 参数，则编辑当前记录。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注释

可在 **EditRecord** 语句之后插入将在提交记录更改之前执行的命令块。以下操作适用于 **EditRecord** 数据块。

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p><a href="comment-macro-statement.md">Comment 宏语句</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="group-macro-statement.md">Group 宏语句</a></p></td>
</tr>
<tr class="even">
<td><p><a href="if-then-else-macro-block.md">如果...然后...Else 宏语句</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="setfield-macro-action.md">SetField 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></p></td>
</tr>
</tbody>
</table>

使用 **SetField** 操作可以指定已编辑记录中某一字段的新值。

可以使用 **If...Then...Else** 语句基于条件来执行操作。

若要取消编辑记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **EditRecord** 数据块。

您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如，使用以下语法引用 AssignedTo 字段的最近创建的记录：

`[LastCreateRecordIdentity].[AssignedTo]`

CreateRecord 数据块只能用于 **[插入后](after-insert-macro-event.md)** 、 **[更新后](after-update-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 数据宏事件。

