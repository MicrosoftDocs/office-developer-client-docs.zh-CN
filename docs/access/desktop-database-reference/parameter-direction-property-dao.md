---
title: Parameter.Direction Property (DAO)
TOCTitle: Direction Property
ms:assetid: b78c87ff-1181-21ef-7126-92d309751005
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822422(v=office.15)
ms:contentKeyID: 48547300
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053586
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4612b578971f59744e25c15d3762cc893f6f71ef
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466180"
---
# <a name="parameterdirection-property-dao"></a><span data-ttu-id="764d4-102">Parameter.Direction Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="764d4-102">Parameter.Direction Property (DAO)</span></span>


<span data-ttu-id="764d4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="764d4-103">**Applies to**: Access 2013 | Office 2013</span></span>


## <a name="syntax"></a><span data-ttu-id="764d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="764d4-104">Syntax</span></span>

<span data-ttu-id="764d4-105">*表达式*。方向</span><span class="sxs-lookup"><span data-stu-id="764d4-105">*expression* .Direction</span></span>

<span data-ttu-id="764d4-106">*表达式*一个代表**Parameter**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="764d4-106">*expression* A variable that represents a **Parameter** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="764d4-107">注解</span><span class="sxs-lookup"><span data-stu-id="764d4-107">Remarks</span></span>

<span data-ttu-id="764d4-108">设置值或返回值是可设置为 **[ParameterDirectionEnum](parameterdirectionenum-enumeration-dao.md)** 常量之一的 Long 类型。</span><span class="sxs-lookup"><span data-stu-id="764d4-108">The setting or return value is a Long that can be set to one of the **[ParameterDirectionEnum](parameterdirectionenum-enumeration-dao.md)** constants.</span></span>

<span data-ttu-id="764d4-p101">使用 **Direction** 属性确定参数是输入参数、输出参数、此两者还是过程的返回值。某些 ODBC 驱动程序不提供与 SELECT 语句或过程调用的参数的方向有关的信息。在这些情况下，执行查询之前必须设置方向。</span><span class="sxs-lookup"><span data-stu-id="764d4-p101">Use the **Direction** property to determine whether the parameter is an input parameter, output parameter, both, or the return value from the procedure. Some ODBC drivers do not provide information on the direction of parameters to a SELECT statement or procedure call. In these cases, it is necessary to set the direction prior to executing the query.</span></span>

<span data-ttu-id="764d4-112">例如，以下过程从名为的存储过程返回值"获取\_员工":</span><span class="sxs-lookup"><span data-stu-id="764d4-112">For example, the following procedure returns a value from a stored procedure named "get\_employees":</span></span>

<span data-ttu-id="764d4-113">{?</span><span class="sxs-lookup"><span data-stu-id="764d4-113"></span></span> <span data-ttu-id="764d4-114">= 呼叫 get\_员工}</span><span class="sxs-lookup"><span data-stu-id="764d4-114">= call get\_employees}</span></span>

<span data-ttu-id="764d4-p103">该调用将生成一个参数，即返回值。在执行 \*\*\*\*QueryDef\*\*\*\* 之前，需要将该参数的方向设置为 [dbParamOutput](querydef-object-dao.md) 或 **dbParamReturnValue**。</span><span class="sxs-lookup"><span data-stu-id="764d4-p103">This call produces one parameter — the return value. You need to set the direction of this parameter to **dbParamOutput** or **dbParamReturnValue** before executing the **[QueryDef](querydef-object-dao.md)**.</span></span>

<span data-ttu-id="764d4-117">在访问或设置参数值之前，以及在执行 **QueryDef** 之前，需要设置除 **dbParamInput** 以外的所有参数方向。</span><span class="sxs-lookup"><span data-stu-id="764d4-117">You need to set all parameter directions except **dbParamInput** before accessing or setting the values of the parameters and before executing the **QueryDef**.</span></span>

<span data-ttu-id="764d4-118">应该为返回值使用 **dbParamReturnValue**，但如果驱动程序或服务器不支持该选项，则可以改用 **dbParamOutput**。</span><span class="sxs-lookup"><span data-stu-id="764d4-118">You should use **dbParamReturnValue** for return values, but in cases where that option is not supported by the driver or the server, you can use **dbParamOutput** instead.</span></span>

<span data-ttu-id="764d4-p104">Microsoft SQL Server 驱动程序可自动设置所有过程参数的 **Direction** 属性。并非所有 ODBC 驱动程序都可以确定查询参数的方向。在这些情况下，执行查询之前必须设置方向。</span><span class="sxs-lookup"><span data-stu-id="764d4-p104">The Microsoft SQL Server driver automatically sets the **Direction** property for all procedure parameters. Not all ODBC drivers can determine the direction of a query parameter. In these cases, it is necessary to set the direction prior to executing the query.</span></span>

## <a name="example"></a><span data-ttu-id="764d4-122">示例</span><span class="sxs-lookup"><span data-stu-id="764d4-122">Example</span></span>

<span data-ttu-id="764d4-123">以下示例使用 **Direction** 属性配置发送到 ODBC 数据源的某个查询的参数。</span><span class="sxs-lookup"><span data-stu-id="764d4-123">This example uses the **Direction** property to configure the parameters of a query to an ODBC data source.</span></span>

```vb 
Sub DirectionX() 
 
 Dim wrkMain As Workspace 
 Dim conMain As Connection 
 Dim qdfTemp As QueryDef 
 Dim rstTemp As Recordset 
 Dim strSQL As String 
 Dim intLoop As Integer 
 
 ' Create ODBC workspace and open a connection to a 
 ' Microsoft SQL Server database. 
 Set wrkMain = CreateWorkspace("ODBCWorkspace", _ 
 "admin", "", dbUseODBC) 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conMain = wrkMain.OpenConnection("Publishers", _ 
 dbDriverNoPrompt, False, _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 ' Set SQL string to call the stored procedure 
 ' getempsperjob. 
 strSQL = "{ call getempsperjob (?, ?) }" 
 
 Set qdfTemp = conMain.CreateQueryDef("", strSQL) 
 
 With qdfTemp 
 ' Indicate that the two query parameters will only 
 ' pass information to the stored procedure. 
 .Parameters(0).Direction = dbParamInput 
 .Parameters(1).Direction = dbParamInput 
 
 ' Assign initial parameter values. 
 .Parameters(0) = "0877" 
 .Parameters(1) = 0 
 
 Set rstTemp = .OpenRecordset() 
 
 With rstTemp 
 ' Loop through all valid values for the second 
 ' parameter. For each value, requery the recordset 
 ' to obtain the correct results and then print out 
 ' the contents of the recordset. 
 For intLoop = 1 To 14 
 qdfTemp.Parameters(1) = intLoop 
 .Requery 
 Debug.Print "Publisher = " & _ 
 qdfTemp.Parameters(0) & _ 
 ", job = " & intLoop 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 Next intLoop 
 .Close 
 End With 
 
 End With 
 
 conMain.Close 
 wrkMain.Close 
 
End Sub 
 
```
