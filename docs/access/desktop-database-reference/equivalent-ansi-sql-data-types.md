---
title: 等价的 ANSI SQL 数据类型
TOCTitle: Equivalent ANSI SQL Data Types
ms:assetid: 720abf59-f9ef-4e14-4223-c873f604ad58
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195814(v=office.15)
ms:contentKeyID: 48545599
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277587
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ed13aab8d1f6851dd05ea2d79877e34c14665a3f
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937160"
---
# <a name="equivalent-ansi-sql-data-types"></a><span data-ttu-id="129ad-102">等价的 ANSI SQL 数据类型</span><span class="sxs-lookup"><span data-stu-id="129ad-102">Equivalent ANSI SQL Data Types</span></span>


<span data-ttu-id="129ad-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="129ad-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="129ad-104">下表列出了 ANSI SQL 数据类型、它们的等价 Microsoft Access 数据库引擎 SQL 数据类型及其有效的同义词。</span><span class="sxs-lookup"><span data-stu-id="129ad-104">The following table lists ANSI SQL data types, their equivalent Microsoft Access database engine SQL data types, and their valid synonyms.</span></span> <span data-ttu-id="129ad-105">它还列出了等效 Microsoft SQL Server™ 数据类型。</span><span class="sxs-lookup"><span data-stu-id="129ad-105">It also lists the equivalent Microsoft SQL Server™ data types.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="129ad-106">ANSI SQL 数据类型</span><span class="sxs-lookup"><span data-stu-id="129ad-106">ANSI SQL data type</span></span></p></th>
<th><p><span data-ttu-id="129ad-107">Microsoft Access SQL 数据类型</span><span class="sxs-lookup"><span data-stu-id="129ad-107">Microsoft Access SQL data type</span></span></p></th>
<th><p><span data-ttu-id="129ad-108">
同义词</span><span class="sxs-lookup"><span data-stu-id="129ad-108">Synonym</span></span></p></th>
<th><p><span data-ttu-id="129ad-109">Microsoft SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="129ad-109">Microsoft SQL Server data type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="129ad-110">BIT 和 BIT VARYING</span><span class="sxs-lookup"><span data-stu-id="129ad-110">BIT, BIT VARYING</span></span></p></td>
<td><p><span data-ttu-id="129ad-111">BINARY（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-111">BINARY (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-112">VARBINARY、 BINARY VARYING 和 BIT VARYING</span><span class="sxs-lookup"><span data-stu-id="129ad-112">VARBINARY, BINARY VARYING BIT VARYING</span></span></p></td>
<td><p><span data-ttu-id="129ad-113">BINARY 和 VARBINARY</span><span class="sxs-lookup"><span data-stu-id="129ad-113">BINARY, VARBINARY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-114">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-114">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-115">BIT（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-115">BIT (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-116">BOOLEAN、LOGICAL、LOGICAL1 和 YESNO</span><span class="sxs-lookup"><span data-stu-id="129ad-116">BOOLEAN, LOGICAL, LOGICAL1, YESNO</span></span></p></td>
<td><p><span data-ttu-id="129ad-117">BIT</span><span class="sxs-lookup"><span data-stu-id="129ad-117">BIT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-118">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-118">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-119">TINYINT</span><span class="sxs-lookup"><span data-stu-id="129ad-119">TINYINT</span></span></p></td>
<td><p><span data-ttu-id="129ad-120">INTEGER1 和 BYTE</span><span class="sxs-lookup"><span data-stu-id="129ad-120">INTEGER1, BYTE</span></span></p></td>
<td><p><span data-ttu-id="129ad-121">TINYINT</span><span class="sxs-lookup"><span data-stu-id="129ad-121">TINYINT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-122">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-122">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-123">COUNTER（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-123">COUNTER (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-124">AUTOINCREMENT</span><span class="sxs-lookup"><span data-stu-id="129ad-124">AUTOINCREMENT</span></span></p></td>
<td><p><span data-ttu-id="129ad-125">（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-125">(See Notes)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-126">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-126">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-127">MONEY</span><span class="sxs-lookup"><span data-stu-id="129ad-127">MONEY</span></span></p></td>
<td><p><span data-ttu-id="129ad-128">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="129ad-128">CURRENCY</span></span></p></td>
<td><p><span data-ttu-id="129ad-129">MONEY</span><span class="sxs-lookup"><span data-stu-id="129ad-129">MONEY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-130">DATE、TIME 和 TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="129ad-130">DATE, TIME, TIMESTAMP</span></span></p></td>
<td><p><span data-ttu-id="129ad-131">DATETIME</span><span class="sxs-lookup"><span data-stu-id="129ad-131">DATETIME</span></span></p></td>
<td><p><span data-ttu-id="129ad-132">DATE、 TIME （参见注意）</span><span class="sxs-lookup"><span data-stu-id="129ad-132">DATE, TIME (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-133">DATETIME</span><span class="sxs-lookup"><span data-stu-id="129ad-133">DATETIME</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-134">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-134">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-135">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="129ad-135">UNIQUEIDENTIFIER</span></span></p></td>
<td><p><span data-ttu-id="129ad-136">GUID</span><span class="sxs-lookup"><span data-stu-id="129ad-136">GUID</span></span></p></td>
<td><p><span data-ttu-id="129ad-137">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="129ad-137">UNIQUEIDENTIFIER</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-138">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="129ad-138">DECIMAL</span></span></p></td>
<td><p><span data-ttu-id="129ad-139">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="129ad-139">DECIMAL</span></span></p></td>
<td><p><span data-ttu-id="129ad-140">NUMERIC 和 DEC</span><span class="sxs-lookup"><span data-stu-id="129ad-140">NUMERIC, DEC</span></span></p></td>
<td><p><span data-ttu-id="129ad-141">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="129ad-141">DECIMAL</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-142">REAL</span><span class="sxs-lookup"><span data-stu-id="129ad-142">REAL</span></span></p></td>
<td><p><span data-ttu-id="129ad-143">REAL</span><span class="sxs-lookup"><span data-stu-id="129ad-143">REAL</span></span></p></td>
<td><p><span data-ttu-id="129ad-144">SINGLE、FLOAT4 和 IEEESINGLE</span><span class="sxs-lookup"><span data-stu-id="129ad-144">SINGLE, FLOAT4, IEEESINGLE</span></span></p></td>
<td><p><span data-ttu-id="129ad-145">REAL</span><span class="sxs-lookup"><span data-stu-id="129ad-145">REAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-146">DOUBLE PRECISION 和 FLOAT</span><span class="sxs-lookup"><span data-stu-id="129ad-146">DOUBLE PRECISION, FLOAT</span></span></p></td>
<td><p><span data-ttu-id="129ad-147">FLOAT</span><span class="sxs-lookup"><span data-stu-id="129ad-147">FLOAT</span></span></p></td>
<td><p><span data-ttu-id="129ad-148">DOUBLE、FLOAT8、IEEEDOUBLE 和 NUMBER（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-148">DOUBLE, FLOAT8, IEEEDOUBLE, NUMBER (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-149">FLOAT</span><span class="sxs-lookup"><span data-stu-id="129ad-149">FLOAT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-150">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="129ad-150">SMALLINT</span></span></p></td>
<td><p><span data-ttu-id="129ad-151">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="129ad-151">SMALLINT</span></span></p></td>
<td><p><span data-ttu-id="129ad-152">SHORT 和 INTEGER2</span><span class="sxs-lookup"><span data-stu-id="129ad-152">SHORT, INTEGER2</span></span></p></td>
<td><p><span data-ttu-id="129ad-153">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="129ad-153">SMALLINT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-154">INTEGER</span><span class="sxs-lookup"><span data-stu-id="129ad-154">INTEGER</span></span></p></td>
<td><p><span data-ttu-id="129ad-155">INTEGER</span><span class="sxs-lookup"><span data-stu-id="129ad-155">INTEGER</span></span></p></td>
<td><p><span data-ttu-id="129ad-156">LONG、INT 和 INTEGER4</span><span class="sxs-lookup"><span data-stu-id="129ad-156">LONG, INT, INTEGER4</span></span></p></td>
<td><p><span data-ttu-id="129ad-157">INTEGER</span><span class="sxs-lookup"><span data-stu-id="129ad-157">INTEGER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-158">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="129ad-158">INTERVAL</span></span></p></td>
<td><p><span data-ttu-id="129ad-159">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-159">Not supported</span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="129ad-160">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-160">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-161">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-161">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-162">IMAGE</span><span class="sxs-lookup"><span data-stu-id="129ad-162">IMAGE</span></span></p></td>
<td><p><span data-ttu-id="129ad-163">LONGBINARY、 GENERAL 和 OLEOBJECT</span><span class="sxs-lookup"><span data-stu-id="129ad-163">LONGBINARY, GENERAL, OLEOBJECT</span></span></p></td>
<td><p><span data-ttu-id="129ad-164">IMAGE</span><span class="sxs-lookup"><span data-stu-id="129ad-164">IMAGE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="129ad-165">不支持</span><span class="sxs-lookup"><span data-stu-id="129ad-165">Not supported</span></span></p></td>
<td><p><span data-ttu-id="129ad-166">文本 （参见注意）</span><span class="sxs-lookup"><span data-stu-id="129ad-166">TEXT (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-167">LONGTEXT、LONGCHAR、MEMO、NOTE 和 NTEXT（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-167">LONGTEXT, LONGCHAR, MEMO, NOTE, NTEXT (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-168">TEXT</span><span class="sxs-lookup"><span data-stu-id="129ad-168">TEXT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="129ad-169">CHARACTER、CHARACTER VARYING、NATIONAL CHARACTER 和 NATIONAL CHARACTER VARYING</span><span class="sxs-lookup"><span data-stu-id="129ad-169">CHARACTER, CHARACTER VARYING, NATIONAL CHARACTER, NATIONAL CHARACTER VARYING</span></span></p></td>
<td><p><span data-ttu-id="129ad-170">CHAR（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="129ad-170">CHAR (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-171">TEXT(n)，ALPHANUMERIC、 CHARACTER、 STRING、 VARCHAR、 CHARACTER VARYING、 NCHAR、 NATIONAL CHARACTER、 NATIONAL CHAR、 NATIONAL CHARACTER VARYING、 NATIONAL CHAR VARYING （参见注意）</span><span class="sxs-lookup"><span data-stu-id="129ad-171">TEXT(n), ALPHANUMERIC, CHARACTER, STRING, VARCHAR, CHARACTER VARYING, NCHAR, NATIONAL CHARACTER, NATIONAL CHAR, NATIONAL CHARACTER VARYING, NATIONAL CHAR VARYING (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="129ad-172">CHAR、VARCHAR、NCHAR 和 NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="129ad-172">CHAR, VARCHAR, NCHAR, NVARCHAR</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> - <span data-ttu-id="129ad-p102">ANSI SQL BIT 数据类型不对应于 Microsoft Access SQL BIT 数据类型。但它对应于 BINARY 数据类型。不存在等价于 Microsoft Access SQL BIT 数据类型的 ANSI SQL 数据类型。</span><span class="sxs-lookup"><span data-stu-id="129ad-p102">The ANSI SQL BIT data type does not correspond to the Microsoft Access SQL BIT data type. It corresponds to the BINARY data type instead. There is no ANSI SQL equivalent for the Microsoft Access SQL BIT data type.</span></span>
> - <span data-ttu-id="129ad-176">不再支持 TIMESTAMP 作为 DATETIME 的同义词。</span><span class="sxs-lookup"><span data-stu-id="129ad-176">TIMESTAMP is no longer supported as a synonym for DATETIME.</span></span>
> - <span data-ttu-id="129ad-p103">不再支持 NUMERIC 作为 FLOAT 或 DOUBLE 的同义词。现在，NUMERIC 可作为 DECIMAL 的同义词使用。</span><span class="sxs-lookup"><span data-stu-id="129ad-p103">NUMERIC is no longer supported as a synonym for FLOAT or DOUBLE. NUMERIC is now used as a synonym for DECIMAL.</span></span>
> - <span data-ttu-id="129ad-179">LONGTEXT 字段总是存储为 Unicode 表示格式。</span><span class="sxs-lookup"><span data-stu-id="129ad-179">A LONGTEXT field is always stored in the Unicode representation format.</span></span>
> - <span data-ttu-id="129ad-p104">如果使用数据类型名称 TEXT，但未指定可选长度，例如 TEXT(25)，将创建一个 LONGTEXT 字段。这样使要编写的 [CREATE TABLE 语句](create-table-statement-microsoft-access-sql.md)生成的数据类型与 Microsoft SQL Server 一致。</span><span class="sxs-lookup"><span data-stu-id="129ad-p104">If the data type name TEXT is used without specifying the optional length, for example TEXT(25), a LONGTEXT field is created. This enables [CREATE TABLE statements](create-table-statement-microsoft-access-sql.md) to be written that will yield data types consistent with Microsoft SQL Server.</span></span>
> - <span data-ttu-id="129ad-182">CHAR 字段总是存储为 Unicode 表示格式，它等价于 ANSI SQL NATIONAL CHAR 数据类型。</span><span class="sxs-lookup"><span data-stu-id="129ad-182">A CHAR field is always stored in the Unicode representation format, which is the equivalent of the ANSI SQL NATIONAL CHAR data type.</span></span>
> - <span data-ttu-id="129ad-p105">如果使用数据类型名称 TEXT，但未指定可选长度，例如 TEXT(25)，那么该字段的数据类型等价于 CHAR 数据类型。这样，可保持大多数 Microsoft Jet 应用程序的后向兼容性，同时使 TEXT 数据类型（没有长度限制）符合 Microsoft SQL Server 规范。</span><span class="sxs-lookup"><span data-stu-id="129ad-p105">If the data type name TEXT is used and the optional length is specified, for example TEXT(25), the data type of the field is equivalent to the CHAR data type. This preserves backwards compatibility for most Microsoft Jet applications, while enabling the TEXT data type (without a length specification) to be aligned with Microsoft SQL Server.</span></span>


