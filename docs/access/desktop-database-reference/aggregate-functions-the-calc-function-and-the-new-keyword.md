---
title: 聚合函数、CALC 函数和 NEW 关键字
TOCTitle: Aggregate functions, the CALC function, and the NEW keyword
ms:assetid: c91fef19-bf41-8d04-f195-5470fb18393f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249977(v=office.15)
ms:contentKeyID: 48547669
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 25f52489430465235a928fff3c38469ec6ba83ad
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718047"
---
# <a name="aggregate-functions-the-calc-function-and-the-new-keyword"></a>聚合函数、CALC 函数和 NEW 关键字


**适用于**： Access 2013、 Office 2013

数据定形支持以下函数。分配给包含作为操作对象的列的章节的名称是 *chapter-alias*。

章节别名可能完全限定，包含导致本章包含的*列名称，* 所有句点隔开每个章节列名称。 例如，如果父章节 chap1 包含子章节 chap2，而后者具有一个数量列 amt，则限定名称为 chap1.chap2.amt。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>聚合函数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SUM (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>计算指定列中所有值之和。</p></td>
</tr>
<tr class="even">
<td><p>平均 (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>计算指定列中所有值的平均值。</p></td>
</tr>
<tr class="odd">
<td><p>最大值 (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>计算指定列中的最大值。</p></td>
</tr>
<tr class="even">
<td><p>MIN (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>计算指定列中的最小值。</p></td>
</tr>
<tr class="odd">
<td><p>计数 (<em>章节别名</em>[。<em>列名称</em>])</p></td>
<td><p>计算指定别名中的行数。如果指定了某列，则仅计算列值非空的行。</p></td>
</tr>
<tr class="even">
<td><p>STDEV (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>计算指定列中的标准偏差。</p></td>
</tr>
<tr class="odd">
<td><p>任何 (<em>章节别名</em>。<em>列名称</em>)</p></td>
<td><p>指定列的值。只有对于章节中所有行该列的值都相同时，ANY 才具有可预测的值。
</p><p><strong>注意</strong>： 如果列不包含相同的章节中的行的所有值，SHAPE 命令任意返回值为任何函数的值之一。</p></td>
</tr>
</tbody>
</table>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>计算表达式</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CALC(<em>expression</em>)</p></td>
<td><p>计算任意表达式，但只作用于包含 CALC 函数的 <strong>Recordset</strong> 的行。允许使用这些 <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications (VBA) 函数</a>的任意表达式。</p></td>
</tr>
</tbody>
</table>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>NEW 关键字</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>新<em>字段类型</em>[(<em>宽度</em> | <em>刻度</em> | <em>精度</em> | <em>错误</em>[，<em>扩展</em> | <em>错误</em>])]</p></td>
<td><p>向 <strong>Recordset</strong> 添加指定类型的空列。</p></td>
</tr>
</tbody>
</table>

<br/>

随 NEW 关键字传递的 *field-type* 可以是以下任意数据类型。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>OLE DB 数据类型</p></th>
<th><p>等效的 ADO 数据类型</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DBTYPE_BSTR</p></td>
<td><p>adBSTR</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_BOOL</p></td>
<td><p>adBoolean</p></td>
</tr>
<tr class="odd">
<td><p>为 DBTYPE_DECIMAL</p></td>
<td><p>为 adDecimal</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_UI1</p></td>
<td><p>adUnsignedTinyInt</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_I1</p></td>
<td><p>adTinyInt</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_UI2</p></td>
<td><p>adUnsignedSmallInt</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_UI4</p></td>
<td><p>adUnsignedInt</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_I8</p></td>
<td><p>adBigInt</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_UI8</p></td>
<td><p>adUnsignedBigInt</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_GUID</p></td>
<td><p>adGuid</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_BYTES</p></td>
<td><p>adBinary，感，adLongVarBinary</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_STR</p></td>
<td><p>每，以便您可以排除 adLongVarChar</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_WSTR</p></td>
<td><p>adWChar，adVarWChar adLongVarWChar</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_NUMERIC</p></td>
<td><p>adNumeric</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_DBDATE</p></td>
<td><p>adDBDate</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_DBTIME</p></td>
<td><p>adDBTime</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_DBTIMESTAMP</p></td>
<td><p>adDBTimeStamp</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_VARNUMERIC</p></td>
<td><p>adVarNumeric</p></td>
</tr>
<tr class="odd">
<td><p>DBTYPE_FILETIME</p></td>
<td><p>adFileTime</p></td>
</tr>
<tr class="even">
<td><p>DBTYPE_ERROR</p></td>
<td><p>adError</p></td>
</tr>
</tbody>
</table>


当新字段为小数类型 (在 OLE DB 中 DBTYPE\_小数，或在 ADO 中为 adDecimal)，您必须指定精度和刻度值。

