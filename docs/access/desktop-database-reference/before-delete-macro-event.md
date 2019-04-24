---
title: Before Delete 宏事件
TOCTitle: Before Delete macro event
ms:assetid: 1a8d3457-5c59-d13e-ada9-6ecd33dfd5b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845672(v=office.15)
ms:contentKeyID: 48543520
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm186077
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2b2a4f978a4af2ba79cab7807f0142d35d7d30c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296911"
---
# <a name="before-delete-macro-event"></a>Before Delete 宏事件

**适用于**：Access 2013、Office 2013

当记录被删除但未提交更改时会发生“删除前”**** 事件。

> [!NOTE]
> ****“删除前”事件仅适用于数据宏。

## <a name="remarks"></a>注解

使用“删除前”**** 事件可以执行您希望在删除记录前发生的任何操作。 “更改前”**** 通常用于执行验证和引发自定义错误消息。

您可以使用以下语法访问要删除的记录中的值:

`[Old].[Field Name]`

例如, 若要访问要删除的记录中的 QuantityInStock 字段的值, 请使用以下语法:

`[Old].[QuantityInStock]`

当“删除前”**** 事件结束时，要删除的记录中包含的值将被永久删除。

您可以使用 **RaiseError** 操作取消“删除前”**** 事件。 在引发错误时, 将放弃**Before Delete**事件中包含的更改。

下表列出了可在**Before Delete**事件中使用的宏命令。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>命令类型</p></th>
<th><p>Command</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>程序流</p></td>
<td><p><a href="comment-macro-statement.md">Comment 宏语句</a></p></td>
</tr>
<tr class="even">
<td><p>程序流</p></td>
<td><p><a href="group-macro-statement.md">Group 宏语句</a></p></td>
</tr>
<tr class="odd">
<td><p>程序流</p></td>
<td><p><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></p></td>
</tr>
<tr class="even">
<td><p>数据块</p></td>
<td><p><a href="lookuprecord-data-block.md">LookupRecord 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="onerror-macro-action.md">OnError 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></p></td>
</tr>
<tr class="even">
<td><p>数据操作</p></td>
<td><p><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></p></td>
</tr>
<tr class="odd">
<td><p>数据操作</p></td>
<td><p><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></p></td>
</tr>
</tbody>
</table>


若要创建可捕获“删除前”**** 事件的数据宏，请执行以下步骤。

1.  打开要捕获其“删除前”**** 事件的表格。

2.  在 "**表**" 选项卡上的 "前期**事件**" 组中, 选择 "**之前删除**"。

