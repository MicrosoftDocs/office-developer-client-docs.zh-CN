---
title: CREATE VIEW 语句 (Microsoft Access SQL)
TOCTitle: CREATE VIEW Statement (Microsoft Access SQL)
ms:assetid: ecaabd75-3081-fd35-830d-5a59b0a51922
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836312(v=office.15)
ms:contentKeyID: 48548519
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 292dddeab15c71fb188a928ac0e491063930214d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466688"
---
# <a name="create-view-statement-microsoft-access-sql"></a>CREATE VIEW 语句 (Microsoft Access SQL)


**适用于**： Access 2013 |Office 2013

创建新视图。


> [!NOTE]
> <P>[!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Access 数据库引擎数据库使用 CREATE VIEW 语句或任何 DDL 语句。</P>



## <a name="syntax"></a>语法

CREATE VIEW*视图* \[(*field1*\[， *field2*\[，...\] \])\]作为*selectstatement*

CREATE VIEW 语句包含以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>部分</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>view</em></p></td>
<td><p>要新建的视图的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>field1</em>、<em>field2</em></p></td>
<td><p><em>selectstatement</em> 中所指定的相应字段的字段名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>selectstatement</em></p></td>
<td><p>SQL SELECT 语句。有关详细信息，请参阅 <a href="select-statement-microsoft-access-sql.md">SELECT 语句</a>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

定义视图的 SELECT 语句不能是 [SELECT INTO](select-into-statement-microsoft-access-sql.md) 语句。

定义视图的 SELECT 语句不能包含任何参数。

视图的名称不能和现有表的名称相同。

如果 SELECT 语句所定义的查询是可更新的，那么视图也是可更新的。否则，视图是只读的。

如果 SELECT 语句定义的查询中有任何两个字段同名，那么视图定义必须包括一个字段列表来为查询中的每个字段指定唯一的名称。

