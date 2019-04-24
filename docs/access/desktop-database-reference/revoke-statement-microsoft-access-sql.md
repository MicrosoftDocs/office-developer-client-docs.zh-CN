---
title: REVOKE 语句 (Microsoft Access SQL)
TOCTitle: REVOKE statement (Microsoft Access SQL)
ms:assetid: 69399fd6-c4e8-f2e2-e5f4-48ae779323f5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195272(v=office.15)
ms:contentKeyID: 48545409
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277479
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 20122fee617597987940766a076d5f968a87c2d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306529"
---
# <a name="revoke-statement-microsoft-access-sql"></a>REVOKE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

撤消现有用户或组的指定权限。

## <a name="syntax"></a>语法

撤消 {*特权*\[,*特权*, .。。\]} ON {TABLE *table* |object*对象*|

CONTAINTER*容器*} FROM {*authorizationname*\[, *authorizationname*, .。。\]}

REVOKE 语句包含以下部分：

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
<td><p>将被撤消的权限。 使用以下关键字指定权限: SELECT、DELETE、INSERT、UPDATE、DROP、SELECTSECURITY、UPDATESECURITY、DBPASSWORD、UPDATEIDENTITY、CREATE、SELECTSCHEMA、SCHEMA 和 UPDATEOWNER。</p></td>
</tr>
<tr class="even">
<td><p><em>table</em></p></td>
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

