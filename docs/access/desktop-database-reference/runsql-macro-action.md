---
title: RunSQL 宏操作
TOCTitle: RunSQL macro action
ms:assetid: 3692142d-f8a8-e194-0b38-051167f46319
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192476(v=office.15)
ms:contentKeyID: 48544174
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12983
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f3ef598ad50747d99ca884043e03ebfabfef8f63
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308993"
---
# <a name="runsql-macro-action"></a>RunSQL 宏操作

**适用于**：Access 2013、Office 2013

您可以使用**RunSQL**操作来运行 Access 操作查询, 方法是使用相应的 SQL 语句。 还可以运行数据定义查询。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**RunSQL** 操作具有下列参数。

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
<td><p><strong>SQL 语句</strong></p></td>
<td><p>要运行的动作查询或数据定义查询所对应的 SQL 语句。此语句的最大长度为 255 个字符。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用事务</strong></p></td>
<td><p>选择<strong>"是"</strong>将此查询包含在事务中。 如果您不想使用事务处理, 请选择 "<strong>否</strong>"。 默认值为 <strong>"是"</strong>。 如果为此参数选择 "<strong>否</strong>", 则查询可能会运行得更快。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用动作查询可以追加、删除和更新记录并将查询的结果集另存为新表。使用数据定义查询可以创建、更改和删除表，还可以创建和删除索引。使用 **RunSQL** 操作可以从宏中直接执行这些操作，而无需使用存储的查询。

如果需要键入长度超过 255 个字符的 SQL 语句，请改用 Visual Basic for Applications (VBA) 模块中的 **DoCmd** 对象的 **RunSQL** 方法。在 VBA 中，可以键入长达 32,768 个字符的 SQL 语句。

Access 查询实际上是 SQL 语句，这些语句是在您使用查询窗口中的设计网格设计查询时创建的。下表中显示了 Access 动作查询和数据定义查询以及与它们对应的 SQL 语句。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>查询类型</p></th>
<th><p>SQL 语句</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Action</strong></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Append</p></td>
<td><p>INSERT INTO</p></td>
</tr>
<tr class="odd">
<td><p>删除</p></td>
<td><p>DELETE</p></td>
</tr>
<tr class="even">
<td><p>生成表</p></td>
<td><p>选择 .。。了解</p></td>
</tr>
<tr class="odd">
<td><p>Update</p></td>
<td><p>更新</p></td>
</tr>
<tr class="even">
<td><p><strong>数据定义 (特定于 SQL)</strong></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>创建表</p></td>
<td><p>创建表</p></td>
</tr>
<tr class="even">
<td><p>更改表</p></td>
<td><p>ALTER TABLE</p></td>
</tr>
<tr class="odd">
<td><p>删除表</p></td>
<td><p>删除表</p></td>
</tr>
<tr class="even">
<td><p>创建索引</p></td>
<td><p>创建索引</p></td>
</tr>
<tr class="odd">
<td><p>删除索引</p></td>
<td><p>删除索引</p></td>
</tr>
</tbody>
</table>

还可以将 IN 子句与这些语句一起使用，以修改另一个数据库中的数据。

> [!NOTE]
> [!注释] 要从宏中运行选择查询或交叉表查询，请使用 **OpenQuery** 操作的"视图"参数在数据表视图中打开一个现有的选择查询和交叉表查询。还可以用同样的方法运行现有的动作查询和 SQL 特定查询。
