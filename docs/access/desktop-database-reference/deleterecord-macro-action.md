---
title: DeleteRecord 宏操作
TOCTitle: DeleteRecord macro action
ms:assetid: c656a72c-c037-76a5-dc07-f6eccb6590dd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823132(v=office.15)
ms:contentKeyID: 48547624
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8fb20068052972696b09ea0d2165b344e97ea922
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294013"
---
# <a name="deleterecord-macro-action"></a>DeleteRecord 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **DeleteRecord** 操作删除记录。

## <a name="setting"></a>Setting

**DeleteRecord** 数据块具有以下参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Record Alias</strong></p></td>
<td><p>一个用于标识要删除的记录的字符串。 如果未指定 <em>Alias</em> 参数，则会删除当前记录。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注解

您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。 例如, 使用以下语法来引用最近创建的记录:

`[LastCreateRecordIdentity]`

