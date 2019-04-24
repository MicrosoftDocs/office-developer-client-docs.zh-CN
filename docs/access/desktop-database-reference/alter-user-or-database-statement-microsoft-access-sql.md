---
title: ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)
TOCTitle: ALTER USER or DATABASE statement (Microsoft Access SQL)
ms:assetid: 86ccd296-5171-97e7-683f-cdaab4bde9ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197012(v=office.15)
ms:contentKeyID: 48546093
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2514ca6403ce70acae9e344d610fbd7b9ba7d73b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297177"
---
# <a name="alter-user-or-database-statement-microsoft-access-sql"></a>ALTER USER 或 DATABASE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

更改现有用户或数据库的密码。

## <a name="syntax"></a>语法

ALTER DATABASE PASSWORD *newpassword oldpassword*

ALTER USER *user* PASSWORD *newpassword oldpassword*

ALTER USER 或 DATABASE 语句包含以下部分：

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
<td><p><em>newpassword</em></p></td>
<td><p>与指定的 <em>user</em> 或 <em>database</em> 名称相关联的新密码。</p></td>
</tr>
<tr class="odd">
<td><p><em>oldpassword</em></p></td>
<td><p>与指定的 <em>user</em> 或 <em>group</em> 名称相关联的现有密码。</p></td>
</tr>
</tbody>
</table>

