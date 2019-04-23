---
title: 参数. Direction 属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 3260fd3f01e8ca22d5be4f8d14f6376c31e2735a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288089"
---
# <a name="parameterdirection-property-dao"></a><span data-ttu-id="19c8e-102">参数. Direction 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="19c8e-102">Parameter.Direction property (DAO)</span></span>


<span data-ttu-id="19c8e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="19c8e-103">**Applies to**: Access 2013, Office 2013</span></span>


## <a name="syntax"></a><span data-ttu-id="19c8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="19c8e-104">Syntax</span></span>

<span data-ttu-id="19c8e-105">*表达式*。方向</span><span class="sxs-lookup"><span data-stu-id="19c8e-105">*expression* .Direction</span></span>

<span data-ttu-id="19c8e-106">*表达式*一个代表**Parameter**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="19c8e-106">*expression* A variable that represents a **Parameter** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="19c8e-107">注解</span><span class="sxs-lookup"><span data-stu-id="19c8e-107">Remarks</span></span>

<span data-ttu-id="19c8e-108">设置或返回值是一个很长的值, 可设置为**[ParameterDirectionEnum](parameterdirectionenum-enumeration-dao.md)** 常量之一。</span><span class="sxs-lookup"><span data-stu-id="19c8e-108">The setting or return value is a Long that can be set to one of the **[ParameterDirectionEnum](parameterdirectionenum-enumeration-dao.md)** constants.</span></span>

<span data-ttu-id="19c8e-109">使用 **Direction** 属性确定参数是输入参数、输出参数、此两者还是过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="19c8e-109">Use the **Direction** property to determine whether the parameter is an input parameter, output parameter, both, or the return value from the procedure.</span></span> <span data-ttu-id="19c8e-110">某些 ODBC 驱动程序不提供与 SELECT 语句或过程调用的参数的方向有关的信息。</span><span class="sxs-lookup"><span data-stu-id="19c8e-110">Some ODBC drivers do not provide information on the direction of parameters to a SELECT statement or procedure call.</span></span> <span data-ttu-id="19c8e-111">在这些情况下，执行查询之前必须设置方向。</span><span class="sxs-lookup"><span data-stu-id="19c8e-111">In these cases, it is necessary to set the direction prior to executing the query.</span></span>

<span data-ttu-id="19c8e-112">例如, 以下过程将从名为 "获取\_员工" 的存储过程返回一个值:</span><span class="sxs-lookup"><span data-stu-id="19c8e-112">For example, the following procedure returns a value from a stored procedure named "get\_employees":</span></span>

<span data-ttu-id="19c8e-113">{?</span><span class="sxs-lookup"><span data-stu-id="19c8e-113"></span></span> <span data-ttu-id="19c8e-114">= 呼叫获取\_员工}</span><span class="sxs-lookup"><span data-stu-id="19c8e-114">= call get\_employees}</span></span>

<span data-ttu-id="19c8e-115">该调用将生成一个参数，即返回值。</span><span class="sxs-lookup"><span data-stu-id="19c8e-115">This call produces one parameter — the return value.</span></span> <span data-ttu-id="19c8e-116">在执行 **[QueryDef](querydef-object-dao.md)** 之前，需要将该参数的方向设置为 **dbParamOutput** 或 **dbParamReturnValue**。</span><span class="sxs-lookup"><span data-stu-id="19c8e-116">You need to set the direction of this parameter to **dbParamOutput** or **dbParamReturnValue** before executing the **[QueryDef](querydef-object-dao.md)**.</span></span>

<span data-ttu-id="19c8e-117">在访问或设置参数值之前，以及在执行 **QueryDef** 之前，需要设置除 **dbParamInput** 以外的所有参数方向。</span><span class="sxs-lookup"><span data-stu-id="19c8e-117">You need to set all parameter directions except **dbParamInput** before accessing or setting the values of the parameters and before executing the **QueryDef**.</span></span>

<span data-ttu-id="19c8e-118">应该为返回值使用 **dbParamReturnValue**，但如果驱动程序或服务器不支持该选项，则可以改用 **dbParamOutput**。</span><span class="sxs-lookup"><span data-stu-id="19c8e-118">You should use **dbParamReturnValue** for return values, but in cases where that option is not supported by the driver or the server, you can use **dbParamOutput** instead.</span></span>

<span data-ttu-id="19c8e-119">Microsoft SQL Server 驱动程序可自动设置所有过程参数的 **Direction** 属性。</span><span class="sxs-lookup"><span data-stu-id="19c8e-119">The Microsoft SQL Server driver automatically sets the **Direction** property for all procedure parameters.</span></span> <span data-ttu-id="19c8e-120">并非所有 ODBC 驱动程序都可以确定查询参数的方向。</span><span class="sxs-lookup"><span data-stu-id="19c8e-120">Not all ODBC drivers can determine the direction of a query parameter.</span></span> <span data-ttu-id="19c8e-121">在这些情况下，执行查询之前必须设置方向。</span><span class="sxs-lookup"><span data-stu-id="19c8e-121">In these cases, it is necessary to set the direction prior to executing the query.</span></span>

## <a name="example"></a><span data-ttu-id="19c8e-122">示例</span><span class="sxs-lookup"><span data-stu-id="19c8e-122">Example</span></span>

<span data-ttu-id="19c8e-123">以下示例使用 **Direction** 属性配置发送到 ODBC 数据源的某个查询的参数。</span><span class="sxs-lookup"><span data-stu-id="19c8e-123">This example uses the **Direction** property to configure the parameters of a query to an ODBC data source.</span></span>

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

