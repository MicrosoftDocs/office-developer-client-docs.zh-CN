---
title: QueryDef.RecordsAffected Property (DAO)
TOCTitle: RecordsAffected Property
ms:assetid: 29a864b5-305c-d33f-b2ca-fc9a08baaa5c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192040(v=office.15)
ms:contentKeyID: 48543886
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053082
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9377f61ec334f41b7f8ccba61b87a9d5953b4429
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467836"
---
# <a name="querydefrecordsaffected-property-dao"></a><span data-ttu-id="517c0-102">QueryDef.RecordsAffected Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="517c0-102">QueryDef.RecordsAffected Property (DAO)</span></span>


<span data-ttu-id="517c0-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="517c0-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="517c0-104">返回最近调用的 **[Execute](querydef-execute-method-dao.md)** 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="517c0-104">Returns the number of records affected by the most recently invoked **[Execute](querydef-execute-method-dao.md)** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="517c0-105">语法</span><span class="sxs-lookup"><span data-stu-id="517c0-105">Syntax</span></span>

<span data-ttu-id="517c0-106">*表达式*。RecordsAffected</span><span class="sxs-lookup"><span data-stu-id="517c0-106">*expression* .RecordsAffected</span></span>

<span data-ttu-id="517c0-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="517c0-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="517c0-108">注解</span><span class="sxs-lookup"><span data-stu-id="517c0-108">Remarks</span></span>

<span data-ttu-id="517c0-109">当使用 **Execute** 方法从 **QueryDef** 对象运行动作查询时， **RecordsAffected** 属性将包含删除的、更新的或插入的记录的数目。</span><span class="sxs-lookup"><span data-stu-id="517c0-109">When you use the **Execute** method to run an action query from a **QueryDef** object, the **RecordsAffected** property will contain the number of records deleted, updated, or inserted.</span></span>

## <a name="example"></a><span data-ttu-id="517c0-110">示例</span><span class="sxs-lookup"><span data-stu-id="517c0-110">Example</span></span>

<span data-ttu-id="517c0-p101">以下示例将 **RecordsAffected** 属性用于从 **[Database](database-object-dao.md)** 对象和 **QueryDef** 对象执行的查询。若要使该过程运行，需要使用 RecordsAffectedOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="517c0-p101">This example uses the **RecordsAffected** property with action queries executed from a **[Database](database-object-dao.md)** object and from a **QueryDef** object. The RecordsAffectedOutput function is required for this procedure to run.</span></span>

```vb
    Sub RecordsAffectedX() 
     
     Dim dbsNorthwind As Database 
     Dim qdfTemp As QueryDef 
     Dim strSQLChange As String 
     Dim strSQLRestore As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "Number of records in Employees table: " & _ 
     .TableDefs!Employees.RecordCount 
     RecordsAffectedOutput dbsNorthwind 
     
     ' Define and execute an action query. 
     strSQLChange = "UPDATE Employees " & _ 
     "SET Country = 'United States' " & _ 
     "WHERE Country = 'USA'" 
     .Execute strSQLChange 
     
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "RecordsAffected after executing query " & _ 
     "from Database: " & .RecordsAffected 
     RecordsAffectedOutput dbsNorthwind 
     
     ' Define and run another action query. 
     strSQLRestore = "UPDATE Employees " & _ 
     "SET Country = 'USA' " & _ 
     "WHERE Country = 'United States'" 
     Set qdfTemp = .CreateQueryDef("", strSQLRestore) 
     qdfTemp.Execute 
     
     ' Print report of contents of the Employees 
     ' table. 
     Debug.Print _ 
     "RecordsAffected after executing query " & _ 
     "from QueryDef: " & qdfTemp.RecordsAffected 
     RecordsAffectedOutput dbsNorthwind 
     
     .Close 
     
     End With 
     
    End Sub 
     
    Function RecordsAffectedOutput(dbsNorthwind As Database) 
     
     Dim rstEmployees As Recordset 
     
     ' Open a Recordset object from the Employees table. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     ' Enumerate Recordset. 
     .MoveFirst 
     Do While Not .EOF 
     Debug.Print " " & !LastName & ", " & !Country 
     .MoveNext 
     Loop 
     .Close 
     End With 
     
    End Function
```