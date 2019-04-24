---
title: EventStatusEnum (Access desktop database reference)
TOCTitle: EventStatusEnum
ms:assetid: ae1711bc-2af5-04fd-7d8c-222d8afc9d3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249821(v=office.15)
ms:contentKeyID: 48547059
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 654d2a485c9273072d1daa61321e73418a15e969
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293271"
---
# <a name="eventstatusenum"></a>EventStatusEnum

**适用于**：Access 2013、Office 2013

指定事件执行的当前状态。

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
<td><p><strong>adStatusCancel</strong></p></td>
<td><p>4</p></td>
<td><p>请求取消导致事件发生的操作。</p></td>
</tr>
<tr class="even">
<td><p><strong>adStatusCantDeny</strong></p></td>
<td><p>第三章</p></td>
<td><p>指示操作无法请求取消挂起的操作。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adStatusErrorsOccurred</strong></p></td>
<td><p>双面</p></td>
<td><p>指示导致事件发生的操作由于错误而失败。</p></td>
</tr>
<tr class="even">
<td><p><strong>adstatusok;</strong></p></td>
<td><p>1</p></td>
<td><p>指示导致事件发生的操作已成功。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adStatusUnwantedEvent</strong></p></td>
<td><p>5</p></td>
<td><p>在事件方法完成执行之前，阻止进行随后的通知。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效项

包：**com.ms.wfc.data**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdoEnums EventStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums EventStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums EventStatus</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums EventStatus</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums EventStatus</p></td>
</tr>
</tbody>
</table>

