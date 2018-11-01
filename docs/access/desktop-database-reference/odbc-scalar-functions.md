---
title: ODBC Scalar 函数
TOCTitle: ODBC Scalar Functions
ms:assetid: dc1096bf-8241-036a-14c6-b19afae45454
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835353(v=office.15)
ms:contentKeyID: 48548120
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277473
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 21e6000e8620011f5f6f0c2481bb9c03fd71bab5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887955"
---
# <a name="odbc-scalar-functions"></a><span data-ttu-id="c4700-102">ODBC Scalar 函数</span><span class="sxs-lookup"><span data-stu-id="c4700-102">ODBC Scalar Functions</span></span>


<span data-ttu-id="c4700-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4700-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c4700-p101">Microsoft® Access SQL 支持使用 ODBC 定义的标量函数语法。例如查询：</span><span class="sxs-lookup"><span data-stu-id="c4700-p101">Microsoft® Access SQL supports the use of the ODBC defined syntax for scalar functions. For example, the query:</span></span>

<span data-ttu-id="c4700-106">SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} \> 5</span><span class="sxs-lookup"><span data-stu-id="c4700-106">SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} \> 5</span></span>

<span data-ttu-id="c4700-107">该查询返回股票价格浮动的绝对值大于 5 的所有行。</span><span class="sxs-lookup"><span data-stu-id="c4700-107">Would return all rows where the absolute value of the change in the price of a stock was greater than five.</span></span>

<span data-ttu-id="c4700-p102">可支持 ODBC 定义的标量函数的子集。下表列出了支持的函数。</span><span class="sxs-lookup"><span data-stu-id="c4700-p102">A subset of the ODBC defined scalar functions is supported. The following table lists the functions that are supported.</span></span>

<span data-ttu-id="c4700-110">关于参数的说明以及在 SQL 语句中包括函数的转义语法的完整说明，请参阅 ODBC 文档。</span><span class="sxs-lookup"><span data-stu-id="c4700-110">For a description of the arguments and a complete explanation of the escape syntax for including functions in a SQL statement, see the ODBC documentation.</span></span>

