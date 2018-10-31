---
title: ADD USER 语句 (Microsoft Access SQL)
TOCTitle: ADD USER statement (Microsoft Access SQL)
ms:assetid: 1feb631f-cb8c-14ae-6214-276f1faf1a55
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845862(v=office.15)
ms:contentKeyID: 48543652
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 80e3a8fe62cf077accfc18a30e188898fb279d1d
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862287"
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

*用户*被添加到*组*后，*用户*将具有所有已向*组*授予的权限。

