---
title: StreamReadEnum (Access desktop database reference)
TOCTitle: StreamReadEnum
ms:assetid: 12432c0d-dc2e-10ea-13db-0c07b6ba29bc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248895(v=office.15)
ms:contentKeyID: 48543336
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e4d9c96a7bb34fe0ab3512a316a92e1f7a01ef4b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314719"
---
# <a name="streamreadenum"></a>StreamReadEnum

**适用于**：Access 2013、Office 2013

用于指定应从 [Stream](stream-object-ado.md) 对象读取整个流还是下一行。

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
<td><p><strong>adReadAll</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。读取流中从当前位置向前直到 <a href="eos-property-ado.md">EOS</a> 标记之间的所有字节。这是用于二进制流（<a href="type-property-ado-stream.md">Type 属性 (ADO Stream) </a><strong>adTypeBinary</strong>）的唯一有效的 <strong>StreamReadEnum</strong> 值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adReadLine</strong></p></td>
<td><p>-2</p></td>
<td><p>读取流中的下一行（由 <a href="lineseparator-property-ado.md">LineSeparator</a> 属性指定）。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

这些常量没有 ADO/WFC 等效值。

