---
title: CompareEnum (Access desktop database reference)
TOCTitle: CompareEnum
ms:assetid: 7ac84af6-4f8b-4d1f-7eb3-a015b8b60bc6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249509(v=office.15)
ms:contentKeyID: 48545801
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cd120f726a51c884d063bb03f6d6864ea2d48344
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296064"
---
# <a name="compareenum"></a>CompareEnum

**适用于**：Access 2013、Office 2013

指定通过记录书签表示的两个记录的相对位置。

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
<td><p><strong>adCompareEqual</strong></p></td>
<td><p>1</p></td>
<td><p>指示书签相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCompareGreaterThan</strong></p></td>
<td><p>双面</p></td>
<td><p>指示第一个书签在第二个书签之后。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCompareLessThan</strong></p></td>
<td><p>0</p></td>
<td><p>指示第一个书签在第二个书签之前。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCompareNotComparable</strong></p></td>
<td><p>4</p></td>
<td><p>指示无法比较书签。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adCompareNotEqual</strong></p></td>
<td><p>第三章</p></td>
<td><p>指示书签不相同或者未排序。</p></td>
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
<td><p>AdoEnums (比较) 相等</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. GREATERTHAN</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. LESSTHAN</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums. NOTCOMPARABLE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums. NOTEQUAL</p></td>
</tr>
</tbody>
</table>

