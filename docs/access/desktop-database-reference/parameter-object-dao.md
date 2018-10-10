---
title: Parameter Object (DAO)
TOCTitle: Parameter Object
ms:assetid: 194efd23-6086-13ac-beb9-c2aec101d6fe
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845640(v=office.15)
ms:contentKeyID: 48543495
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 69388834d5469c9fa66d70d397d63be4376db218
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468714"
---
# <a name="parameter-object-dao"></a><span data-ttu-id="1b7d4-102">Parameter Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="1b7d4-102">Parameter Object (DAO)</span></span>


<span data-ttu-id="1b7d4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1b7d4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1b7d4-p101">**Parameter** 对象代表提供给查询的值。此参数与从参数查询创建的 **QueryDef** 对象关联。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-p101">A **Parameter** object represents a value supplied to a query. The parameter is associated with a **QueryDef** object created from a parameter query.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b7d4-106">注解</span><span class="sxs-lookup"><span data-stu-id="1b7d4-106">Remarks</span></span>

<span data-ttu-id="1b7d4-107">使用 **Parameter** 可以更改经常运行的 **QueryDef** 对象中的参数，而不必重新编译查询。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-107">**Parameter** objects allow you to change the arguments in a frequently run **QueryDef** object without having to recompile the query.</span></span>

<span data-ttu-id="1b7d4-p102">使用 **Parameter** 对象的属性，可以设置能够在运行查询之前更改的查询参数。您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1b7d4-p102">Using the properties of a **Parameter** object, you can set a query parameter that can be changed before the query is run. You can:</span></span>

  - <span data-ttu-id="1b7d4-110">使用 **Name** 属性返回参数的名称。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-110">Use the **Name** property to return the name of a parameter.</span></span>

  - <span data-ttu-id="1b7d4-111">使用 **Value** 属性设置或返回需要在查询中使用的参数值。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-111">Use the **Value** property to set or return the parameter values to be used in the query.</span></span>

  - <span data-ttu-id="1b7d4-112">使用 **Type** 属性返回 **Parameter** 对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-112">Use the **Type** property to return the data type of the **Parameter** object.</span></span>

  - <span data-ttu-id="1b7d4-113">使用 **Direction** 属性设置或返回参数是输入参数、输出参数还是此两者的信息。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-113">Use the **Direction** property to set or return whether the parameter is an input parameter, an output parameter, or both.</span></span>

## <a name="example"></a><span data-ttu-id="1b7d4-114">示例</span><span class="sxs-lookup"><span data-stu-id="1b7d4-114">Example</span></span>

<span data-ttu-id="1b7d4-p103">以下示例通过创建一个临时 **QueryDef**，并基于对 **QueryDef** 对象的 **Parameters** 所做的更改检索数据，来演示 **Parameter** 对象和 **Parameters** 集合。若要使该过程运行，需要使用 ParametersChange 过程。</span><span class="sxs-lookup"><span data-stu-id="1b7d4-p103">This example demonstrates **Parameter** objects and the **Parameters** collection by creating a temporary **QueryDef** and retrieving data based on changes made to the **QueryDef** object's **Parameters**. The ParametersChange procedure is required for this procedure to run.</span></span>

```vb
    Sub ParameterX() 
     
     Dim dbsNorthwind As Database 
     Dim qdfReport As QueryDef 
     Dim prmBegin As Parameter 
     Dim prmEnd As Parameter 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create temporary QueryDef object with two 
     ' parameters. 
     Set qdfReport = dbsNorthwind.CreateQueryDef("", _ 
     "PARAMETERS dteBegin DateTime, dteEnd DateTime; " & _ 
     "SELECT EmployeeID, COUNT(OrderID) AS NumOrders " & _ 
     "FROM Orders WHERE ShippedDate BETWEEN " & _ 
     "[dteBegin] AND [dteEnd] GROUP BY EmployeeID " & _ 
     "ORDER BY EmployeeID") 
     Set prmBegin = qdfReport.Parameters!dteBegin 
     Set prmEnd = qdfReport.Parameters!dteEnd 
     
     ' Print report using specified parameter values. 
     ParametersChange qdfReport, prmBegin, #1/1/95#, _ 
     prmEnd, #6/30/95# 
     ParametersChange qdfReport, prmBegin, #7/1/95#, _ 
     prmEnd, #12/31/95# 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub ParametersChange(qdfTemp As QueryDef, _ 
     prmFirst As Parameter, dteFirst As Date, _ 
     prmLast As Parameter, dteLast As Date) 
     ' Report function for ParameterX. 
     
     Dim rstTemp As Recordset 
     Dim fldLoop As Field 
     
     ' Set parameter values and open recordset from 
     ' temporary QueryDef object. 
     prmFirst = dteFirst 
     prmLast = dteLast 
     Set rstTemp = _ 
     qdfTemp.OpenRecordset(dbOpenForwardOnly) 
     Debug.Print "Period " & dteFirst & " to " & dteLast 
     
     ' Enumerate recordset. 
     Do While Not rstTemp.EOF 
     
     ' Enumerate Fields collection of recordset. 
     For Each fldLoop In rstTemp.Fields 
     Debug.Print " - " & fldLoop.Name & " = " & fldLoop; 
     Next fldLoop 
     
     Debug.Print 
     rstTemp.MoveNext 
     Loop 
     
     rstTemp.Close 
     
    End Sub
```
