---
title: CREATE PROCEDURE 语句 (Microsoft Access SQL)
TOCTitle: CREATE PROCEDURE statement (Microsoft Access SQL)
ms:assetid: 1fbb5267-9862-bfb4-6436-176152d7a6cd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845861(v=office.15)
ms:contentKeyID: 48543649
ms.date: 10/18/2018
mtps_version: v=office.15
dev_langs:
- sql
localization_priority: Priority
ms.openlocfilehash: f223e164bd36a6a1a76140a28dd57cd2005e4a20
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295400"
---
# <a name="create-procedure-statement-microsoft-access-sql"></a><span data-ttu-id="1b3a2-102">CREATE PROCEDURE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="1b3a2-102">CREATE PROCEDURE Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="1b3a2-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b3a2-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="1b3a2-104">创建存储过程。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-104">Creates a stored procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1b3a2-105">Microsoft Access 数据库引擎不支持对非 Microsoft Jet 数据库引擎的数据库使用 CREATE PROCEDURE 语句或者任何 DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-105">The Microsoft Access database engine does not support the use of CREATE PROCEDURE, or any of the DDL statements, with non-Microsoft Jet database engine databases.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b3a2-106">语法</span><span class="sxs-lookup"><span data-stu-id="1b3a2-106">Syntax</span></span>

<span data-ttu-id="1b3a2-107">CREATE PROCEDURE *procedure* \[*param1 datatype*\[, *param2 datatype*\[, …\]\] AS sqlstatement</span><span class="sxs-lookup"><span data-stu-id="1b3a2-107">CREATE PROCEDURE procedure
    [param1 datatype[, param2 datatype[, …]] AS sqlstatement</span></span>

<span data-ttu-id="1b3a2-108">CREATE PROCEDURE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="1b3a2-108">The CREATE PROCEDURE statement has these parts:</span></span>

|<span data-ttu-id="1b3a2-109">Part</span><span class="sxs-lookup"><span data-stu-id="1b3a2-109">Part</span></span>|<span data-ttu-id="1b3a2-110">说明</span><span class="sxs-lookup"><span data-stu-id="1b3a2-110">Description</span></span>|
|:---|:----------|
|<span data-ttu-id="1b3a2-111">*procedure*</span><span class="sxs-lookup"><span data-stu-id="1b3a2-111">*procedure*</span></span>|<span data-ttu-id="1b3a2-112">过程的名称。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-112">A name for the procedure.</span></span> <span data-ttu-id="1b3a2-113">它必须遵循标准命名规则。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-113">It must follow standard naming conventions.</span></span>|
|<span data-ttu-id="1b3a2-114">*param1*、*param2*</span><span class="sxs-lookup"><span data-stu-id="1b3a2-114">*param1*, *param2*</span></span>|<span data-ttu-id="1b3a2-115">从 1 到 255 个字段名或参数。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-115">From one to 255 field names or parameters.</span></span> <span data-ttu-id="1b3a2-116">例如：</span><span class="sxs-lookup"><span data-stu-id="1b3a2-116">For example:</span></span><br/><br/>`CREATE PROCEDURE Sales_By_Country [Beginning Date] DateTime, [Ending Date] DateTime;`<br/><br/><span data-ttu-id="1b3a2-117">有关参数的详细信息，请参阅 [PARAMETERS](parameters-declaration-microsoft-access-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-117">For more information on parameters, see [PARAMETERS](parameters-declaration-microsoft-access-sql.md).</span></span>|
|<span data-ttu-id="1b3a2-118">*datatype*</span><span class="sxs-lookup"><span data-stu-id="1b3a2-118">*DataType*</span></span>|<span data-ttu-id="1b3a2-119">主要 [Microsoft Access SQL 数据类型](sql-data-types.md)或其同义词之一。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-119">One of the primary [Microsoft Access SQL data types](sql-data-types.md) or their synonyms.</span></span>|
|<span data-ttu-id="1b3a2-120">*sqlstatement*</span><span class="sxs-lookup"><span data-stu-id="1b3a2-120">*SQLStatement*</span></span>|<span data-ttu-id="1b3a2-121">SQL 语句，如 SELECT、UPDATE、DELETE、INSERT、CREATE TABLE、DROP TABLE 等。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-121">An SQL statement such as SELECT, UPDATE, DELETE, INSERT, CREATE TABLE, DROP TABLE, and so on.</span></span>|


## <a name="remarks"></a><span data-ttu-id="1b3a2-122">说明</span><span class="sxs-lookup"><span data-stu-id="1b3a2-122">Remarks</span></span>

<span data-ttu-id="1b3a2-123">SQL 过程包含一个 PROCEDURE 子句（该子句指定过程的名称）、参数定义的可选列表和单个 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-123">An SQL procedure consists of a PROCEDURE clause that specifies the name of the procedure, an optional list of parameter definitions, and a single SQL statement.</span></span>

<span data-ttu-id="1b3a2-124">过程名称不能与现有表的名称相同。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-124">A procedure name cannot be the same as the name of an existing table.</span></span>

## <a name="example"></a><span data-ttu-id="1b3a2-125">示例</span><span class="sxs-lookup"><span data-stu-id="1b3a2-125">Example</span></span>

<span data-ttu-id="1b3a2-126">本示例将查询命名为 CategoryList，并调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。</span><span class="sxs-lookup"><span data-stu-id="1b3a2-126">This example calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

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
