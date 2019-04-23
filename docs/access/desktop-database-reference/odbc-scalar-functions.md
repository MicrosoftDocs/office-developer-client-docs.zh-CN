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
# <a name="odbc-scalar-functions"></a><span data-ttu-id="bef48-102">ODBC Scalar 函数</span><span class="sxs-lookup"><span data-stu-id="bef48-102">ODBC scalar functions</span></span>

<span data-ttu-id="bef48-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bef48-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bef48-104">Microsoft Access SQL 支持对标量函数使用 ODBC 定义的语法。</span><span class="sxs-lookup"><span data-stu-id="bef48-104">Microsoft Access SQL supports the use of the ODBC defined syntax for scalar functions.</span></span> 

<span data-ttu-id="bef48-105">例如, 该查询`SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} > 5`将返回股票价格中的绝对值超过五个的所有行。</span><span class="sxs-lookup"><span data-stu-id="bef48-105">For example, the query `SELECT DAILYCLOSE, DAILYCHANGE FROM DAILYQUOTE WHERE {fn ABS(DAILYCHANGE)} > 5` would return all rows where the absolute value of the change in the price of a stock was greater than five.</span></span>

<span data-ttu-id="bef48-p101">可支持 ODBC 定义的标量函数的子集。下表列出了支持的函数。</span><span class="sxs-lookup"><span data-stu-id="bef48-p101">A subset of the ODBC defined scalar functions is supported. The following table lists the functions that are supported.</span></span>

<span data-ttu-id="bef48-108">关于参数的说明以及在 SQL 语句中包括函数的转义语法的完整说明，请参阅 ODBC 文档。</span><span class="sxs-lookup"><span data-stu-id="bef48-108">For a description of the arguments and a complete explanation of the escape syntax for including functions in a SQL statement, see the ODBC documentation.</span></span>

