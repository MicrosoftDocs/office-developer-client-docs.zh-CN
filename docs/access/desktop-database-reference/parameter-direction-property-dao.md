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
ms.openlocfilehash: c06fbf6bb3424e776e21f32343c8cdb8a795b604
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877105"
---
# <a name="parameterdirection-property-dao"></a>Parameter.Direction Property (DAO)


**适用于**： Access 2013、 Office 2013


## <a name="syntax"></a>语法

*表达式*。方向

*表达式*一个代表**Parameter**对象的变量。

## <a name="remarks"></a>注解

设置值或返回值是可设置为 **[ParameterDirectionEnum](parameterdirectionenum-enumeration-dao.md)** 常量之一的 Long 类型。

使用 **Direction** 属性确定参数是输入参数、输出参数、此两者还是过程的返回值。某些 ODBC 驱动程序不提供与 SELECT 语句或过程调用的参数的方向有关的信息。在这些情况下，执行查询之前必须设置方向。

例如，以下过程从名为的存储过程返回值"获取\_员工":

{? = 呼叫 get\_员工}

该调用将生成一个参数，即返回值。在执行 ****QueryDef**** 之前，需要将该参数的方向设置为 [dbParamOutput](querydef-object-dao.md) 或 **dbParamReturnValue**。

在访问或设置参数值之前，以及在执行 **QueryDef** 之前，需要设置除 **dbParamInput** 以外的所有参数方向。

应该为返回值使用 **dbParamReturnValue**，但如果驱动程序或服务器不支持该选项，则可以改用 **dbParamOutput**。

Microsoft SQL Server 驱动程序可自动设置所有过程参数的 **Direction** 属性。并非所有 ODBC 驱动程序都可以确定查询参数的方向。在这些情况下，执行查询之前必须设置方向。

## <a name="example"></a>示例

以下示例使用 **Direction** 属性配置发送到 ODBC 数据源的某个查询的参数。

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

