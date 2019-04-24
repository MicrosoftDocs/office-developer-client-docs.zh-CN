---
title: ForEachRecord 数据块
TOCTitle: ForEachRecord data block
ms:assetid: be369196-230e-1f92-e36b-667048eef2be
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822743(v=office.15)
ms:contentKeyID: 48547455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 84ab685b946e390645027790e5b1402561527ab6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292326"
---
# <a name="foreachrecord-data-block"></a>ForEachRecord 数据块

**适用于**：Access 2013、Office 2013

**ForEachRecord**数据块为域中的每条记录重复一组语句。

> [!NOTE]
> **ForEachRecord** 数据块仅适用于数据宏。

## <a name="setting"></a>Setting

**ForEachRecord** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>实时</strong></p></td>
<td><p>是</p></td>
<td><p>一个用于标识要对其执行操作的记录域的字符串。 <em>In</em>参数可以包含表、选择查询或 SQL 语句的名称。</p><p><strong>注意</strong>: 指定的域不能包含存储在链接表或 ODBC 数据源中的数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>Where 条件</strong></p></td>
<td><p>否</p></td>
<td><p>一个字符串表达式, 用于限制要对其执行<strong>ForEachRecord</strong>数据块的数据的范围。 例如，条件通常相当于 SQL 表达式中的 WHERE 子句（无单词 WHERE）。 如果省略条件, 则<strong>ForEachRecord</strong>数据块在由<em>In</em>参数指定的整个域上运行。 条件中包括的所有字段还必须是 <em>In</em> 中的字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Alias</strong></p></td>
<td><p>否</p></td>
<td><p>为<em>In</em>参数指定的域提供备用名称的字符串。 通常用于缩短后续引用的表名称, 以防止可能的不明确引用。如果未指定<em>alias</em> , 则表或查询名称将用作别名。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **[ExitForEachRecord](exitforeachrecord-macro-action.md)** 操作可立即退出 **ForEachRecord** 数据块。

