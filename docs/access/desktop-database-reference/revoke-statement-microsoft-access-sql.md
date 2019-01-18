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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698447"
---
# <a name="revoke-statement-microsoft-access-sql"></a>REVOKE 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

撤消现有用户或组的指定权限。

## <a name="syntax"></a>语法

REVOKE {*privilege*\[， *privilege*，...\]} ON {表*表*|对象*对象*|

CONTAINTER *container*} FROM {*authorizationname*\[， *authorizationname*，...\]}

REVOKE 语句包含以下部分：

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
<td><p><em>privilege</em></p></td>
<td><p>权限被吊销。 使用以下关键字指定权限： 选择、 删除、 插入、 更新、 投递、 SELECTSECURITY、 UPDATESECURITY、 DBPASSWORD、 UPDATEIDENTITY、 CREATE、 SELECTSCHEMA、 架构和 UPDATEOWNER。</p></td>
</tr>
<tr class="even">
<td><p><em>table</em></p></td>
<td><p>任何有效的表名。</p></td>
</tr>
<tr class="odd">
<td><p><em>object</em></p></td>
<td><p>可以包含任何非表对象。存储查询（视图或过程）就是一个示例。</p></td>
</tr>
<tr class="even">
<td><p><em>container</em></p></td>
<td><p>有效容器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>authorizationname</em></p></td>
<td><p>用户名或组名。</p></td>
</tr>
</tbody>
</table>

