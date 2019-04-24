---
title: SeekEnum (Access desktop database reference)
TOCTitle: SeekEnum
ms:assetid: a0574809-db2d-8759-18cc-fb1cf776e8fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249737(v=office.15)
ms:contentKeyID: 48546706
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2f8334cbfc8e0f6a362a36e03984739d1d52b6f6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314656"
---
# <a name="seekenum"></a>SeekEnum

**适用于**：Access 2013、Office 2013

用于指定要执行的 [Seek 方法 (ADO)](seek-method-ado.md) 类型。

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
<td><p>adSeekFirstEQ</p></td>
<td><p>1</p></td>
<td><p>搜寻第一个等于 <em>KeyValues</em> 的键。</p></td>
</tr>
<tr class="even">
<td><p>adSeekLastEQ</p></td>
<td><p>双面</p></td>
<td><p>搜寻最后一个等于 <em>KeyValues</em> 的键。</p></td>
</tr>
<tr class="odd">
<td><p>adSeekAfterEQ</p></td>
<td><p>4</p></td>
<td><p>搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之后的键。</p></td>
</tr>
<tr class="even">
<td><p>adSeekAfter</p></td>
<td><p>utf-8</p></td>
<td><p>搜索正好在应出现匹配 <em>KeyValues</em> 的项的位置之后的键。</p></td>
</tr>
<tr class="odd">
<td><p>adSeekBeforeEQ</p></td>
<td><p>位</p></td>
<td><p>搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之前的键。</p></td>
</tr>
<tr class="even">
<td><p>adSeekBefore</p></td>
<td><p>32</p></td>
<td><p>搜寻正好在应出现匹配 <em>KeyValues</em> 的项的位置之前的键。</p></td>
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
<td><p>AdoEnums。 FIRSTEQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums。 LASTEQ</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums。 AFTEREQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums。</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums。 BEFOREEQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums。</p></td>
</tr>
</tbody>
</table>

