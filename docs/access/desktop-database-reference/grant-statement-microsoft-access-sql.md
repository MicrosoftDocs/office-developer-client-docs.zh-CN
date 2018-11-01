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
ms.openlocfilehash: 7c109d1993d4f092439ae10828ce3143625b4ad6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871953"
---
# <a name="grant-statement-microsoft-access-sql"></a>GRANT 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

为现有用户或组授予指定的特权。

## <a name="syntax"></a>语法

GRANT {*privilege*\[， *privilege*，...\]} ON {表*表*|对象*对象*|

CONTAINER *container* } TO {*authorizationname*\[， *authorizationname*，...\]}

GRANT 语句包含以下部分：

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
<td><p>要授予的权限。 使用以下关键字指定权限： 选择、 删除、 插入、 更新、 投递、 SELECTSECURITY、 UPDATESECURITY、 DBPASSWORD、 UPDATEIDENTITY、 CREATE、 SELECTSCHEMA、 架构和 UPDATEOWNER。</p></td>
</tr>
<tr class="even">
<td><p><em>tablename</em></p></td>
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

