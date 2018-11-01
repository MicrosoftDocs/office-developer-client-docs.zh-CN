---
title: SeekEnum （访问桌面数据库参考 （英文）
TOCTitle: SeekEnum
ms:assetid: a0574809-db2d-8759-18cc-fb1cf776e8fd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249737(v=office.15)
ms:contentKeyID: 48546706
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 5035853f8896b711687fed9f9651af6665d9d9b6
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875717"
---
# <a name="seekenum"></a>SeekEnum

**适用于**： Access 2013、 Office 2013

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
<td><p>2</p></td>
<td><p>搜寻最后一个等于 <em>KeyValues</em> 的键。</p></td>
</tr>
<tr class="odd">
<td><p>adSeekAfterEQ</p></td>
<td><p>4</p></td>
<td><p>搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之后的键。</p></td>
</tr>
<tr class="even">
<td><p>adSeekAfter</p></td>
<td><p>8</p></td>
<td><p>搜索正好在应出现匹配 <em>KeyValues</em> 的项的位置之后的键。</p></td>
</tr>
<tr class="odd">
<td><p>adSeekBeforeEQ</p></td>
<td><p>16</p></td>
<td><p>搜寻等于 <em>KeyValues</em> 的键或正好在应出现匹配项的位置之前的键。</p></td>
</tr>
<tr class="even">
<td><p>adSeekBefore</p></td>
<td><p>32</p></td>
<td><p>搜寻正好在应出现匹配 <em>KeyValues</em> 的项的位置之前的键。</p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a>ADO/WFC 等效值

包： **com.ms.wfc.data**

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
<td><p>AdoEnums.Seek.FIRSTEQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.Seek.LASTEQ</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.Seek.AFTEREQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.Seek.AFTER</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.Seek.BEFOREEQ</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.Seek.BEFORE</p></td>
</tr>
</tbody>
</table>

