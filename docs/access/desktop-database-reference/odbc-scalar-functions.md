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
ms.openlocfilehash: 4e841da9d401558311682f0abcbefde9161b71b3
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025992"
---
# <a name="odbc-scalar-functions"></a><span data-ttu-id="f348a-102">ODBC Scalar 函数</span><span class="sxs-lookup"><span data-stu-id="f348a-102">ODBC scalar functions</span></span>

<span data-ttu-id="f348a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f348a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f348a-104">Microsoft Access SQL 支持的 scalar 函数的定义的 ODBC 语法。</span><span class="sxs-lookup"><span data-stu-id="f348a-104">Microsoft Access SQL supports the use of the ODBC defined syntax for scalar functions.</span></span> 

<span data-ttu-id="f348a-105">例如，查询`SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} > 5`查询返回股票价格浮动的更改的绝对值大于 5 的所有行。</span><span class="sxs-lookup"><span data-stu-id="f348a-105">For example, the query `SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} > 5` would return all rows where the absolute value of the change in the price of a stock was greater than five.</span></span>

<span data-ttu-id="f348a-p101">可支持 ODBC 定义的标量函数的子集。下表列出了支持的函数。</span><span class="sxs-lookup"><span data-stu-id="f348a-p101">A subset of the ODBC defined scalar functions is supported. The following table lists the functions that are supported.</span></span>

<span data-ttu-id="f348a-108">关于参数的说明以及在 SQL 语句中包括函数的转义语法的完整说明，请参阅 ODBC 文档。</span><span class="sxs-lookup"><span data-stu-id="f348a-108">For a description of the arguments and a complete explanation of the escape syntax for including functions in a SQL statement, see the ODBC documentation.</span></span>

