---
title: StreamOpenOptionsEnum
TOCTitle: StreamOpenOptionsEnum
ms:assetid: d4bbd6be-41f1-cdf2-9d8f-b77ce83fb88e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250069(v=office.15)
ms:contentKeyID: 48547951
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7de4acb6278bb90b893eb290065c4c31967464d1
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884077"
---
# <a name="streamopenoptionsenum"></a>StreamOpenOptionsEnum


**适用于**： Access 2013、 Office 2013

用于指定打开 [Stream](stream-object-ado.md) 对象的选项。可以使用 OR 运算符来组合使用这些值。

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
<td><p><strong>adOpenStreamAsync</strong></p></td>
<td><p>1</p></td>
<td><p>以异步模式打开 <strong>Stream</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenStreamFromRecord</strong></p></td>
<td><p>4</p></td>
<td><p>将 <em>Source</em> 参数的内容标识为某个已打开的 <a href="record-object-ado.md">Record</a> 对象。默认行为是将 <em>Source</em> 视为直接指向树结构中的某个节点的 URL。与该节点关联的默认流已打开。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenStreamUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。指定使用默认选项打开 <strong>Stream</strong> 对象。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

