---
title: QueryDef 属性 (DAO)
TOCTitle: Prepare Property
ms:assetid: d5a285c4-bd00-028b-b785-f1890db29bab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835035(v=office.15)
ms:contentKeyID: 48547968
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101187
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ac05510a218d1cf4cf925acc2ca8908b7bcbcd03
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303267"
---
# <a name="querydefprepare-property-dao"></a><span data-ttu-id="25a5e-102">QueryDef 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="25a5e-102">QueryDef.Prepare property (DAO)</span></span>

<span data-ttu-id="25a5e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="25a5e-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="25a5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="25a5e-104">Syntax</span></span>

<span data-ttu-id="25a5e-105">*表达式*。份</span><span class="sxs-lookup"><span data-stu-id="25a5e-105">*expression* .Prepare</span></span>

<span data-ttu-id="25a5e-106">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="25a5e-106">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="25a5e-107">注解</span><span class="sxs-lookup"><span data-stu-id="25a5e-107">Remarks</span></span>

<span data-ttu-id="25a5e-p101">可以使用 **Prepare** 属性让服务器从您的查询创建并执行临时存储过程，也可以直接执行查询。默认情况下， **Prepare** 属性设置为 **dbQPrepare**。但是，您可以将该属性设置为 **dbQUnprepare**，以禁止准备查询。在此情况下，将使用 **SQLExecDirect** API 执行查询。</span><span class="sxs-lookup"><span data-stu-id="25a5e-p101">You can use the **Prepare** property to either have the server create a temporary stored procedure from your query and then execute it, or just have the query executed directly. By default the **Prepare** property is set to **dbQPrepare**. However, you can set this property to **dbQUnprepare** to prohibit preparing of the query. In this case, the query is executed using the **SQLExecDirect** API.</span></span>

<span data-ttu-id="25a5e-p102">创建存储过程可能降低初始操作的速度，但是提高了对该查询的所有后续引用的性能。不过，某些查询不能以存储过程的形式来执行。在这种情况下，您必须将 **Prepare** 属性设置为 **dbQUnprepare**。</span><span class="sxs-lookup"><span data-stu-id="25a5e-p102">Creating a stored procedure can slow down the initial operation, but increases performance of all subsequent references to the query. However, some queries cannot be executed in the form of stored procedures. In these cases, you must set the **Prepare** property to **dbQUnprepare**.</span></span>

<span data-ttu-id="25a5e-115">如果**Prepare**设置为**dbQPrepare**, 则可以在执行查询时通过将**[Execute](querydef-execute-method-dao.md)** 方法的 options 参数设置为**这一设置**来覆盖此设置。</span><span class="sxs-lookup"><span data-stu-id="25a5e-115">If **Prepare** is set to **dbQPrepare**, this can be overridden when the query is executed by setting the **[Execute](querydef-execute-method-dao.md)** method's options argument to **dbExecDirect**.</span></span>

> [!NOTE]
> <span data-ttu-id="25a5e-p103">[!注释] 一旦设置了 DAO [**SQL**](querydef-sql-property-dao.md) 属性，就会调用 ODBC **SQLPrepare** API。因此，如果您希望使用 **dbQUnprepare** 选项来提高性能，则必须在设置 **SQL** 属性之前设置 **Prepare** 属性。</span><span class="sxs-lookup"><span data-stu-id="25a5e-p103">The ODBC **SQLPrepare** API is called as soon as the DAO **[SQL](querydef-sql-property-dao.md)** property is set. Therefore, if you want to improve performance using the **dbQUnprepare** option, you must set the **Prepare** property before setting the **SQL** property.</span></span>

## <a name="example"></a><span data-ttu-id="25a5e-118">示例</span><span class="sxs-lookup"><span data-stu-id="25a5e-118">Example</span></span>

<span data-ttu-id="25a5e-119">以下示例使用 **Prepare** 属性指定应当直接执行查询，而不是首先在服务器上创建临时存储过程。</span><span class="sxs-lookup"><span data-stu-id="25a5e-119">This example uses the **Prepare** property to specify that a query should be executed directly rather than first creating a temporary stored procedure on the server.</span></span>

```vb 
Sub PrepareX() 
 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim qdfTemp As QueryDef 
 Dim rstTemp As Recordset 
 
 ' Create ODBCDirect Workspace object and open Connection 
 ' object. 
 Set wrkODBC = CreateWorkspace("", _ 
 "admin", "", dbUseODBC) 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Publishers", , , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Set qdfTemp = conPubs.CreateQueryDef("") 
 
 With qdfTemp 
 ' Because you will only run this query once, specify 
 ' the ODBC SQLExecDirect API function. If you do 
 ' not set this property before you set the SQL 
 ' property, the ODBC SQLPrepare API function will 
 ' be called anyway which will nullify any 
 ' performance gain. 
 .Prepare = dbQUnprepare 
 .SQL = "UPDATE roysched " & _ 
 "SET royalty = royalty * 2 " & _ 
 "WHERE title_id LIKE 'BU____' OR " & _ 
 "title_id LIKE 'PC____'" 
 .Execute 
 End With 
 
 Debug.Print "Query results:" 
 
 ' Open recordset containing modified records. 
 Set rstTemp = conPubs.OpenRecordset( _ 
 "SELECT * FROM roysched " & _ 
 "WHERE title_id LIKE 'BU____' OR " & _ 
 "title_id LIKE 'PC____'") 
 
 ' Enumerate recordset. 
 With rstTemp 
 Do While Not .EOF 
 Debug.Print , !title_id, !lorange, _ 
 !hirange, !royalty 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 conPubs.Close 
 wrkODBC.Close 
 
```