## <a name="string-functions"></a><span data-ttu-id="bef48-109">String 函数</span><span class="sxs-lookup"><span data-stu-id="bef48-109">String functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bef48-110">ASCII</span><span class="sxs-lookup"><span data-stu-id="bef48-110">ASCII</span></span></p></td>
<td><p><span data-ttu-id="bef48-111">段</span><span class="sxs-lookup"><span data-stu-id="bef48-111">LENGTH</span></span></p></td>
<td><p><span data-ttu-id="bef48-112">RTRIM</span><span class="sxs-lookup"><span data-stu-id="bef48-112">RTRIM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-113">资料</span><span class="sxs-lookup"><span data-stu-id="bef48-113">CHAR</span></span></p></td>
<td><p><span data-ttu-id="bef48-114">找</span><span class="sxs-lookup"><span data-stu-id="bef48-114">LOCATE</span></span></p></td>
<td><p><span data-ttu-id="bef48-115">SPACE</span><span class="sxs-lookup"><span data-stu-id="bef48-115">SPACE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-116">串联</span><span class="sxs-lookup"><span data-stu-id="bef48-116">CONCAT</span></span></p></td>
<td><p><span data-ttu-id="bef48-117">LTRIM</span><span class="sxs-lookup"><span data-stu-id="bef48-117">LTRIM</span></span></p></td>
<td><p><span data-ttu-id="bef48-118">取</span><span class="sxs-lookup"><span data-stu-id="bef48-118">SUBSTRING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-119">LCASE</span><span class="sxs-lookup"><span data-stu-id="bef48-119">LCASE</span></span></p></td>
<td><p><span data-ttu-id="bef48-120">左向右</span><span class="sxs-lookup"><span data-stu-id="bef48-120">RIGHT</span></span></p></td>
<td><p><span data-ttu-id="bef48-121">UCASE</span><span class="sxs-lookup"><span data-stu-id="bef48-121">UCASE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-122">左至右</span><span class="sxs-lookup"><span data-stu-id="bef48-122">LEFT</span></span></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="numeric-functions"></a><span data-ttu-id="bef48-123">数值函数</span><span class="sxs-lookup"><span data-stu-id="bef48-123">Numeric functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bef48-124">ABS</span><span class="sxs-lookup"><span data-stu-id="bef48-124">ABS</span></span></p></td>
<td><p><span data-ttu-id="bef48-125">图</span><span class="sxs-lookup"><span data-stu-id="bef48-125">FLOOR</span></span></p></td>
<td><p><span data-ttu-id="bef48-126">SIN</span><span class="sxs-lookup"><span data-stu-id="bef48-126">SIN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-127">ATAN</span><span class="sxs-lookup"><span data-stu-id="bef48-127">ATAN</span></span></p></td>
<td><p><span data-ttu-id="bef48-128">.log</span><span class="sxs-lookup"><span data-stu-id="bef48-128">LOG</span></span></p></td>
<td><p><span data-ttu-id="bef48-129">SQRT</span><span class="sxs-lookup"><span data-stu-id="bef48-129">SQRT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-130">向上</span><span class="sxs-lookup"><span data-stu-id="bef48-130">CEILING</span></span></p></td>
<td><p><span data-ttu-id="bef48-131">能力</span><span class="sxs-lookup"><span data-stu-id="bef48-131">POWER</span></span></p></td>
<td><p><span data-ttu-id="bef48-132">TAN</span><span class="sxs-lookup"><span data-stu-id="bef48-132">TAN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-133">COS</span><span class="sxs-lookup"><span data-stu-id="bef48-133">COS</span></span></p></td>
<td><p><span data-ttu-id="bef48-134">多次</span><span class="sxs-lookup"><span data-stu-id="bef48-134">RAND</span></span></p></td>
<td><p><span data-ttu-id="bef48-135">模块</span><span class="sxs-lookup"><span data-stu-id="bef48-135">MOD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-136">过期</span><span class="sxs-lookup"><span data-stu-id="bef48-136">EXP</span></span></p></td>
<td><p><span data-ttu-id="bef48-137">记号</span><span class="sxs-lookup"><span data-stu-id="bef48-137">SIGN</span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="time--date-functions"></a><span data-ttu-id="bef48-138">时间 & 日期函数</span><span class="sxs-lookup"><span data-stu-id="bef48-138">Time & Date functions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bef48-139">CURDATE</span><span class="sxs-lookup"><span data-stu-id="bef48-139">CURDATE</span></span></p></td>
<td><p><span data-ttu-id="bef48-140">DAYOFYEAR</span><span class="sxs-lookup"><span data-stu-id="bef48-140">DAYOFYEAR</span></span></p></td>
<td><p><span data-ttu-id="bef48-141">本月</span><span class="sxs-lookup"><span data-stu-id="bef48-141">MONTH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-142">CURTIME</span><span class="sxs-lookup"><span data-stu-id="bef48-142">CURTIME</span></span></p></td>
<td><p><span data-ttu-id="bef48-143">本年</span><span class="sxs-lookup"><span data-stu-id="bef48-143">YEAR</span></span></p></td>
<td><p><span data-ttu-id="bef48-144">周</span><span class="sxs-lookup"><span data-stu-id="bef48-144">WEEK</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-145">已经</span><span class="sxs-lookup"><span data-stu-id="bef48-145">NOW</span></span></p></td>
<td><p><span data-ttu-id="bef48-146">七点</span><span class="sxs-lookup"><span data-stu-id="bef48-146">HOUR</span></span></p></td>
<td><p><span data-ttu-id="bef48-147">结算</span><span class="sxs-lookup"><span data-stu-id="bef48-147">QUARTER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bef48-148">DAYOFMONTH</span><span class="sxs-lookup"><span data-stu-id="bef48-148">DAYOFMONTH</span></span></p></td>
<td><p><span data-ttu-id="bef48-149">还要</span><span class="sxs-lookup"><span data-stu-id="bef48-149">MINUTE</span></span></p></td>
<td><p><span data-ttu-id="bef48-150">MONTHNAME</span><span class="sxs-lookup"><span data-stu-id="bef48-150">MONTHNAME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bef48-151">DAYOFWEEK</span><span class="sxs-lookup"><span data-stu-id="bef48-151">DAYOFWEEK</span></span></p></td>
<td><p><span data-ttu-id="bef48-152">第二个</span><span class="sxs-lookup"><span data-stu-id="bef48-152">SECOND</span></span></p></td>
<td><p><span data-ttu-id="bef48-153">DAYNAME</span><span class="sxs-lookup"><span data-stu-id="bef48-153">DAYNAME</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="data-type-conversion"></a><span data-ttu-id="bef48-154">数据类型转换</span><span class="sxs-lookup"><span data-stu-id="bef48-154">Data type conversion</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bef48-155">转换</span><span class="sxs-lookup"><span data-stu-id="bef48-155">CONVERT</span></span></p></td>
<td><p><span data-ttu-id="bef48-156">字面字符串可以转换成以下数据类型：SQL_FLOAT、SQL_DOUBLE、SQL_NUMERIC、SQL_INTEGER、SQL_REAL、SQL_SMALLINT、SQL_VARCHAR 和 SQL_DATETIME。</span><span class="sxs-lookup"><span data-stu-id="bef48-156">String literals can be converted to the following data types: SQL_FLOAT, SQL_DOUBLE, SQL_NUMERIC, SQL_INTEGER, SQL_REAL, SQL_SMALLINT, SQL_VARCHAR and SQL_DATETIME.</span></span></p></td>
</tr>
</tbody>
</table>

