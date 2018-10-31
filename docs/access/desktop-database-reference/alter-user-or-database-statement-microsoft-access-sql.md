---
title: ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)
TOCTitle: ALTER USER or DATABASE statement (Microsoft Access SQL)
ms:assetid: 86ccd296-5171-97e7-683f-cdaab4bde9ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197012(v=office.15)
ms:contentKeyID: 48546093
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: ad03607b6452da016bad09fd33561bd811a2a16d
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862609"
---
# <a name="alter-user-or-database-statement-microsoft-access-sql"></a>ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)

**适用于**： Access 2013 |Office 2013

更改现有用户或数据库的密码。

## <a name="syntax"></a>语法

更改数据库密码*newpassword 旧密码*

ALTER USER*用户*密码*newpassword 旧密码*

ALTER USER 或 DATABASE 语句包含以下部分：

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
<td><p><em>newpassword</em></p></td>
<td><p>与指定的 <em>user</em> 或 <em>database</em> 名称相关联的新密码。</p></td>
</tr>
<tr class="odd">
<td><p><em>oldpassword</em></p></td>
<td><p>与指定的 <em>user</em> 或 <em>group</em> 名称相关联的现有密码。</p></td>
</tr>
</tbody>
</table>

