---
title: ResyncEnum (Access desktop database reference)
TOCTitle: ResyncEnum
ms:assetid: 3d38b77b-6afe-e6a0-1a05-7c7ffc19edef
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249164(v=office.15)
ms:contentKeyID: 48544337
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ff09d69a9cf36246b3367202531a011c4e1aba12
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306543"
---
# <a name="resyncenum"></a>ResyncEnum

**适用于**：Access 2013、Office 2013

指定是否通过调用 [Resync](resync-method-ado.md) 来覆盖基础值。

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
<td><p><strong>adResyncAllValues</strong></p></td>
<td><p>双面</p></td>
<td><p>默认值。覆盖数据，且取消挂起更改。</p></td>
</tr>
<tr class="even">
<td><p><strong>adResyncUnderlyingValues</strong></p></td>
<td><p>1</p></td>
<td><p>不覆盖数据，且不取消挂起更改。</p></td>
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
<td><p>AdoEnums ALLVALUES</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums UNDERLYINGVALUES</p></td>
</tr>
</tbody>
</table>

