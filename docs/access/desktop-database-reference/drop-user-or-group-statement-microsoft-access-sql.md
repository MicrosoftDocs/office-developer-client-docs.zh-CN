---
title: DROP USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: DROP USER or GROUP Statement (Microsoft Access SQL)
ms:assetid: 46bc5916-556b-17df-2f4c-8fd7bbd21ef7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193192(v=office.15)
ms:contentKeyID: 48544575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a5cf75de06c13e2452e5f33b8355b7fb480d8a3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466043"
---
# <a name="drop-user-or-group-statement-microsoft-access-sql"></a>DROP USER 或 GROUP 语句 (Microsoft Access SQL)


**适用于**： Access 2013 |Office 2013

删除一个或多个现有*用户*或*组*，或者从现有*组*中删除一个或多个现有的*用户*。

## <a name="syntax"></a>语法

删除一个或多个*用户*，或者从*组*中删除一个或多个*用户*：

DROP USER*用户*\[，*用户*...\] \[从*组*\]

删除一个或多个*组*：

投递组*组*\[，*组*中，...\]

DROP USER 或 GROUP 语句包含以下部分：

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
<td><p>要从工作组信息文件中删除的用户的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>组</em></p></td>
<td><p>要从工作组信息文件中删除的组的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果在 DROP USER 语句中使用了 FROM 关键字，那么在该语句中列出的每个*用户*都将从 FROM 关键字后面所指定的*组*中删除。然而，*用户*自身不会被删除。

DROP GROUP 语句将删除指定的*组*。属于该*组*的*用户*不会受到影响，但他们将不再是已删除的*组*的成员。

