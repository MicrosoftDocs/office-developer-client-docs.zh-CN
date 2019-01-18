---
title: Property.Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: bf8258ca-08b5-c4f9-e6d7-114e4300b2ef
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822796(v=office.15)
ms:contentKeyID: 48547490
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4280b89102e06b2ecc09a783840e671b0af9ff73
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28707169"
---
# <a name="propertytype-property-dao"></a>Property.Type 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 **Integer**。

## <a name="syntax"></a>语法

*表达式*。类型

*表达式*一个代表**Property**对象的变量。

## <a name="remarks"></a>注解

设置或返回值是一个指示操作类型或数据类型的常量。对于 **[Property](property-object-dao.md)** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。

对于 **Property** 对象，下表中描述了可能的设置和返回值。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbBigInt</strong></p></td>
<td><p>大整数</p></td>
</tr>
<tr class="even">
<td><p><strong>dbBinary</strong></p></td>
<td><p>Binary</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbBoolean</strong></p></td>
<td><p>Boolean</p></td>
</tr>
<tr class="even">
<td><p><strong>dbByte</strong></p></td>
<td><p>字节</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbChar</strong></p></td>
<td><p>字符</p></td>
</tr>
<tr class="even">
<td><p><strong>dbCurrency</strong></p></td>
<td><p>货币</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbDate</strong></p></td>
<td><p>日期/时间</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDecimal</strong></p></td>
<td><p>小数</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbDouble</strong></p></td>
<td><p>Double</p></td>
</tr>
<tr class="even">
<td><p><strong>dbFloat</strong></p></td>
<td><p>Float</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbGUID</strong></p></td>
<td><p>GUID</p></td>
</tr>
<tr class="even">
<td><p><strong>dbInteger</strong></p></td>
<td><p>整数</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbLong</strong></p></td>
<td><p>Long</p></td>
</tr>
<tr class="even">
<td><p><strong>dbLongBinary</strong></p></td>
<td><p>长二进制（OLE 对象）</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbMemo</strong></p></td>
<td><p>Memo</p></td>
</tr>
<tr class="even">
<td><p><strong>dbNumeric</strong></p></td>
<td><p>Numeric</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSingle</strong></p></td>
<td><p>Single</p></td>
</tr>
<tr class="even">
<td><p><strong>dbText</strong></p></td>
<td><p>文本</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbTime</strong></p></td>
<td><p>时间</p></td>
</tr>
<tr class="even">
<td><p><strong>dbTimeStamp</strong></p></td>
<td><p>时间戳</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVarBinary</strong></p></td>
<td><p>VarBinary</p></td>
</tr>
</tbody>
</table>


将新的 **Field**、 **Parameter** 或 **Property** 对象追加到 **[Index](index-object-dao.md)** 、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。

