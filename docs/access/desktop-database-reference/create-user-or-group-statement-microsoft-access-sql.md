---
title: CREATE USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: CREATE USER or GROUP statement (Microsoft Access SQL)
ms:assetid: 62148ce2-0f81-944e-a1ab-edef990fff9f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194914(v=office.15)
ms:contentKeyID: 48545229
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5b294af16498778eae94b38a7a31b93fd029585e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295378"
---
# <a name="create-user-or-group-statement-microsoft-access-sql"></a>CREATE USER 或 GROUP 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

新建一个或多个用户或组。

## <a name="syntax"></a>语法

### <a name="create-a-user"></a>创建用户

创建用户*用户**密码 pid* \[,*用户**密码 pid*, .。。\]

### <a name="create-a-group"></a>创建组

创建组*组* *pid*\[,*组* *pid*, .。。\]

CREATE USER 或 GROUP 语句包含以下部分：

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
<td><p><em>user</em></p></td>
<td><p>要添加到工作组信息文件中的用户的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>组</em></p></td>
<td><p>要添加到工作组信息文件中的组的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>口令</em></p></td>
<td><p>与指定的 <em>user</em> 名称相关联的密码。</p></td>
</tr>
<tr class="even">
<td><p><em>pid</em></p></td>
<td><p>个人标识。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

*user* 和 *group* 不能同名。

所创建的每个 *user* 或 *group* 必须要有 *password*。

