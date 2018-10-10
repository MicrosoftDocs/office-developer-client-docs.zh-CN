---
title: ADD USER 语句 (Microsoft Access SQL)
TOCTitle: ADD USER Statement (Microsoft Access SQL)
ms:assetid: 1feb631f-cb8c-14ae-6214-276f1faf1a55
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845862(v=office.15)
ms:contentKeyID: 48543652
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ba08ab3104fa08780e8affa310b52a65f67d8831
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467322"
---
# <a name="add-user-statement-microsoft-access-sql"></a>ADD USER 语句 (Microsoft Access SQL)

**适用于**： Access 2013 |Office 2013

将现有*用户*添加到现有*组*中。

## <a name="syntax"></a>语法

添加用户*用户*\[，*用户*...\]到*组*

ADD USER 语句包含以下部分：

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
</tbody>
</table>


## <a name="remarks"></a>注解

只要*用户*被添加到*组*中，这个*用户*就拥有已授予该*组*的所有权限。

