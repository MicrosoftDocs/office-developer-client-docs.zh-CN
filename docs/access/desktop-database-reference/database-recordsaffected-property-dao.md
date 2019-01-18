---
title: Database.RecordsAffected 属性 (DAO)
TOCTitle: RecordsAffected Property
ms:assetid: 1c591231-21dd-f0b1-4ba6-87784c5890d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845732(v=office.15)
ms:contentKeyID: 48543567
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a1bcb9ac1140b275d0c7a2441f58d2ced0e0f82c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715849"
---
# <a name="databaserecordsaffected-property-dao"></a><span data-ttu-id="2d53d-102">Database.RecordsAffected 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="2d53d-102">Database.RecordsAffected property (DAO)</span></span>


<span data-ttu-id="2d53d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2d53d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2d53d-104">返回最近调用的 **[Execute](connection-execute-method-dao.md)** 方法所影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="2d53d-104">Returns the number of records affected by the most recently invoked **[Execute](connection-execute-method-dao.md)** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="2d53d-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d53d-105">Syntax</span></span>

<span data-ttu-id="2d53d-106">*表达式*。RecordsAffected</span><span class="sxs-lookup"><span data-stu-id="2d53d-106">*expression* .RecordsAffected</span></span>

<span data-ttu-id="2d53d-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2d53d-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="example"></a><span data-ttu-id="2d53d-108">示例</span><span class="sxs-lookup"><span data-stu-id="2d53d-108">Example</span></span>

<span data-ttu-id="2d53d-p101">以下示例将 **RecordsAffected** 属性用于从 **Database** 对象和 **QueryDef** 对象执行的查询。若要使该过程运行，需要使用 RecordsAffectedOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="2d53d-p101">This example uses the **RecordsAffected** property with action queries executed from a **Database** object and from a **QueryDef** object. The RecordsAffectedOutput function is required for this procedure to run.</span></span>

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
