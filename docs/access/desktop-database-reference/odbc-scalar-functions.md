---
title: ODBC Scalar 函数
TOCTitle: ODBC scalar functions
ms:assetid: dc1096bf-8241-036a-14c6-b19afae45454
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835353(v=office.15)
ms:contentKeyID: 48548120
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277473
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 33443fda474b3785d34d457719e49f5e358bb254
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288509"
---
# <a name="odbc-scalar-functions"></a>ODBC Scalar 函数

**适用于**：Access 2013、Office 2013

Microsoft Access SQL 支持对标量函数使用 ODBC 定义的语法。 

例如, 该查询`SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} > 5`将返回股票价格中的绝对值超过五个的所有行。

可支持 ODBC 定义的标量函数的子集。下表列出了支持的函数。

关于参数的说明以及在 SQL 语句中包括函数的转义语法的完整说明，请参阅 ODBC 文档。

## <a name="string-functions"></a>String 函数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>ASCII</p></td>
<td><p>段</p></td>
<td><p>RTRIM</p></td>
</tr>
<tr class="even">
<td><p>资料</p></td>
<td><p>找</p></td>
<td><p>SPACE</p></td>
</tr>
<tr class="odd">
<td><p>串联</p></td>
<td><p>LTRIM</p></td>
<td><p>取</p></td>
</tr>
<tr class="even">
<td><p>LCASE</p></td>
<td><p>左向右</p></td>
<td><p>UCASE</p></td>
</tr>
<tr class="odd">
<td><p>左至右</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="numeric-functions"></a>数值函数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>ABS</p></td>
<td><p>图</p></td>
<td><p>SIN</p></td>
</tr>
<tr class="even">
<td><p>ATAN</p></td>
<td><p>.log</p></td>
<td><p>SQRT</p></td>
</tr>
<tr class="odd">
<td><p>向上</p></td>
<td><p>能力</p></td>
<td><p>TAN</p></td>
</tr>
<tr class="even">
<td><p>COS</p></td>
<td><p>多次</p></td>
<td><p>模块</p></td>
</tr>
<tr class="odd">
<td><p>过期</p></td>
<td><p>记号</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="time--date-functions"></a>时间 & 日期函数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>CURDATE</p></td>
<td><p>DAYOFYEAR</p></td>
<td><p>本月</p></td>
</tr>
<tr class="even">
<td><p>CURTIME</p></td>
<td><p>本年</p></td>
<td><p>周</p></td>
</tr>
<tr class="odd">
<td><p>已经</p></td>
<td><p>七点</p></td>
<td><p>结算</p></td>
</tr>
<tr class="even">
<td><p>DAYOFMONTH</p></td>
<td><p>还要</p></td>
<td><p>MONTHNAME</p></td>
</tr>
<tr class="odd">
<td><p>DAYOFWEEK</p></td>
<td><p>第二个</p></td>
<td><p>DAYNAME</p></td>
</tr>
</tbody>
</table>


## <a name="data-type-conversion"></a>数据类型转换

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>转换</p></td>
<td><p>字面字符串可以转换成以下数据类型：SQL_FLOAT、SQL_DOUBLE、SQL_NUMERIC、SQL_INTEGER、SQL_REAL、SQL_SMALLINT、SQL_VARCHAR 和 SQL_DATETIME。</p></td>
</tr>
</tbody>
</table>

