---
title: CREATE VIEW 语句 (Microsoft Access SQL)
TOCTitle: CREATE VIEW statement (Microsoft Access SQL)
ms:assetid: ecaabd75-3081-fd35-830d-5a59b0a51922
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836312(v=office.15)
ms:contentKeyID: 48548519
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 73fac5ff9dd1f5cf277b8cb241044af23609b764
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295364"
---
# <a name="create-view-statement-microsoft-access-sql"></a>CREATE VIEW 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

创建新视图。

> [!NOTE]
> Microsoft Access 数据库引擎不支持将 CREATE VIEW 或任何 DDL 语句与非 Microsoft Access 数据库引擎数据库结合使用。

## <a name="syntax"></a>语法

CREATE VIEW *view* \[(*field1*\[, *field2*\[, …\]\])\] AS *selectstatement*

CREATE VIEW 语句包含以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Part</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>view</em></p></td>
<td><p>要创建的视图的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>, <em>field2</em></p></td>
<td><p>
            <em>selectstatement</em> 中指定的字段的对应字段的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>selectstatement</em></p></td>
<td><p>SQL SELECT 语句。 有关详细信息，请参阅 <a href="select-statement-microsoft-access-sql.md">SELECT 语句</a>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

定义视图的 SELECT 语句不能是 [SELECT INTO](select-into-statement-microsoft-access-sql.md) 语句。

定义视图的 SELECT 语句不能包含任何参数。

视图名称不能与现有表的名称相同。

如果 SELECT 语句定义的查询可更新，则视图也可更新。 否则视图为只读。

如果 SELECT 语句定义的查询中有任何两个字段具有相同的名称，则视图定义必须包含一个字段列表，该列表为查询中的每个字段指定唯一名称。