## <a name="string-functions"></a><span data-ttu-id="f348a-109">字符串函数</span><span class="sxs-lookup"><span data-stu-id="f348a-109">String functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f348a-110">ASCII</span><span class="sxs-lookup"><span data-stu-id="f348a-110">ASCII</span></span></p></td>
<td><p><span data-ttu-id="f348a-111">LENGTH</span><span class="sxs-lookup"><span data-stu-id="f348a-111">LENGTH</span></span></p></td>
<td><p><span data-ttu-id="f348a-112">RTRIM</span><span class="sxs-lookup"><span data-stu-id="f348a-112">RTRIM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-113">CHAR</span><span class="sxs-lookup"><span data-stu-id="f348a-113">CHAR</span></span></p></td>
<td><p><span data-ttu-id="f348a-114">LOCATE</span><span class="sxs-lookup"><span data-stu-id="f348a-114">LOCATE</span></span></p></td>
<td><p><span data-ttu-id="f348a-115">SPACE</span><span class="sxs-lookup"><span data-stu-id="f348a-115">SPACE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-116">CONCAT</span><span class="sxs-lookup"><span data-stu-id="f348a-116">CONCAT</span></span></p></td>
<td><p><span data-ttu-id="f348a-117">LTRIM</span><span class="sxs-lookup"><span data-stu-id="f348a-117">LTRIM</span></span></p></td>
<td><p><span data-ttu-id="f348a-118">SUBSTRING</span><span class="sxs-lookup"><span data-stu-id="f348a-118">SUBSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-119">LCASE</span><span class="sxs-lookup"><span data-stu-id="f348a-119">LCASE</span></span></p></td>
<td><p><span data-ttu-id="f348a-120">RIGHT</span><span class="sxs-lookup"><span data-stu-id="f348a-120">RIGHT</span></span></p></td>
<td><p><span data-ttu-id="f348a-121">UCASE</span><span class="sxs-lookup"><span data-stu-id="f348a-121">UCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-122">LEFT</span><span class="sxs-lookup"><span data-stu-id="f348a-122">LEFT</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="numeric-functions"></a><span data-ttu-id="f348a-123">数值函数</span><span class="sxs-lookup"><span data-stu-id="f348a-123">Numeric functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f348a-124">ABS</span><span class="sxs-lookup"><span data-stu-id="f348a-124">ABS</span></span></p></td>
<td><p><span data-ttu-id="f348a-125">FLOOR</span><span class="sxs-lookup"><span data-stu-id="f348a-125">FLOOR</span></span></p></td>
<td><p><span data-ttu-id="f348a-126">SIN</span><span class="sxs-lookup"><span data-stu-id="f348a-126">SIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-127">ATAN</span><span class="sxs-lookup"><span data-stu-id="f348a-127">ATAN</span></span></p></td>
<td><p><span data-ttu-id="f348a-128">LOG</span><span class="sxs-lookup"><span data-stu-id="f348a-128">LOG</span></span></p></td>
<td><p><span data-ttu-id="f348a-129">SQRT</span><span class="sxs-lookup"><span data-stu-id="f348a-129">SQRT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-130">CEILING</span><span class="sxs-lookup"><span data-stu-id="f348a-130">CEILING</span></span></p></td>
<td><p><span data-ttu-id="f348a-131">POWER</span><span class="sxs-lookup"><span data-stu-id="f348a-131">POWER</span></span></p></td>
<td><p><span data-ttu-id="f348a-132">TAN</span><span class="sxs-lookup"><span data-stu-id="f348a-132">TAN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-133">COS</span><span class="sxs-lookup"><span data-stu-id="f348a-133">COS</span></span></p></td>
<td><p><span data-ttu-id="f348a-134">RAND</span><span class="sxs-lookup"><span data-stu-id="f348a-134">RAND</span></span></p></td>
<td><p><span data-ttu-id="f348a-135">MOD</span><span class="sxs-lookup"><span data-stu-id="f348a-135">MOD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-136">EXP</span><span class="sxs-lookup"><span data-stu-id="f348a-136">EXP</span></span></p></td>
<td><p><span data-ttu-id="f348a-137">SIGN</span><span class="sxs-lookup"><span data-stu-id="f348a-137">SIGN</span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="time--date-functions"></a><span data-ttu-id="f348a-138">时间和日期函数</span><span class="sxs-lookup"><span data-stu-id="f348a-138">Time & Date functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f348a-139">CURDATE</span><span class="sxs-lookup"><span data-stu-id="f348a-139">CURDATE</span></span></p></td>
<td><p><span data-ttu-id="f348a-140">DAYOFYEAR</span><span class="sxs-lookup"><span data-stu-id="f348a-140">DAYOFYEAR</span></span></p></td>
<td><p><span data-ttu-id="f348a-141">MONTH</span><span class="sxs-lookup"><span data-stu-id="f348a-141">MONTH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-142">CURTIME</span><span class="sxs-lookup"><span data-stu-id="f348a-142">CURTIME</span></span></p></td>
<td><p><span data-ttu-id="f348a-143">YEAR</span><span class="sxs-lookup"><span data-stu-id="f348a-143">YEAR</span></span></p></td>
<td><p><span data-ttu-id="f348a-144">WEEK</span><span class="sxs-lookup"><span data-stu-id="f348a-144">WEEK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-145">NOW</span><span class="sxs-lookup"><span data-stu-id="f348a-145">NOW</span></span></p></td>
<td><p><span data-ttu-id="f348a-146">HOUR</span><span class="sxs-lookup"><span data-stu-id="f348a-146">HOUR</span></span></p></td>
<td><p><span data-ttu-id="f348a-147">QUARTER</span><span class="sxs-lookup"><span data-stu-id="f348a-147">QUARTER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f348a-148">DAYOFMONTH</span><span class="sxs-lookup"><span data-stu-id="f348a-148">DAYOFMONTH</span></span></p></td>
<td><p><span data-ttu-id="f348a-149">MINUTE</span><span class="sxs-lookup"><span data-stu-id="f348a-149">MINUTE</span></span></p></td>
<td><p><span data-ttu-id="f348a-150">MONTHNAME</span><span class="sxs-lookup"><span data-stu-id="f348a-150">MONTHNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f348a-151">DAYOFWEEK</span><span class="sxs-lookup"><span data-stu-id="f348a-151">DAYOFWEEK</span></span></p></td>
<td><p><span data-ttu-id="f348a-152">SECOND</span><span class="sxs-lookup"><span data-stu-id="f348a-152">SECOND</span></span></p></td>
<td><p><span data-ttu-id="f348a-153">DAYNAME</span><span class="sxs-lookup"><span data-stu-id="f348a-153">DAYNAME</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="data-type-conversion"></a><span data-ttu-id="f348a-154">数据类型转换</span><span class="sxs-lookup"><span data-stu-id="f348a-154">Data type conversion</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f348a-155">CONVERT</span><span class="sxs-lookup"><span data-stu-id="f348a-155">CONVERT</span></span></p></td>
<td><p><span data-ttu-id="f348a-156">字面字符串可以转换成以下数据类型：SQL_FLOAT、SQL_DOUBLE、SQL_NUMERIC、SQL_INTEGER、SQL_REAL、SQL_SMALLINT、SQL_VARCHAR 和 SQL_DATETIME。</span><span class="sxs-lookup"><span data-stu-id="f348a-156">String literals can be converted to the following data types: SQL_FLOAT, SQL_DOUBLE, SQL_NUMERIC, SQL_INTEGER, SQL_REAL, SQL_SMALLINT, SQL_VARCHAR and SQL_DATETIME.</span></span></p></td>
</tr>
</tbody>
</table>

