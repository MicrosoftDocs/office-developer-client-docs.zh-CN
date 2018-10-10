---
title: SaveOptionsEnum （访问桌面数据库参考 （英文）
TOCTitle: SaveOptionsEnum
ms:assetid: 2a4e4c7a-6331-7270-0514-cc549c721ffd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249053(v=office.15)
ms:contentKeyID: 48543906
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 68526eca205fb41dd2789ec187514d0f9b11e35f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466437"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum


**适用于**： Access 2013 |Office 2013

指定当从 [Stream](stream-object-ado.md) 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adSaveCreateNotExist</strong></p></td>
<td><p>1</p></td>
<td><p>默认值。指示如果 <em>FileName</em> 参数指定的文件不存在，则创建一个新文件。</p></td>
</tr>
<tr class="even">
<td><p><strong>adSaveCreateOverWrite</strong></p></td>
<td><p>2</p></td>
<td><p>如果 <em>Filename</em> 参数指定的文件已存在，则使用当前打开的 <strong>Stream</strong> 对象中的数据覆盖该文件。</p></td>
</tr>
</tbody>
</table>


**ADO/WFC 等效值**

这些常量没有 ADO/WFC 等效值。

