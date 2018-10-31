---
title: DataTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: DataTypeEnum
ms:assetid: a8ab7616-552f-ed5f-ed55-95254cfb374a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249780(v=office.15)
ms:contentKeyID: 48546904
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: f5c192589f2c90b2ce7b6c7b376b80c92b341e2d
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860656"
---
# <a name="datatypeenum"></a>DataTypeEnum

**适用于**： Access 2013 |Office 2013

用于指定 [Field](field-object-ado.md)、[Parameter](parameter-object-ado.md) 或 [Property](property-object-ado.md) 的数据类型。下表的说明列的圆括号中显示了对应的 OLE DB 类型指示器。有关 OLE DB 数据类型的详细信息，请参阅 *《OLE DB 程序员参考》* 的第 13 章和附录 A。

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
<td><p><strong>AdArray<br />
</strong>（不适用于 ADOX。）</p></td>
<td><p>0x2000</p></td>
<td><p>标志值，始终与另一个数据类型常量组合使用，以指示该数据类型的数组。</p></td>
</tr>
<tr class="even">
<td><p><strong>adBigInt</strong></p></td>
<td><p>20</p></td>
<td><p>指示八字节有符号整数 (DBTYPE_I8)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adBinary</strong></p></td>
<td><p>128</p></td>
<td><p>指示二进制值 (DBTYPE_BYTES)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adBoolean</strong></p></td>
<td><p>11</p></td>
<td><p>指示布尔型值 (DBTYPE_BOOL)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adBSTR</strong></p></td>
<td><p>8</p></td>
<td><p>指示空结尾字符串 (Unicode) (DBTYPE_BSTR)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adChapter</strong></p></td>
<td><p>136</p></td>
<td><p>指示四字节章节值（标识子行集中的行）(DBTYPE_HCHAPTER)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>每</strong></p></td>
<td><p>129</p></td>
<td><p>指示字符串值 (DBTYPE_STR)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adCurrency</strong></p></td>
<td><p>6</p></td>
<td><p>指示货币值 (DBTYPE_CY)。货币是小数位数固定的数字（小数点右侧保留四位）。以八字节有符号整数（以 10,000 为比例）存储。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adDate</strong></p></td>
<td><p>7</p></td>
<td><p>指示日期值 (DBTYPE_DATE)。日期存储为双精度型，其整数部分是 1899 年 12 月 30 日以后的天数，小数部分是某一天内的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>adDBDate</strong></p></td>
<td><p>133</p></td>
<td><p>指示日期值（年月日）(DBTYPE_DBDATE)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adDBTime</strong></p></td>
<td><p>134</p></td>
<td><p>指示时间值（小时分秒）(DBTYPE_DBTIME)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adDBTimeStamp</strong></p></td>
<td><p>135</p></td>
<td><p>指示日期/时间戳（年月日小时分秒加上分数，单位：十亿分之一）(DBTYPE_DBTIMESTAMP)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>为 adDecimal</strong></p></td>
<td><p>14</p></td>
<td><p>指示具有固定精度和范围的确切数值 (DBTYPE_DECIMAL)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adDouble</strong></p></td>
<td><p>5</p></td>
<td><p>指示双精度浮点值 (DBTYPE_R8)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adEmpty</strong></p></td>
<td><p>0</p></td>
<td><p>不指定值 (DBTYPE_EMPTY)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adError</strong></p></td>
<td><p>10</p></td>
<td><p>指示 32 位错误代码 (DBTYPE_ERROR)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adFileTime</strong></p></td>
<td><p>64</p></td>
<td><p>指示 64 位值，该值表示自 1601 年 1 月 1 日以来的 100 纳秒间隔的数量 (DBTYPE_FILETIME)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adGUID</strong></p></td>
<td><p>72</p></td>
<td><p>指示全局唯一标识符 (GUID) (DBTYPE_GUID)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adIDispatch</strong></p></td>
<td><p>9</p></td>
<td><p>指示指向 COM 对象上的 <strong>IDispatch</strong> 接口的指针 (DBTYPE_IDISPATCH)。
</p><p><strong>注意</strong>： ADO 当前不支持此数据类型。 使用情况可能会导致无法预料的结果。</p>
</td>
</tr>
<tr class="even">
<td><p><strong>adInteger</strong></p></td>
<td><p>3</p></td>
<td><p>指示四字节有符号整数 (DBTYPE_I4)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adIUnknown</strong></p></td>
<td><p>13</p></td>
<td><p>指示指向 COM 对象上的 <strong>IUnknown</strong> 接口的指针 (DBTYPE_IUNKNOWN)。
</p><p><strong>注意</strong>： ADO 当前不支持此数据类型。 使用情况可能会导致无法预料的结果。
</p></td>
</tr>
<tr class="even">
<td><p><strong>adLongVarBinary</strong></p></td>
<td><p>205</p></td>
<td><p>指示长二进制值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adLongVarChar</strong></p></td>
<td><p>201</p></td>
<td><p>指示长字符串值。</p></td>
</tr>
<tr class="even">
<td><p><strong>adLongVarWChar</strong></p></td>
<td><p>203</p></td>
<td><p>指示长空结尾 Unicode 字符串值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adNumeric</strong></p></td>
<td><p>131</p></td>
<td><p>指示具有固定精度和范围的确切数值 (DBTYPE_NUMERIC)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adPropVariant</strong></p></td>
<td><p>138</p></td>
<td><p>指示 Automation PROPVARIANT 类型 (DBTYPE_PROP_VARIANT)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adSingle</strong></p></td>
<td><p>4</p></td>
<td><p>指示单精度浮点值 (DBTYPE_R4)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adSmallInt</strong></p></td>
<td><p>2</p></td>
<td><p>指示双字节有符号整数 (DBTYPE_I2)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adTinyInt</strong></p></td>
<td><p>16</p></td>
<td><p>指示单字节有符号整数 (DBTYPE_I1)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUnsignedBigInt</strong></p></td>
<td><p>21</p></td>
<td><p>指示八字节无符号整数 (DBTYPE_UI8)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adUnsignedInt</strong></p></td>
<td><p>19</p></td>
<td><p>指示四字节无符号整数 (DBTYPE_UI4)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUnsignedSmallInt</strong></p></td>
<td><p>18</p></td>
<td><p>指示双字节无符号整数 (DBTYPE_UI2)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adUnsignedTinyInt</strong></p></td>
<td><p>17</p></td>
<td><p>指示单字节无符号整数 (DBTYPE_UI1)。</p></td>
</tr>
<tr class="even">
<td><p><strong>adUserDefined</strong></p></td>
<td><p>132</p></td>
<td><p>指示用户定义的变量 (DBTYPE_UDT)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>感</strong></p></td>
<td><p>204</p></td>
<td><p>指示二进制值（仅限 <strong>Parameter</strong> 对象）。</p></td>
</tr>
<tr class="even">
<td><p><strong>以便您可以排除</strong></p></td>
<td><p>200</p></td>
<td><p>指示字符串值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adVariant</strong></p></td>
<td><p>12</p></td>
<td><p>指示自动化<strong>变量型</strong> (DBTYPE_VARIANT)。
</p><p><strong>注意</strong>： ADO 当前不支持此数据类型。 使用情况可能会导致无法预料的结果。</p></td>
</tr>
<tr class="even">
<td><p><strong>adVarNumeric</strong></p></td>
<td><p>139</p></td>
<td><p>指示数字值（仅限 <strong>Parameter</strong> 对象）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>adVarWChar</strong></p></td>
<td><p>202</p></td>
<td><p>指示空结尾 Unicode 字符串。</p></td>
</tr>
<tr class="even">
<td><p><strong>adWChar</strong></p></td>
<td><p>130</p></td>
<td><p>指示空结尾 Unicode 字符串 (DBTYPE_WSTR)。</p></td>
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
<td><p>AdoEnums.DataType.ARRAY</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.BIGINT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.BINARY</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.BOOLEAN</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.BSTR</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.CHAPTER</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.CHAR</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.CURRENCY</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.DATE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.DBDATE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.DBTIME</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.DBTIMESTAMP</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.DECIMAL</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.DOUBLE</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.EMPTY</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.ERROR</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.FILETIME</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.GUID</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.IDISPATCH</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.INTEGER</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.IUNKNOWN</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.LONGVARBINARY</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.LONGVARCHAR</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.LONGVARWCHAR</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.NUMERIC</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.PROPVARIANT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.SINGLE</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.SMALLINT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.TINYINT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.UNSIGNEDBIGINT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.UNSIGNEDINT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.UNSIGNEDSMALLINT</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.UNSIGNEDTINYINT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.USERDEFINED</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.VARBINARY</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.VARCHAR</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.VARIANT</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.VARNUMERIC</p></td>
</tr>
<tr class="odd">
<td><p>AdoEnums.DataType.VARWCHAR</p></td>
</tr>
<tr class="even">
<td><p>AdoEnums.DataType.WCHAR</p></td>
</tr>
</tbody>
</table>

