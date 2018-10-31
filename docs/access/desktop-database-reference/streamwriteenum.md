---
title: StreamWriteEnum （访问桌面数据库参考 （英文）
TOCTitle: StreamWriteEnum
ms:assetid: b4356999-d7a8-abfa-f6a8-6c2dd04b9257
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249861(v=office.15)
ms:contentKeyID: 48547216
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 76286fcd09e5b92f19d8dbf0e8d0419ad4c600df
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861888"
---
# <a name="streamwriteenum"></a>StreamWriteEnum

**适用于**： Access 2013 |Office 2013

用于指定是否将行分隔符追加到写入 [Stream](stream-object-ado.md) 对象的字符串。

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
<td><p><strong>adWriteChar</strong></p></td>
<td><p>0</p></td>
<td><p>默认值。将指定的文本字符串（由 <em>Data</em> 参数指定）写入 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong>adWriteLine</strong></p></td>
<td><p>1</p></td>
<td><p>将文本字符串和行分隔符写入 <strong>Stream</strong> 对象。如果未定义 <a href="lineseparator-property-ado.md">LineSeparator</a> 属性，此常量将返回一个运行时错误。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

