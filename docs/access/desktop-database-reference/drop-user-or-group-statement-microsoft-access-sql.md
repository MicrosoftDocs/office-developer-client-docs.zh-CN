---
title: DROP USER 或 GROUP 语句 (Microsoft Access SQL)
TOCTitle: DROP USER or GROUP statement (Microsoft Access SQL)
ms:assetid: 46bc5916-556b-17df-2f4c-8fd7bbd21ef7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193192(v=office.15)
ms:contentKeyID: 48544575
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 995f935ceea5af3b740215c5a4137e02e7ebb1b2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700834"
---
# <a name="drop-user-or-group-statement-microsoft-access-sql"></a>DROP USER 或 GROUP 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

删除一个或多个现有*用户*或*组*，或者从现有*组*中删除一个或多个现有*用户*。

## <a name="syntax"></a>语法

### <a name="delete-one-or-more-users-or-remove-one-or-more-users-from-a-group"></a>删除一个或多个用户或从组中删除一个或多个用户

DROP USER*用户*\[，*用户*...\] \[从*组*\]

### <a name="delete-one-or-more-groups"></a>删除一个或多个组

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

如果 DROP USER 语句中使用 FROM 关键字，则将从指定的*组*FROM 关键字后面删除每个*用户*语句中列出。 但是，*用户*本身不会被删除。

投递 GROUP 语句将删除指定的*组*(s)。 不会影响*用户**组*(s) 的成员，但不再将已删除*组*(s) 的成员。

