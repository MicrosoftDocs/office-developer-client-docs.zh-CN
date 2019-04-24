---
title: CreateRecordset 方法 (RDS)
TOCTitle: CreateRecordset method (RDS)
ms:assetid: 19524509-31da-9af1-4062-cd3c59b51278
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248940(v=office.15)
ms:contentKeyID: 48543497
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3dda0840617c32e9dceea3bd1baa362c5652a373
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295336"
---
# <a name="createrecordset-method-rds"></a>CreateRecordset 方法 (RDS)

**适用于**：Access 2013、Office 2013

用于创建断开连接的空 [Recordset](recordset-object-ado.md)。

## <a name="syntax"></a>语法

*对象*。CreateRecordset (*ColumnInfos*)

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Object* |一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*ColumnsInfos* |属性的 **变量型** 数组，用于定义所创建的 **Recordset** 中的各个列。 每个列定义都包含一个数组，其中包含四个必需属性和一个可选属性。 列数组集合随后组合到定义 **Recordset** 的数组中。 有关属性的列表, 请参阅下表。|

### <a name="variant-array-attributes"></a>Variant 数组属性

|属性|说明|
|:--------|:----------|
|Name |列标题的名称。|
|类型 |代表数据类型的整数。|
|大小 |代表宽度的整数（以字符为单位），与数据类型无关。|
|null |布尔值。|
|小数位数 (可选) |此可选属性定义数值字段的位数。如果未指定此值，数值将被截取为三位。精度不会受影响，但小数点之后的位数将截取为三位。|

## <a name="remarks"></a>注解

服务器端业务对象可以使用来自非 OLE DB 数据提供程序（例如，包含股票报价的操作系统文件）的数据来填充生成的 **Recordset**。

下表列出了 [CreateRecordset](datatypeenum.md) 方法支持的 **DataTypeEnum** 值。所列的数字是用于定义字段的引用编号。

每种数据类型可能是固定长度，也可能是可变长度。固定长度的类型应使用大小 –1 来定义，由于该大小是预先确定的，因此仍然需要大小定义。可变长度的数据类型允许大小为 1 到 32767。

对于某些可变数据类型，类型可能会被强制为"替换"列中注明的类型。在创建并填充了 **Recordset** 之后，您才会看到替换内容。然后，可以根据需要检查实际的数据类型。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Length</p></th>
<th><p>常量</p></th>
<th><p>帐号</p></th>
<th><p>置换</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adTinyInt</strong></p></td>
<td><p>位</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adSmallInt</strong></p></td>
<td><p>双面</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adInteger</strong></p></td>
<td><p>第三章</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adBigInt</strong></p></td>
<td><p>20</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adUnsignedTinyInt</strong></p></td>
<td><p>×</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adUnsignedSmallInt</strong></p></td>
<td><p>18</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adUnsignedInt</strong></p></td>
<td><p>合</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adUnsignedBigInt</strong></p></td>
<td><p>不足</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adSingle</strong></p></td>
<td><p>4</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adDouble</strong></p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adCurrency</strong></p></td>
<td><p>型</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adDecimal</strong></p></td>
<td><p>日</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adNumeric</strong></p></td>
<td><p>131</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adBoolean</strong></p></td>
<td><p>11x17</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adError</strong></p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adGuid</strong></p></td>
<td><p>72</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adDate</strong></p></td>
<td><p>步</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adDBDate</strong></p></td>
<td><p>133</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Fixed</p></td>
<td><p><strong>adDBTime</strong></p></td>
<td><p>134</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Fixed</p></td>
<td><p><strong>adDBTimestamp</strong></p></td>
<td><p>135</p></td>
<td><p>步</p></td>
</tr>
<tr class="odd">
<td><p>变量</p></td>
<td><p><strong>adBSTR</strong></p></td>
<td><p>utf-8</p></td>
<td><p>130</p></td>
</tr>
<tr class="even">
<td><p>变量</p></td>
<td><p><strong>adChar</strong></p></td>
<td><p>129</p></td>
<td><p>200</p></td>
</tr>
<tr class="odd">
<td><p>变量</p></td>
<td><p><strong>adVarChar</strong></p></td>
<td><p>200</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>变量</p></td>
<td><p><strong>adLongVarChar</strong></p></td>
<td><p>201</p></td>
<td><p>200</p></td>
</tr>
<tr class="odd">
<td><p>变量</p></td>
<td><p><strong>adWChar</strong></p></td>
<td><p>130</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>变量</p></td>
<td><p><strong>adVarWChar</strong></p></td>
<td><p>202</p></td>
<td><p>130</p></td>
</tr>
<tr class="odd">
<td><p>变量</p></td>
<td><p><strong>adLongVarWChar</strong></p></td>
<td><p>203</p></td>
<td><p>130</p></td>
</tr>
<tr class="even">
<td><p>变量</p></td>
<td><p><strong>adBinary</strong></p></td>
<td><p>128</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>变量</p></td>
<td><p><strong>adVarBinary</strong></p></td>
<td><p>204</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>变量</p></td>
<td><p><strong>adLongVarBinary</strong></p></td>
<td><p>205</p></td>
<td><p>204</p></td>
</tr>
</tbody>
</table>

