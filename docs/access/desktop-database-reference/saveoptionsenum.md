---
title: SaveOptionsEnum (Access desktop database reference)
TOCTitle: SaveOptionsEnum
ms:assetid: 2a4e4c7a-6331-7270-0514-cc549c721ffd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249053(v=office.15)
ms:contentKeyID: 48543906
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 77a617dc54d8acd145648d926e10cf7c9a3cf252
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314740"
---
# <a name="saveoptionsenum"></a>SaveOptionsEnum

**适用于**：Access 2013、Office 2013

指定当从 [Stream](stream-object-ado.md) 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。

<br/>

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
<td><p>双面</p></td>
<td><p>如果 <em>Filename</em> 参数指定的文件已存在，则使用当前打开的 <strong>Stream</strong> 对象中的数据覆盖该文件。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

这些常量没有 ADO/WFC 等效值。

