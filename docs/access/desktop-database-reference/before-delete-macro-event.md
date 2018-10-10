---
title: “删除前”宏事件
TOCTitle: Before Delete Macro Event
ms:assetid: 1a8d3457-5c59-d13e-ada9-6ecd33dfd5b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845672(v=office.15)
ms:contentKeyID: 48543520
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm186077
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 7863f8500a81014f3c70b5547fb363c46803f4f1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467775"
---
# <a name="before-delete-macro-event"></a>“删除前”宏事件

**适用于**： Access 2013 |Office 2013

当记录被删除，但未提交更改时会发生的**删除前**事件。

> [!NOTE]
> **删除前**事件仅适用于数据宏。

## <a name="remarks"></a>说明

删除使用的**删除前**事件执行所需记录之前，需要进行任何操作。 **Before Change**常用来执行验证并将引发自定义错误消息。

您可以访问中使用以下语法删除的记录的值：

`[Old].[Field Name]`

例如，若要访问要删除的记录中 QuantityInStock 字段的值，请使用以下语法：

`[Old].[QuantityInStock]`

在**删除前**事件结束时，包含要删除的记录中的值将被永久删除。

您可以通过使用**RaiseError**操作取消的**删除前**事件。 引发错误时，将丢弃的**删除前**事件中包含的更改。

下表列出了可在**删除前**事件中使用的宏命令。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>命令类型</p></th>
<th><p>命令</p></th>
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
<td><p><a href="stopmacro-macro-action.md">StopMacro Macro Action</a></p></td>
</tr>
</tbody>
</table>


若要创建可捕获**删除前**事件的数据宏，请使用以下步骤。

1.  打开要为其捕获**删除前**事件的表格。

2.  在**表**选项卡中的**前期事件**组中，选择**删除前**。

