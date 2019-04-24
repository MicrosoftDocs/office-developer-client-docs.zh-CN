---
title: CollatingOrder 属性 (DAO)
TOCTitle: CollatingOrder Property
ms:assetid: cb1d6fc9-a2a6-54c2-abf5-48b609e38738
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834380(v=office.15)
ms:contentKeyID: 48547709
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 02711fbbf39b058bb88e9568716169825ae4a923
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292865"
---
# <a name="field2collatingorder-property-dao"></a>CollatingOrder 属性 (DAO)


**适用于**：Access 2013、Office 2013

返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 **Long**。

## <a name="syntax"></a>语法

*表达式*。CollatingOrder

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

返回值为 **Long** 类型值，或者为下列值之一的常量。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>排序次序</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbSortGeneral</strong></p></td>
<td><p>常规（英语、法语、德语、葡萄牙语、意大利语和现代西班牙语）</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortArabic</strong></p></td>
<td><p>阿拉伯语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortChineseSimplified</strong></p></td>
<td><p>简体中文</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortChineseTraditional</strong></p></td>
<td><p>繁体中文</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortCyrillic</strong></p></td>
<td><p>俄语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortCzech</strong></p></td>
<td><p>捷克语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortDutch</strong></p></td>
<td><p>荷兰语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortGreek</strong></p></td>
<td><p>希腊语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortHebrew</strong></p></td>
<td><p>希伯来语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortHungarian</strong></p></td>
<td><p>匈牙利语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortIcelandic</strong></p></td>
<td><p>冰岛语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortJapanese</strong></p></td>
<td><p>日语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortKorean</strong></p></td>
<td><p>朝鲜语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortNeutral</strong></p></td>
<td><p>适中</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortNorwDan</strong></p></td>
<td><p>挪威语或丹麦语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortPDXIntl</strong></p></td>
<td><p>Paradox 国际型</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortPDXNor</strong></p></td>
<td><p>Paradox 挪威语或丹麦语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortPDXSwe</strong></p></td>
<td><p>Paradox 瑞典语或芬兰语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortPolish</strong></p></td>
<td><p>波兰语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortSlovenian</strong></p></td>
<td><p>斯洛文尼亚语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortSpanish</strong></p></td>
<td><p>西班牙语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortSwedFin</strong></p></td>
<td><p>瑞典语或芬兰语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortThai</strong></p></td>
<td><p>泰语</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSortTurkish</strong></p></td>
<td><p>土耳其语</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSortUndefined</strong></p></td>
<td><p>不确定或未知</p></td>
</tr>
</tbody>
</table>


**CollatingOrder** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 Fields 集合属于</p></th>
<th><p>则 CollatingOrder</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong> 对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong> 对象</p></td>
<td><p>不受支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


创建数据库时, **CollatingOrder**属性设置对应于**CreateDatabase**方法的 locale 参数, 或者数据库最近压缩时的**CompactDatabase**方法。

**Index** 对象的 **Fields** 集合中的 **Field2** 对象的 **CollatingOrder** 和 **Attributes** 属性设置共同确定索引中排序次序的序列和方向。但是，不能设置单个索引的整理顺序 - 只能设置整个表的整理顺序。

