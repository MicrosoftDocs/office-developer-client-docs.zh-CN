---
title: PROCEDURE 子句 (Microsoft Access SQL)
TOCTitle: PROCEDURE clause (Microsoft Access SQL)
ms:assetid: a718802c-9260-88d5-ec29-d5e5594927b0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821342(v=office.15)
ms:contentKeyID: 48546872
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277578
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 72f31c71e710cca79695a7221f0e033d18d2f420
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301377"
---
# <a name="procedure-clause-microsoft-access-sql"></a><span data-ttu-id="c569f-102">PROCEDURE 子句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="c569f-102">PROCEDURE clause (Microsoft Access SQL)</span></span>

<span data-ttu-id="c569f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c569f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c569f-104">定义查询的名称和可选参数。</span><span class="sxs-lookup"><span data-stu-id="c569f-104">Defines a name and optional parameters for a query.</span></span>

> [!NOTE]
> <span data-ttu-id="c569f-p101">[!注释] PROCEDURE 子句已经被 PROCEDURE 语句所取代。虽然现在仍然支持 PROCEDURE 子句，但是 PROCEDURE 语句提供了兼容 PROCEDURE 子句的超集，并且它是推荐使用的语法。</span><span class="sxs-lookup"><span data-stu-id="c569f-p101">The PROCEDURE clause has been superseded by the PROCEDURE statement. Although the PROCEDURE clause is still supported, the PROCEDURE statement provides a superset of the capability of the PROCEDURE clause and is the recommended syntax.</span></span>

## <a name="syntax"></a><span data-ttu-id="c569f-107">语法</span><span class="sxs-lookup"><span data-stu-id="c569f-107">Syntax</span></span>

<span data-ttu-id="c569f-108">过程*名称* \[ *param1 datatype*\[, *param2 datatype*\[, .。。\]\]</span><span class="sxs-lookup"><span data-stu-id="c569f-108">PROCEDURE *name* \[*param1 datatype*\[, *param2 datatype*\[, …\]\]</span></span>

<span data-ttu-id="c569f-109">PROCEDURE 子句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="c569f-109">The PROCEDURE clause has these parts:</span></span>

|<span data-ttu-id="c569f-110">Part</span><span class="sxs-lookup"><span data-stu-id="c569f-110">Part</span></span> |<span data-ttu-id="c569f-111">说明</span><span class="sxs-lookup"><span data-stu-id="c569f-111">Description</span></span> |
|:----|:-----------|
|<span data-ttu-id="c569f-112">*name*</span><span class="sxs-lookup"><span data-stu-id="c569f-112">*name*</span></span> |<span data-ttu-id="c569f-113">过程名称。</span><span class="sxs-lookup"><span data-stu-id="c569f-113">A name for the procedure.</span></span> <span data-ttu-id="c569f-114">它必须遵循标准命名规则。</span><span class="sxs-lookup"><span data-stu-id="c569f-114">It must follow standard naming conventions.</span></span>|
|<span data-ttu-id="c569f-115">*param1*、 *param2*</span><span class="sxs-lookup"><span data-stu-id="c569f-115">*param1*, *param2*</span></span> |<span data-ttu-id="c569f-116">一个或多个字段名或者参数。</span><span class="sxs-lookup"><span data-stu-id="c569f-116">One or more field names or parameters.</span></span> <span data-ttu-id="c569f-117">例如：</span><span class="sxs-lookup"><span data-stu-id="c569f-117">For example:</span></span><br/><br/>`PROCEDURE Sales_By_Country [Beginning Date] DateTime, [Ending Date] DateTime;`<br/><br/><span data-ttu-id="c569f-118">有关参数的详细信息, 请参阅[parameters](parameters-declaration-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="c569f-118">For more information about parameters, see [parameters](parameters-declaration-microsoft-access-sql.md).</span></span>|
|<span data-ttu-id="c569f-119">*udt*</span><span class="sxs-lookup"><span data-stu-id="c569f-119">*datatype*</span></span> | <span data-ttu-id="c569f-120">主要 [Microsoft Access SQL 数据类型](sql-data-types.md)或其同义词之一。</span><span class="sxs-lookup"><span data-stu-id="c569f-120">One of the primary [Microsoft Access SQL data types](sql-data-types.md) or their synonyms.</span></span> |


## <a name="remarks"></a><span data-ttu-id="c569f-121">注解</span><span class="sxs-lookup"><span data-stu-id="c569f-121">Remarks</span></span>

<span data-ttu-id="c569f-122">SQL 过程由 PROCEDURE 子句（指定该过程的名称）、可选的参数定义列表和一个 SQL 语句组成。</span><span class="sxs-lookup"><span data-stu-id="c569f-122">An SQL procedure consists of a PROCEDURE clause (which specifies the name of the procedure), an optional list of parameter definitions, and a single SQL statement.</span></span> <span data-ttu-id="c569f-123">例如, 过程获取\_部件\_号可能会运行检索指定部件号的查询。</span><span class="sxs-lookup"><span data-stu-id="c569f-123">For example, the procedure Get\_Part\_Number might run a query that retrieves a specified part number.</span></span>

> [!NOTE]
> - <span data-ttu-id="c569f-124">如果子句包含多个字段定义（即有多个 *param-datatype* 对），请使用逗号分隔它们。</span><span class="sxs-lookup"><span data-stu-id="c569f-124">If the clause includes more than one field definition (that is, *param-datatype* pairs), separate them with commas.</span></span>
> - <span data-ttu-id="c569f-125">PROCEDURE 子句的后面必须跟随 SQL 语句（例如，[SELECT](select-statement-microsoft-access-sql.md) 或 [UPDATE](update-statement-microsoft-access-sql.md) 语句）。</span><span class="sxs-lookup"><span data-stu-id="c569f-125">The PROCEDURE clause must be followed by an SQL statement (for example, a [SELECT](select-statement-microsoft-access-sql.md) or [UPDATE](update-statement-microsoft-access-sql.md) statement).</span></span>

## <a name="example"></a><span data-ttu-id="c569f-126">示例</span><span class="sxs-lookup"><span data-stu-id="c569f-126">Example</span></span>

<span data-ttu-id="c569f-127">本示例将查询命名为 CategoryList, 并调用 EnumFields 过程, 您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="c569f-127">This example names the query CategoryList, and calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

```vb
    Sub ProcedureX() 
     
        Dim dbs As Database, rst As Recordset 
        Dim qdf As QueryDef, strSql As String 
         
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        strSql = "PROCEDURE CategoryList; " _ 
            & "SELECT DISTINCTROW CategoryName, " _ 
            & "CategoryID FROM Categories " _ 
            & "ORDER BY CategoryName;" 
         
        ' Create a named QueryDef based on the SQL 
        ' statement. 
        Set qdf = dbs.CreateQueryDef("NewQry", strSql) 
     
        ' Create a temporary snapshot-type Recordset. 
        Set rst = qdf.OpenRecordset(dbOpenSnapshot) 
     
        ' Populate the Recordset. 
        rst.MoveLast 
                 
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 15 
         
        ' Delete the QueryDef because this is a 
        ' demonstration. 
        dbs.QueryDefs.Delete "NewQry" 
         
        dbs.Close 
     
    End Sub
```
