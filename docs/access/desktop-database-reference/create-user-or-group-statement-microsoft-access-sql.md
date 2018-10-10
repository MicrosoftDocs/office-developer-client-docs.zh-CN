---
title: CREATE USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: CREATE USER or GROUP Statement (Microsoft Access SQL)
ms:assetid: 62148ce2-0f81-944e-a1ab-edef990fff9f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194914(v=office.15)
ms:contentKeyID: 48545229
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dce5b9a6894eb1e09a0307b389207baefae6aa58
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467752"
---
# <a name="create-user-or-group-statement-microsoft-access-sql"></a>CREATE USER 或 GROUP 语句 (Microsoft Access SQL)


**适用于**： Access 2013 |Office 2013

新建一个或多个用户或组。

## <a name="syntax"></a>语法

创建用户：

CREATE USER *user* *密码 pid* \[，*用户**密码 pid*，...\]

创建组：

创建组*组* *pid*\[，*组* *pid*，...\]

CREATE USER 或 GROUP 语句包含以下部分：

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
<td><p><em>用户</em></p></td>
<td><p>要添加到工作组信息文件中的用户的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>组</em></p></td>
<td><p>要添加到工作组信息文件中的组的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>password</em></p></td>
<td><p>与指定的 <em>user</em> 名称相关联的密码。</p></td>
</tr>
<tr class="even">
<td><p><em>pid</em></p></td>
<td><p>个人标识。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

*用户*和*组*不能具有相同的名称。

*密码*，则需要为每个*用户*或*组*的创建。

