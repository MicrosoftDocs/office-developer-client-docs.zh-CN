---
title: CreateRecord 数据块
TOCTitle: CreateRecord data block
ms:assetid: e18f47f8-2aad-9a14-ad63-ab603a4d5b07
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835671(v=office.15)
ms:contentKeyID: 48548263
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 63e189143e77f9fcc42fa8d48c3ebfb2feda6633
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28719812"
---
# <a name="createrecord-data-block"></a>CreateRecord 数据块


**适用于**： Access 2013、 Office 2013

您可以使用 **CreateRecord** 数据块在指定表中创建新记录。

> [!NOTE]
> [!注释] **CreateRecord** 数据块仅适用于数据宏。

## <a name="setting"></a>设置

**DeleteRecord** 数据块具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Create a Record In</strong></p></td>
<td><p>是</p></td>
<td><p>要在其中创建新记录的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Alias</strong></p></td>
<td><p>否</p></td>
<td><p>一个用于标识记录的字符串。 您可以使用记录的别名来标识该记录</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

**CreateRecord** 创建的记录会自动成为当前记录。

**CreateRecord**语句之后，您可以插入提交新记录之前将执行的命令的块。 以下操作适用于 **CreateRecord** 数据块。

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


在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。

可以使用 **If...Then...Else** 语句基于条件来执行操作。

若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。

提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。 例如，使用以下语法引用 AssignedTo 字段的最近创建的记录。

`[LastCreateRecordIdentity].[AssignedTo]`

**CreateRecord** 数据块只能用于 **[插入后](after-insert-macro-event.md)** 、 **[更新后](after-update-macro-event.md)** 和 **[删除后](after-update-macro-event.md)** 数据宏事件。

