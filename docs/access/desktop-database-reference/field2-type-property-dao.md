---
title: Field2 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 057d6ec9-b72c-cee6-005a-6d916e3dda29
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844921(v=office.15)
ms:contentKeyID: 48543032
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4da32f18a2b3e9dddbb0ae04e3257de34ba09761
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292662"
---
# <a name="field2type-property-dao"></a>Field2 属性 (DAO)


**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示对象的操作类型或数据类型。 可读/写 **Integer** 类型。

## <a name="syntax"></a>语法

*表达式*。类型

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

设置值或返回值是一个指示操作类型或数据类型的常量。对于 **Field2** 对象，该属性是可读写的，直到该对象追加到集合或另一个对象中，该属性才变为只读。

对于 **Field2** 对象，下表中描述了可能的设置和返回值。

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
<td><p>Char</p></td>
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
<td><p>双精度</p></td>
</tr>
<tr class="even">
<td><p><strong>dbFloat</strong></p></td>
<td><p>点数</p></td>
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
<td><p>备注</p></td>
</tr>
<tr class="even">
<td><p><strong>dbNumeric</strong></p></td>
<td><p>Numeric</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSingle</strong></p></td>
<td><p>单倍行距</p></td>
</tr>
<tr class="even">
<td><p><strong>dbText</strong></p></td>
<td><p>文本</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbTime</strong></p></td>
<td><p>Time</p></td>
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


将新的 **Field2**、 **Parameter** 或 **Property** 对象追加到 **Index**、 **QueryDef**、 **Recordset** 或 **TableDef** 对象集合中时，如果基础数据库不支持为新对象指定的数据类型，则会发生错误。

