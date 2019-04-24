---
title: Microsoft Access SQL 和 ANSI SQL 的比较
TOCTitle: Comparison of Microsoft Access SQL and ANSI SQL
ms:assetid: 0686f98f-10fe-0e02-e9d1-84ff3e755b57
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844937(v=office.15)
ms:contentKeyID: 48543052
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 195d9f5d882fd252b1b10e937fe851c4830c52d3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296050"
---
# <a name="comparison-of-microsoft-access-sql-and-ansi-sql"></a><span data-ttu-id="91c7d-102">比较 Microsoft Access SQL 和 ANSI SQL</span><span class="sxs-lookup"><span data-stu-id="91c7d-102">Comparison of Microsoft Access SQL and ANSI SQL</span></span>

<span data-ttu-id="91c7d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="91c7d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="91c7d-104">Microsoft Access 数据库引擎 SQL 的兼容性通常为 ANSI-89 级别1。</span><span class="sxs-lookup"><span data-stu-id="91c7d-104">Microsoft Access database engine SQL is generally ANSI-89 Level 1 compliant.</span></span> <span data-ttu-id="91c7d-105">但是, 某些 ANSI SQL 功能未在 Microsoft Access SQL 中实现。</span><span class="sxs-lookup"><span data-stu-id="91c7d-105">However, certain ANSI SQL features are not implemented in Microsoft Access SQL.</span></span> <span data-ttu-id="91c7d-106">相反, Microsoft Access SQL 包含 ANSI SQL 中不支持的保留字和功能。</span><span class="sxs-lookup"><span data-stu-id="91c7d-106">Conversely, Microsoft Access SQL includes reserved words and features not supported in ANSI SQL.</span></span>

## <a name="major-differences"></a><span data-ttu-id="91c7d-107">主要差异</span><span class="sxs-lookup"><span data-stu-id="91c7d-107">Major differences</span></span>

- <span data-ttu-id="91c7d-p102">Microsoft Access SQL 和 ANSI SQL 各自拥有不同的保留字和数据类型。有关详细信息，请参阅 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)和[等价的 ANSI SQL 数据类型](equivalent-ansi-sql-data-types.md)。使用 Microsoft Access 数据库引擎 OLE DB 提供程序时，还提供其他保留字。</span><span class="sxs-lookup"><span data-stu-id="91c7d-p102">Microsoft Access SQL and ANSI SQL each have different reserved words and data types. For more information, see [Microsoft Access Database Engine SQL Reserved Words](sql-reserved-words.md) and [Equivalent ANSI SQL Data Types](equivalent-ansi-sql-data-types.md). Using the Microsoft Access Database Engine OLE DB Provider there are additional reserved words.</span></span>

