---
title: RecordOpenOptionsEnum
TOCTitle: RecordOpenOptionsEnum
ms:assetid: 44a69719-0789-a084-fb96-21468e270205
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249207(v=office.15)
ms:contentKeyID: 48544534
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4c39d9ca7da2955343e38c67628c9c603a2c256b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25869804"
---
# <a name="recordopenoptionsenum"></a>RecordOpenOptionsEnum


**适用于**： Access 2013、 Office 2013

用于指定打开 [Record](record-object-ado.md) 的选项。可以通过 OR 来组合使用这些值。

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
<td><p><strong>adDelayFetchFields</strong></p></td>
<td><p>0x8000</p></td>
<td><p>向提供程序指示：最初不需要检索与 <strong>Record</strong> 关联的字段，而是可以在第一次尝试访问字段时进行检索。缺少此标志时指示执行默认行为，即检索所有 <strong>Record</strong> 对象字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>adDelayFetchStream</strong></p></td>
<td><p>0x4000</p></td>
<td><p>向提供程序指示：最初不需要检索与 <strong>Record</strong> 关联的默认流。缺少此标志时指示执行默认行为，即检索与 <strong>Record</strong> 对象关联的默认流。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenAsync</strong></p></td>
<td><p>0x1000</p></td>
<td><p>指示 <strong>Record</strong> 对象以异步模式打开。</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenExecuteCommand</strong></p></td>
<td><p>0x10000</p></td>
<td><p>指示源字符串包含应执行的命令文本。此值与 <strong>Recordset.Open</strong> 上的 <strong>adCmdText</strong> 选项等同。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adOpenRecordUnspecified</strong></p></td>
<td><p>-1</p></td>
<td><p>默认值。指示未指定选项。</p></td>
</tr>
<tr class="even">
<td><p><strong>adOpenOutput</strong></p></td>
<td><p>0x800000</p></td>
<td><p>指示如果源指向的节点包含可执行脚本（如 .ASP 页），则打开的 <strong>Record</strong> 将包含执行后的脚本的结果。此值仅对于非集合记录有效。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

这些常量没有 ADO/WFC 等效值。

