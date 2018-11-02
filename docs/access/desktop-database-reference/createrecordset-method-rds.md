---
title: CreateRecordset 方法 (RDS)
TOCTitle: CreateRecordset method (RDS)
ms:assetid: 19524509-31da-9af1-4062-cd3c59b51278
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248940(v=office.15)
ms:contentKeyID: 48543497
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 42a5bf11e2ed287ac683f634d3953739b2501f60
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922802"
---
# <a name="createrecordset-method-rds"></a>CreateRecordset 方法 (RDS)


**适用于**： Access 2013、 Office 2013


用于创建断开连接的空 [Recordset](recordset-object-ado.md)。

## <a name="syntax"></a>语法

*对象*。CreateRecordset (*ColumnInfos*)

## <a name="parameters"></a>参数

  - *Object*

  - 一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

  - *ColumnsInfos*

  - 属性的 **变量型** 数组，用于定义所创建的 **Recordset** 中的各个列。每个列定义都包含一个数组，其中包含四个必需属性和一个可选属性。 列数组集合随后组合到定义 **Recordset** 的数组中。
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>属性</p></th>
    <th><p>说明</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>列标题的名称。</p></td>
    </tr>
    <tr class="even">
    <td><p>Type</p></td>
    <td><p>代表数据类型的整数。</p></td>
    </tr>
    <tr class="odd">
    <td><p>Size</p></td>
    <td><p>代表宽度的整数（以字符为单位），与数据类型无关。</p></td>
    </tr>
    <tr class="even">
    <td><p>Nullability</p></td>
    <td><p>布尔值。</p></td>
    </tr>
    <tr class="odd">
    <td><p>Scale<br />
（可选）</p></td>
    <td><p>此可选属性定义数值字段的位数。如果未指定此值，数值将被截取为三位。精度不会受影响，但小数点之后的位数将截取为三位。</p></td>
    </tr>
    </tbody>
    </table>


## <a name="remarks"></a>说明

服务器端业务对象可以使用来自非 OLE DB 数据提供程序（例如，包含股票报价的操作系统文件）的数据来填充生成的 **Recordset** 。

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
<th><p>长度</p></th>
<th><p>常量</p></th>
<th><p>编号</p></th>
<th><p>替换</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adTinyInt</strong></p></td>
<td><p>16</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adSmallInt</strong></p></td>
<td><p>2</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adInteger</strong></p></td>
<td><p>3</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adBigInt</strong></p></td>
<td><p>20</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adUnsignedTinyInt</strong></p></td>
<td><p>17</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adUnsignedSmallInt</strong></p></td>
<td><p>18</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adUnsignedInt</strong></p></td>
<td><p>19</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adUnsignedBigInt</strong></p></td>
<td><p>21</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adSingle</strong></p></td>
<td><p>4</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adDouble</strong></p></td>
<td><p>5</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adCurrency</strong></p></td>
<td><p>6</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>为 adDecimal</strong></p></td>
<td><p>14</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adNumeric</strong></p></td>
<td><p>131</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adBoolean</strong></p></td>
<td><p>11</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adError</strong></p></td>
<td><p>10</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adGuid</strong></p></td>
<td><p>72</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adDate</strong></p></td>
<td><p>7</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adDBDate</strong></p></td>
<td><p>133</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>固定</p></td>
<td><p><strong>adDBTime</strong></p></td>
<td><p>134</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>固定</p></td>
<td><p><strong>adDBTimestamp</strong></p></td>
<td><p>135</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>可变</p></td>
<td><p><strong>adBSTR</strong></p></td>
<td><p>8</p></td>
<td><p>130</p></td>
</tr>
<tr class="even">
<td><p>可变</p></td>
<td><p><strong>每</strong></p></td>
<td><p>129</p></td>
<td><p>200</p></td>
</tr>
<tr class="odd">
<td><p>可变</p></td>
<td><p><strong>以便您可以排除</strong></p></td>
<td><p>200</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>可变</p></td>
<td><p><strong>adLongVarChar</strong></p></td>
<td><p>201</p></td>
<td><p>200</p></td>
</tr>
<tr class="odd">
<td><p>可变</p></td>
<td><p><strong>adWChar</strong></p></td>
<td><p>130</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>可变</p></td>
<td><p><strong>adVarWChar</strong></p></td>
<td><p>202</p></td>
<td><p>130</p></td>
</tr>
<tr class="odd">
<td><p>可变</p></td>
<td><p><strong>adLongVarWChar</strong></p></td>
<td><p>203</p></td>
<td><p>130</p></td>
</tr>
<tr class="even">
<td><p>可变</p></td>
<td><p><strong>adBinary</strong></p></td>
<td><p>128</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>可变</p></td>
<td><p><strong>感</strong></p></td>
<td><p>204</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>可变</p></td>
<td><p><strong>adLongVarBinary</strong></p></td>
<td><p>205</p></td>
<td><p>204</p></td>
</tr>
</tbody>
</table>

