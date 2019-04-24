---
title: GRANT 语句 (Microsoft Access SQL)
TOCTitle: GRANT statement (Microsoft Access SQL)
ms:assetid: 50ae97ae-d5be-57e5-d9da-f3fc42f01d83
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193820(v=office.15)
ms:contentKeyID: 48544800
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277478
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4357099f8bcb9b2308b5cda3543949765b8c3420
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292130"
---
# <a name="grant-statement-microsoft-access-sql"></a>GRANT 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

为现有用户或组授予指定的特权。

## <a name="syntax"></a>语法

授予 {*特权*\[,*特权*, .。。\]} ON {TABLE *table* |object*对象*|

容器*容器*} TO {*authorizationname*\[, *authorizationname*, .。。\]}

GRANT 语句包含以下部分：

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
<td><p><em>小特权</em></p></td>
<td><p>要授予的特权。 使用以下关键字指定权限: SELECT、DELETE、INSERT、UPDATE、DROP、SELECTSECURITY、UPDATESECURITY、DBPASSWORD、UPDATEIDENTITY、CREATE、SELECTSCHEMA、SCHEMA 和 UPDATEOWNER。</p></td>
</tr>
<tr class="even">
<td><p><em>名</em></p></td>
<td><p>任何有效的表名。</p></td>
</tr>
<tr class="odd">
<td><p><em>object</em></p></td>
<td><p>可以包含任何非表对象。 存储查询（视图或过程）就是一个示例。</p></td>
</tr>
<tr class="even">
<td><p><em>箱</em></p></td>
<td><p>有效容器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>authorizationname</em></p></td>
<td><p>用户名或组名。</p></td>
</tr>
</tbody>
</table>

