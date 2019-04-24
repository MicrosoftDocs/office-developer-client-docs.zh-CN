---
title: FieldAttributeEnum (Access desktop database reference)
TOCTitle: FieldAttributeEnum
ms:assetid: 2d3a541e-a437-6108-ab0e-90c7884b3df7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249071(v=office.15)
ms:contentKeyID: 48543967
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 079c79af3d15a6a5864a7db7f8334393258cfd42
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292599"
---
# <a name="fieldattributeenum"></a>FieldAttributeEnum

**适用于**：Access 2013、Office 2013

指定 [Field](field-object-ado.md) 对象的一个或多个属性。

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
<td><p><strong>adFldCacheDeferred</strong></p></td>
<td><p>0x1000</p></td>
<td><p>指示提供程序缓存字段值，且随后的读取从缓存中完成。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldFixed</strong></p></td>
<td><p>0x10</p></td>
<td><p>指示字段包含固定长度的数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldIsChapter</strong></p></td>
<td><p>0x2000</p></td>
<td><p>指示字段包含章节值，此值指定与该父字段相关的特定子记录集。通常，章节字段用于数据定形或筛选器。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldIsCollection</strong></p></td>
<td><p>0x40000</p></td>
<td><p>指示字段指定由记录表示的资源是其他资源的集合（如文件夹），而不是一个简单资源（如文本文件）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldIsDefaultStream</strong></p></td>
<td><p>0x20000</p></td>
<td><p>指示字段包含由记录表示的资源的默认流。 例如, 默认流可以是网站上的根文件夹的 HTML 内容, 当指定根 URL 时, 将自动提供该内容。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldIsNullable</strong></p></td>
<td><p>0x20</p></td>
<td><p>指示字段接受空值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldIsRowURL</strong></p></td>
<td><p>0x10000</p></td>
<td><p>指示字段包含通过由记录表示的数据源来命名资源的 URL。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldLong</strong></p></td>
<td><p>0x80</p></td>
<td><p>指示字段是长二进制字段。还指示您可以使用 <a href="appendchunk-method-ado.md">AppendChunk</a> 和 <a href="getchunk-method-ado.md">GetChunk</a> 方法。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldMayBeNull</strong></p></td>
<td><p>0x40</p></td>
<td><p>指示您可以从字段中读取空值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldMayDefer</strong></p></td>
<td><p>0x2</p></td>
<td><p>指示字段是延迟的，即，字段值不是从具有整个记录的数据源检索的，而只是在您显式访问它们时检索的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldNegativeScale</strong></p></td>
<td><p>0x4000</p></td>
<td><p>指示字段代表来自支持负小数值的列中的数值。小数由 <a href="numericscale-property-ado.md">NumericScale</a> 属性指定。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldRowID</strong></p></td>
<td><p>0x100</p></td>
<td><p>指示字段包含无法写入的持久行标识符，并且除了用于标识行的值（如记录号、唯一标识符等）以外，字段的其他值没有意义。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldRowVersion</strong></p></td>
<td><p>0x200</p></td>
<td><p>指示字段包含用于跟踪更新的某些种类的时间戳或日期戳。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldUnknownUpdatable</strong></p></td>
<td><p>0x8</p></td>
<td><p>指示提供程序无法确定您是否可以向字段中写入内容。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFldUnspecified</strong></p></td>
<td><p>-1<br />
0xFFFFFFFF</p></td>
<td><p>指示提供程序不指定字段属性。</p></td>
</tr>
<tr class="even">
<td><p><strong>adFldUpdatable</strong></p></td>
<td><p>0x4</p></td>
<td><p>指示您可以写入字段。</p></td>
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
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums (长 FieldAttribute)</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums FieldAttribute</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums 不指定 FieldAttribute</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums 可更新 FieldAttribute</p></td>
</tr>
</tbody>
</table>

