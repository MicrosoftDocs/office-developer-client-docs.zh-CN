---
title: 聚合函数、CALC 函数和 NEW 关键字
TOCTitle: Aggregate Functions, the CALC Function, and the NEW Keyword
ms:assetid: c91fef19-bf41-8d04-f195-5470fb18393f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249977(v=office.15)
ms:contentKeyID: 48547669
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3616ab20e1d1f6a5d80c70f90a90ad13b3abc0fb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466409"
---
# <a name="aggregate-functions-the-calc-function-and-the-new-keyword"></a><span data-ttu-id="daf83-102">聚合函数、CALC 函数和 NEW 关键字</span><span class="sxs-lookup"><span data-stu-id="daf83-102">Aggregate Functions, the CALC Function, and the NEW Keyword</span></span>


<span data-ttu-id="daf83-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="daf83-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="daf83-p101">数据定形支持以下函数。分配给包含作为操作对象的列的章节的名称是 *chapter-alias*。</span><span class="sxs-lookup"><span data-stu-id="daf83-p101">Data shaping supports the following functions. The name assigned to the chapter containing the column to be operated on is the *chapter-alias*.</span></span>

<span data-ttu-id="daf83-p102">章节别名可以是完全限定名称，由指向包含 *column-name* 的章节的各章节列名组成，各部分均由句点分隔。例如，如果父章节 chap1 包含子章节 chap2，而后者具有一个数量列 amt，则限定名称为 chap1.chap2.amt。</span><span class="sxs-lookup"><span data-stu-id="daf83-p102">A chapter-alias may be fully qualified, consisting of each chapter column name leading to the chapter containing the *column-name,* all separated by periods. For example, if the parent chapter, chap1, contains a child chapter, chap2, that has an amount column, amt, then the qualified name would be chap1.chap2.amt.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daf83-108">聚合函数</span><span class="sxs-lookup"><span data-stu-id="daf83-108">Aggregate Functions</span></span></p></th>
<th><p><span data-ttu-id="daf83-109">说明</span><span class="sxs-lookup"><span data-stu-id="daf83-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daf83-110">SUM (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-110">SUM(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-111">计算指定列中所有值之和。</span><span class="sxs-lookup"><span data-stu-id="daf83-111">Calculates the sum of all values in the specified column.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-112">平均 (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-112">AVG(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-113">计算指定列中所有值的平均值。</span><span class="sxs-lookup"><span data-stu-id="daf83-113">Calculates the average of all values in the specified column.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-114">最大值 (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-114">MAX(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-115">计算指定列中的最大值。</span><span class="sxs-lookup"><span data-stu-id="daf83-115">Calculates the maximum value in the specified column.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-116">MIN (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-116">MIN(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-117">计算指定列中的最小值。</span><span class="sxs-lookup"><span data-stu-id="daf83-117">Calculates the minimum value in the specified column.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-118">计数 (<em>章节别名</em>[。<em>列名称</em>])</span><span class="sxs-lookup"><span data-stu-id="daf83-118">COUNT(<em>chapter-alias</em>[.<em>column-name</em>])</span></span></p></td>
<td><p><span data-ttu-id="daf83-p103">计算指定别名中的行数。如果指定了某列，则仅计算列值非空的行。</span><span class="sxs-lookup"><span data-stu-id="daf83-p103">Counts the number of rows in the specified alias. If a column is specified, only rows for which that column is non-Null are included in the count.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-121">STDEV (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-121">STDEV(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-122">计算指定列中的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="daf83-122">Calculates the standard deviation in the specified column.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-123">任何 (<em>章节别名</em>。<em>列名称</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-123">ANY(<em>chapter-alias</em>.<em>column-name</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-p104">指定列的值。只有对于章节中所有行该列的值都相同时，ANY 才具有可预测的值。
</span><span class="sxs-lookup"><span data-stu-id="daf83-p104">A value of the specified column. ANY has a predictable value only when the value of the column is the same for all rows in the chapter.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="daf83-126">如果对于章节中所有行，该列的值不同，则 SHAPE 命令会任意返回一个值作为 ANY 函数的值。</span><span class="sxs-lookup"><span data-stu-id="daf83-126">If the column does not contain the same value for all of the rows in the chapter, the SHAPE command arbitrarily returns one of the values to be the value of the ANY function.</span></span></P>


<p></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daf83-127">计算表达式</span><span class="sxs-lookup"><span data-stu-id="daf83-127">Calculated expression</span></span></p></th>
<th><p><span data-ttu-id="daf83-128">说明</span><span class="sxs-lookup"><span data-stu-id="daf83-128">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daf83-129">CALC(<em>expression</em>)</span><span class="sxs-lookup"><span data-stu-id="daf83-129">CALC(<em>expression</em>)</span></span></p></td>
<td><p><span data-ttu-id="daf83-p105">计算任意表达式，但只作用于包含 CALC 函数的 <strong>Recordset</strong> 的行。允许使用这些 <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications (VBA) 函数</a>的任意表达式。</span><span class="sxs-lookup"><span data-stu-id="daf83-p105">Calculates an arbitrary expression, but only on the row of the <strong>Recordset</strong> containing the CALC function. Any expression using these <a href="visual-basic-for-applications-functions.md">Visual Basic for Applications (VBA) Functions</a> is allowed.</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daf83-132">NEW 关键字</span><span class="sxs-lookup"><span data-stu-id="daf83-132">NEW keyword</span></span></p></th>
<th><p><span data-ttu-id="daf83-133">说明</span><span class="sxs-lookup"><span data-stu-id="daf83-133">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daf83-134">新<em>字段类型</em>[(<em>宽度</em> | <em>刻度</em> | <em>精度</em> | <em>错误</em>[，<em>扩展</em> | <em>错误</em>])]</span><span class="sxs-lookup"><span data-stu-id="daf83-134">NEW <em>field-type</em> [(<em>width</em> | <em>scale</em> | <em>precision</em> | <em>error</em> [, <em>scale</em> | <em>error</em>])]</span></span></p></td>
<td><p><span data-ttu-id="daf83-135">向 <strong>Recordset</strong> 添加指定类型的空列。</span><span class="sxs-lookup"><span data-stu-id="daf83-135">Adds an empty column of the specified type to the <strong>Recordset</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="daf83-136">随 NEW 关键字传递的 *field-type* 可以是以下任意数据类型。</span><span class="sxs-lookup"><span data-stu-id="daf83-136">The *field-type* passed with the NEW keyword can be any of the following data types.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="daf83-137">OLE DB 数据类型</span><span class="sxs-lookup"><span data-stu-id="daf83-137">OLE DB data types</span></span></p></th>
<th><p><span data-ttu-id="daf83-138">等效的 ADO 数据类型</span><span class="sxs-lookup"><span data-stu-id="daf83-138">ADO data type equivalent(s)</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daf83-139">DBTYPE_BSTR</span><span class="sxs-lookup"><span data-stu-id="daf83-139">DBTYPE_BSTR</span></span></p></td>
<td><p><span data-ttu-id="daf83-140">adBSTR</span><span class="sxs-lookup"><span data-stu-id="daf83-140">adBSTR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-141">DBTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="daf83-141">DBTYPE_BOOL</span></span></p></td>
<td><p><span data-ttu-id="daf83-142">adBoolean</span><span class="sxs-lookup"><span data-stu-id="daf83-142">adBoolean</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-143">为 DBTYPE_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="daf83-143">DBTYPE_DECIMAL</span></span></p></td>
<td><p><span data-ttu-id="daf83-144">为 adDecimal</span><span class="sxs-lookup"><span data-stu-id="daf83-144">adDecimal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-145">DBTYPE_UI1</span><span class="sxs-lookup"><span data-stu-id="daf83-145">DBTYPE_UI1</span></span></p></td>
<td><p><span data-ttu-id="daf83-146">adUnsignedTinyInt</span><span class="sxs-lookup"><span data-stu-id="daf83-146">adUnsignedTinyInt</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-147">DBTYPE_I1</span><span class="sxs-lookup"><span data-stu-id="daf83-147">DBTYPE_I1</span></span></p></td>
<td><p><span data-ttu-id="daf83-148">adTinyInt</span><span class="sxs-lookup"><span data-stu-id="daf83-148">adTinyInt</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-149">DBTYPE_UI2</span><span class="sxs-lookup"><span data-stu-id="daf83-149">DBTYPE_UI2</span></span></p></td>
<td><p><span data-ttu-id="daf83-150">adUnsignedSmallInt</span><span class="sxs-lookup"><span data-stu-id="daf83-150">adUnsignedSmallInt</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-151">DBTYPE_UI4</span><span class="sxs-lookup"><span data-stu-id="daf83-151">DBTYPE_UI4</span></span></p></td>
<td><p><span data-ttu-id="daf83-152">adUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="daf83-152">adUnsignedInt</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-153">DBTYPE_I8</span><span class="sxs-lookup"><span data-stu-id="daf83-153">DBTYPE_I8</span></span></p></td>
<td><p><span data-ttu-id="daf83-154">adBigInt</span><span class="sxs-lookup"><span data-stu-id="daf83-154">adBigInt</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-155">DBTYPE_UI8</span><span class="sxs-lookup"><span data-stu-id="daf83-155">DBTYPE_UI8</span></span></p></td>
<td><p><span data-ttu-id="daf83-156">adUnsignedBigInt</span><span class="sxs-lookup"><span data-stu-id="daf83-156">adUnsignedBigInt</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-157">DBTYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="daf83-157">DBTYPE_GUID</span></span></p></td>
<td><p><span data-ttu-id="daf83-158">adGuid</span><span class="sxs-lookup"><span data-stu-id="daf83-158">adGuid</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-159">DBTYPE_BYTES</span><span class="sxs-lookup"><span data-stu-id="daf83-159">DBTYPE_BYTES</span></span></p></td>
<td><p><span data-ttu-id="daf83-160">adBinary，感，adLongVarBinary</span><span class="sxs-lookup"><span data-stu-id="daf83-160">adBinary, AdVarBinary, adLongVarBinary</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-161">DBTYPE_STR</span><span class="sxs-lookup"><span data-stu-id="daf83-161">DBTYPE_STR</span></span></p></td>
<td><p><span data-ttu-id="daf83-162">每，以便您可以排除 adLongVarChar</span><span class="sxs-lookup"><span data-stu-id="daf83-162">adChar, adVarChar, adLongVarChar</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-163">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="daf83-163">DBTYPE_WSTR</span></span></p></td>
<td><p><span data-ttu-id="daf83-164">adWChar，adVarWChar adLongVarWChar</span><span class="sxs-lookup"><span data-stu-id="daf83-164">adWChar, adVarWChar, adLongVarWChar</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-165">DBTYPE_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="daf83-165">DBTYPE_NUMERIC</span></span></p></td>
<td><p><span data-ttu-id="daf83-166">adNumeric</span><span class="sxs-lookup"><span data-stu-id="daf83-166">adNumeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-167">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="daf83-167">DBTYPE_DBDATE</span></span></p></td>
<td><p><span data-ttu-id="daf83-168">adDBDate</span><span class="sxs-lookup"><span data-stu-id="daf83-168">adDBDate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-169">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="daf83-169">DBTYPE_DBTIME</span></span></p></td>
<td><p><span data-ttu-id="daf83-170">adDBTime</span><span class="sxs-lookup"><span data-stu-id="daf83-170">adDBTime</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-171">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="daf83-171">DBTYPE_DBTIMESTAMP</span></span></p></td>
<td><p><span data-ttu-id="daf83-172">adDBTimeStamp</span><span class="sxs-lookup"><span data-stu-id="daf83-172">adDBTimeStamp</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-173">DBTYPE_VARNUMERIC</span><span class="sxs-lookup"><span data-stu-id="daf83-173">DBTYPE_VARNUMERIC</span></span></p></td>
<td><p><span data-ttu-id="daf83-174">adVarNumeric</span><span class="sxs-lookup"><span data-stu-id="daf83-174">adVarNumeric</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf83-175">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="daf83-175">DBTYPE_FILETIME</span></span></p></td>
<td><p><span data-ttu-id="daf83-176">adFileTime</span><span class="sxs-lookup"><span data-stu-id="daf83-176">adFileTime</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf83-177">DBTYPE_ERROR</span><span class="sxs-lookup"><span data-stu-id="daf83-177">DBTYPE_ERROR</span></span></p></td>
<td><p><span data-ttu-id="daf83-178">adError</span><span class="sxs-lookup"><span data-stu-id="daf83-178">adError</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="daf83-179">当新字段为小数类型 (在 OLE DB 中 DBTYPE\_小数，或在 ADO 中为 adDecimal)，您必须指定精度和刻度值。</span><span class="sxs-lookup"><span data-stu-id="daf83-179">When the new field is of type decimal (in OLE DB, DBTYPE\_DECIMAL, or in ADO, adDecimal), you must specify the precision and scale values.</span></span>