## <a name="string-functions"></a><span data-ttu-id="c4700-111">字符串函数</span><span class="sxs-lookup"><span data-stu-id="c4700-111">String Functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4700-112">ASCII</span><span class="sxs-lookup"><span data-stu-id="c4700-112">ASCII</span></span></p></td>
<td><p><span data-ttu-id="c4700-113">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c4700-113">LENGTH</span></span></p></td>
<td><p><span data-ttu-id="c4700-114">RTRIM</span><span class="sxs-lookup"><span data-stu-id="c4700-114">RTRIM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-115">CHAR</span><span class="sxs-lookup"><span data-stu-id="c4700-115">CHAR</span></span></p></td>
<td><p><span data-ttu-id="c4700-116">LOCATE</span><span class="sxs-lookup"><span data-stu-id="c4700-116">LOCATE</span></span></p></td>
<td><p><span data-ttu-id="c4700-117">SPACE</span><span class="sxs-lookup"><span data-stu-id="c4700-117">SPACE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-118">CONCAT</span><span class="sxs-lookup"><span data-stu-id="c4700-118">CONCAT</span></span></p></td>
<td><p><span data-ttu-id="c4700-119">LTRIM</span><span class="sxs-lookup"><span data-stu-id="c4700-119">LTRIM</span></span></p></td>
<td><p><span data-ttu-id="c4700-120">SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="c4700-120">SUBSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-121">LCASE</span><span class="sxs-lookup"><span data-stu-id="c4700-121">LCASE</span></span></p></td>
<td><p><span data-ttu-id="c4700-122">RIGHT</span><span class="sxs-lookup"><span data-stu-id="c4700-122">RIGHT</span></span></p></td>
<td><p><span data-ttu-id="c4700-123">UCASE</span><span class="sxs-lookup"><span data-stu-id="c4700-123">UCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-124">LEFT</span><span class="sxs-lookup"><span data-stu-id="c4700-124">LEFT</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="numeric-functions"></a><span data-ttu-id="c4700-125">数值函数</span><span class="sxs-lookup"><span data-stu-id="c4700-125">Numeric Functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4700-126">ABS</span><span class="sxs-lookup"><span data-stu-id="c4700-126">ABS</span></span></p></td>
<td><p><span data-ttu-id="c4700-127">FLOOR</span><span class="sxs-lookup"><span data-stu-id="c4700-127">FLOOR</span></span></p></td>
<td><p><span data-ttu-id="c4700-128">SIN</span><span class="sxs-lookup"><span data-stu-id="c4700-128">SIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-129">ATAN</span><span class="sxs-lookup"><span data-stu-id="c4700-129">ATAN</span></span></p></td>
<td><p><span data-ttu-id="c4700-130">LOG</span><span class="sxs-lookup"><span data-stu-id="c4700-130">LOG</span></span></p></td>
<td><p><span data-ttu-id="c4700-131">SQRT</span><span class="sxs-lookup"><span data-stu-id="c4700-131">SQRT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-132">CEILING</span><span class="sxs-lookup"><span data-stu-id="c4700-132">CEILING</span></span></p></td>
<td><p><span data-ttu-id="c4700-133">POWER</span><span class="sxs-lookup"><span data-stu-id="c4700-133">POWER</span></span></p></td>
<td><p><span data-ttu-id="c4700-134">TAN</span><span class="sxs-lookup"><span data-stu-id="c4700-134">TAN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-135">COS</span><span class="sxs-lookup"><span data-stu-id="c4700-135">COS</span></span></p></td>
<td><p><span data-ttu-id="c4700-136">RAND</span><span class="sxs-lookup"><span data-stu-id="c4700-136">RAND</span></span></p></td>
<td><p><span data-ttu-id="c4700-137">MOD</span><span class="sxs-lookup"><span data-stu-id="c4700-137">MOD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-138">EXP</span><span class="sxs-lookup"><span data-stu-id="c4700-138">EXP</span></span></p></td>
<td><p><span data-ttu-id="c4700-139">SIGN</span><span class="sxs-lookup"><span data-stu-id="c4700-139">SIGN</span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="time--date-functions"></a><span data-ttu-id="c4700-140">时间和日期函数</span><span class="sxs-lookup"><span data-stu-id="c4700-140">Time & Date Functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4700-141">CURDATE</span><span class="sxs-lookup"><span data-stu-id="c4700-141">CURDATE</span></span></p></td>
<td><p><span data-ttu-id="c4700-142">DAYOFYEAR</span><span class="sxs-lookup"><span data-stu-id="c4700-142">DAYOFYEAR</span></span></p></td>
<td><p><span data-ttu-id="c4700-143">MONTH</span><span class="sxs-lookup"><span data-stu-id="c4700-143">MONTH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-144">CURTIME</span><span class="sxs-lookup"><span data-stu-id="c4700-144">CURTIME</span></span></p></td>
<td><p><span data-ttu-id="c4700-145">YEAR</span><span class="sxs-lookup"><span data-stu-id="c4700-145">YEAR</span></span></p></td>
<td><p><span data-ttu-id="c4700-146">WEEK</span><span class="sxs-lookup"><span data-stu-id="c4700-146">WEEK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-147">NOW</span><span class="sxs-lookup"><span data-stu-id="c4700-147">NOW</span></span></p></td>
<td><p><span data-ttu-id="c4700-148">HOUR</span><span class="sxs-lookup"><span data-stu-id="c4700-148">HOUR</span></span></p></td>
<td><p><span data-ttu-id="c4700-149">QUARTER</span><span class="sxs-lookup"><span data-stu-id="c4700-149">QUARTER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4700-150">DAYOFMONTH</span><span class="sxs-lookup"><span data-stu-id="c4700-150">DAYOFMONTH</span></span></p></td>
<td><p><span data-ttu-id="c4700-151">MINUTE</span><span class="sxs-lookup"><span data-stu-id="c4700-151">MINUTE</span></span></p></td>
<td><p><span data-ttu-id="c4700-152">MONTHNAME</span><span class="sxs-lookup"><span data-stu-id="c4700-152">MONTHNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4700-153">DAYOFWEEK</span><span class="sxs-lookup"><span data-stu-id="c4700-153">DAYOFWEEK</span></span></p></td>
<td><p><span data-ttu-id="c4700-154">SECOND</span><span class="sxs-lookup"><span data-stu-id="c4700-154">SECOND</span></span></p></td>
<td><p><span data-ttu-id="c4700-155">DAYNAME</span><span class="sxs-lookup"><span data-stu-id="c4700-155">DAYNAME</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="data-type-conversion"></a><span data-ttu-id="c4700-156">数据类型转换</span><span class="sxs-lookup"><span data-stu-id="c4700-156">Data Type Conversion</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4700-157">CONVERT</span><span class="sxs-lookup"><span data-stu-id="c4700-157">CONVERT</span></span></p></td>
<td><p><span data-ttu-id="c4700-158">字面字符串可以转换成以下数据类型：SQL_FLOAT、SQL_DOUBLE、SQL_NUMERIC、SQL_INTEGER、SQL_REAL、SQL_SMALLINT、SQL_VARCHAR 和 SQL_DATETIME。</span><span class="sxs-lookup"><span data-stu-id="c4700-158">String literals can be converted to the following data types: SQL_FLOAT, SQL_DOUBLE, SQL_NUMERIC, SQL_INTEGER, SQL_REAL, SQL_SMALLINT, SQL_VARCHAR and SQL_DATETIME.</span></span></p></td>
</tr>
</tbody>
</table>