- <span data-ttu-id="91c7d-111">**[Between...And](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**</span><span class="sxs-lookup"><span data-stu-id="91c7d-111">**[Between…And](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/and-operator)**</span></span>
    
  <span data-ttu-id="91c7d-112">*表达式 1*\[不\] **介于** *value1* **和** *value2*之间</span><span class="sxs-lookup"><span data-stu-id="91c7d-112">*expr1* \[NOT\] **Between** *value1* **And** *value2*</span></span>
    
  <span data-ttu-id="91c7d-113">在 Microsoft Access SQL 中，*value1* 可以大于 *value2*；在 ANSI SQL 中，*value1* 必须小于或等于 *value2*。</span><span class="sxs-lookup"><span data-stu-id="91c7d-113">In Microsoft Access SQL, *value1* can be greater than *value2*; in ANSI SQL, *value1* must be equal to or less than *value2.*</span></span>

- <span data-ttu-id="91c7d-p103">Microsoft Access SQL 既支持 ANSI SQL 通配符，也支持特定于 Microsoft Access 数据库引擎的[通配符](using-wildcard-characters-in-string-comparisons.md)以便与 **[Like](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)** 运算符配合使用。ANSI 和 Microsoft Access 数据库引擎通配符的使用是相互排斥的。必须使用其中一种而不能混合使用。ANSI SQL 通配符仅在使用 Microsoft Access 数据库引擎和 Microsoft Access 数据库引擎 OLE DB 提供程序时可用。如果试图通过 Microsoft Access 或者 DAO 来使用 ANSI SQL 通配符，则这些通配符将被解释为文本。相反，使用 Microsoft Access 数据库引擎 OLE DB 提供程序才能使用 ANSI SQL 通配符。</span><span class="sxs-lookup"><span data-stu-id="91c7d-p103">Microsoft Access SQL supports both ANSI SQL wildcard characters and [wildcard characters](using-wildcard-characters-in-string-comparisons.md) that are specific to the Microsoft Access database engine to use with the **[Like](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/like-operator-microsoft-access-sql)** operator. The use of the ANSI and Microsoft Access database engine wildcard characters is mutually exclusive. You must use one set or the other and cannot mix them. The ANSI SQL wildcards are only available when using the Microsoft Access database engine and the Microsoft Access Database Engine OLE DB Provider. If you try to use the ANSI SQL wildcards through Microsoft Access or DAO, then they will be interpreted as literals. The opposite is true when using the Microsoft Access Database Engine OLE DB Provider.</span></span>
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><span data-ttu-id="91c7d-120">匹配字符</span><span class="sxs-lookup"><span data-stu-id="91c7d-120">Matching character</span></span></p></th>
    <th><p><span data-ttu-id="91c7d-121">Microsoft Access SQL</span><span class="sxs-lookup"><span data-stu-id="91c7d-121">Microsoft Access SQL</span></span></p></th>
    <th><p><span data-ttu-id="91c7d-122">ANSI SQL</span><span class="sxs-lookup"><span data-stu-id="91c7d-122">ANSI SQL</span></span></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="91c7d-123">任意单个字符</span><span class="sxs-lookup"><span data-stu-id="91c7d-123">Any single character</span></span></p></td>
    <td><p><span data-ttu-id="91c7d-124">?</span><span class="sxs-lookup"><span data-stu-id="91c7d-124"></span></span></p></td>
    <td><p><span data-ttu-id="91c7d-125">_（下划线）</span><span class="sxs-lookup"><span data-stu-id="91c7d-125">_ (underscore)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="91c7d-126">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="91c7d-126">Zero or more characters</span></span></p></td>
    <td><p>*</p></td>
    <td><p>%</p></td>
    </tr>
    </tbody>
    </table>


- <span data-ttu-id="91c7d-p104">Microsoft Access SQL 通常限制性很少。例如，它允许对表达式进行分组和排序。</span><span class="sxs-lookup"><span data-stu-id="91c7d-p104">Microsoft Access SQL is generally less restrictive. For example, it permits grouping and ordering on expressions.</span></span>

- <span data-ttu-id="91c7d-129">Microsoft Access SQL 支持更加强大的表达式。</span><span class="sxs-lookup"><span data-stu-id="91c7d-129">Microsoft Access SQL supports more powerful expressions.</span></span>

## <a name="enhanced-features-of-microsoft-access-sql"></a><span data-ttu-id="91c7d-130">Microsoft Access SQL 的增强功能</span><span class="sxs-lookup"><span data-stu-id="91c7d-130">Enhanced features of Microsoft Access SQL</span></span>

<span data-ttu-id="91c7d-131">Microsoft Access SQL 提供了以下增强功能：</span><span class="sxs-lookup"><span data-stu-id="91c7d-131">Microsoft Access SQL provides the following enhanced features:</span></span>

- <span data-ttu-id="91c7d-132">[TRANSFORM](transform-statement-microsoft-access-sql.md) 语句，它支持交叉表查询。</span><span class="sxs-lookup"><span data-stu-id="91c7d-132">The [TRANSFORM](transform-statement-microsoft-access-sql.md) statement, which provides support for crosstab queries.</span></span>

- <span data-ttu-id="91c7d-133">其他[聚合函数](sql-aggregate-functions-sql.md)，例如 **StDev** 和 **VarP** 。</span><span class="sxs-lookup"><span data-stu-id="91c7d-133">Additional [aggregate functions](sql-aggregate-functions-sql.md), such as **StDev** and **VarP**.</span></span>

- <span data-ttu-id="91c7d-134">[PARAMETERS](parameters-declaration-microsoft-access-sql.md) 声明，用于定义参数查询。</span><span class="sxs-lookup"><span data-stu-id="91c7d-134">The [PARAMETERS](parameters-declaration-microsoft-access-sql.md) declaration for defining parameter queries.</span></span>

## <a name="ansi-sql-features-not-supported-in-microsoft-access-sql"></a><span data-ttu-id="91c7d-135">Microsoft Access SQL 中不支持 ANSI SQL 功能</span><span class="sxs-lookup"><span data-stu-id="91c7d-135">ANSI SQL features not supported in Microsoft Access SQL</span></span>

<span data-ttu-id="91c7d-136">Microsoft Access SQL 不支持以下 ANSI SQL 功能：</span><span class="sxs-lookup"><span data-stu-id="91c7d-136">Microsoft Access SQL does not support the following ANSI SQL features:</span></span>

- <span data-ttu-id="91c7d-p105">DISTINCT 聚合函数引用。例如，Microsoft Access SQL 不允许 SUM(DISTINCT *columnname*)。</span><span class="sxs-lookup"><span data-stu-id="91c7d-p105">DISTINCT aggregate function references. For example, Microsoft Access SQL does not allow SUM(DISTINCT *columnname*).</span></span>

- <span data-ttu-id="91c7d-p106">用于限制查询返回的行数的 LIMIT TO *nn* ROWS 子句。只能使用 [WHERE 子句](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql)来限制查询的范围。</span><span class="sxs-lookup"><span data-stu-id="91c7d-p106">The LIMIT TO *nn* ROWS clause used to limit the number of rows returned by a query. You can use only the [WHERE clause](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql) to limit the scope of a query.</span></span>

