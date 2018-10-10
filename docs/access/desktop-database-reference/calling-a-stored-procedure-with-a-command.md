---
title: 通过命令调用存储过程
TOCTitle: Calling a Stored Procedure with a Command
ms:assetid: 19d600d7-f717-39df-11a0-951e3ed0f812
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248944(v=office.15)
ms:contentKeyID: 48543509
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 573b847f53d3fc7ca07691e9a92d152598531bce
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467206"
---
# <a name="calling-a-stored-procedure-with-a-command"></a><span data-ttu-id="945fb-102">通过命令调用存储过程</span><span class="sxs-lookup"><span data-stu-id="945fb-102">Calling a Stored Procedure with a Command</span></span>


<span data-ttu-id="945fb-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="945fb-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="945fb-p101">还可以在调用存储过程时使用命令。以下代码调用罗斯文示例数据库中名为 CustOrdersOrders 的存储过程，定义如下：</span><span class="sxs-lookup"><span data-stu-id="945fb-p101">You can also use a command when calling a stored procedure. The following code calls a stored procedure in the Northwind sample database, called CustOrdersOrders, which is defined as follows:</span></span>

```vb 
 
CREATE PROCEDURE CustOrdersOrders @CustomerID nchar(5) AS 
SELECT OrderID, OrderDate, RequiredDate, ShippedDate 
FROM Orders 
WHERE CustomerID = @CustomerID 
ORDER BY OrderID 
```

<span data-ttu-id="945fb-p102">此存储过程类似于 [Command 对象参数](command-object-parameters.md)中使用的命令，在该参数中它获取客户 ID 参数并返回有关该客户订单的信息。以下代码将此存储过程作为 ADO **Recordset** 的源。</span><span class="sxs-lookup"><span data-stu-id="945fb-p102">This stored procedure is similar to the command used in [Command Object Parameters](command-object-parameters.md), in that it takes a customer ID parameter and returns information about that customer's orders. The code below uses this stored procedure as the source for an ADO **Recordset**.</span></span>

<span data-ttu-id="945fb-p103">使用该存储过程可以访问另一 ADO 功能： **Parameters** 集合的 **Refresh** 方法。通过使用此方法，ADO 可以自动填写在该命令运行时所需参数的所有信息。使用此技术时存在性能损失，因为 ADO 必须查询数据源才能获得有关参数的信息。</span><span class="sxs-lookup"><span data-stu-id="945fb-p103">Using the stored procedure allows you to access another capability of ADO: the **Parameters** collection **Refresh** method. By using this method, ADO can automatically fill in all information about the parameters required by the command at run time. There is a performance penalty in using this technique, because ADO must query the data source for the information about the parameters.</span></span>

<span data-ttu-id="945fb-p104">以下代码和 [Command 对象参数](command-object-parameters.md)中的代码之间存在一些其他重要差异（后者的参数是手动输入的）。首先，此代码没有将 **Prepared** 属性设置为 **True** ，因为它是 SQL Server 存储过程且已按定义进行了预编译。其次，在第二个示例中， **Command** 对象的 **CommandType** 属性更改为 **adCmdStoredProc** ，以通知 ADO 该命令是存储过程。</span><span class="sxs-lookup"><span data-stu-id="945fb-p104">Other important differences exist between the code below and the code in [Command Object Parameters](command-object-parameters.md), where the parameters were entered manually. First, this code does not set the **Prepared** property to **True** because it is a SQL Server stored procedure and is precompiled by definition. Second, the **CommandType** property of the **Command** object changed to **adCmdStoredProc** in the second example to inform ADO that the command was a stored procedure.</span></span>

```vb 
 
'BeginAutoParamCmd 
 On Error GoTo ErrHandler: 
 
 Dim objConn As New ADODB.Connection 
 Dim objCmd As New ADODB.Command 
 Dim objParm1 As New ADODB.Parameter 
 Dim objRs As New ADODB.Recordset 
 
 ' Set CommandText equal to the stored procedure name. 
 objCmd.CommandText = "CustOrdersOrders" 
 objCmd.CommandType = adCmdStoredProc 
 
 ' Connect to the data source. 
 Set objConn = GetNewConnection 
 objCmd.ActiveConnection = objConn 
 
 ' Automatically fill in parameter info from stored procedure. 
 objCmd.Parameters.Refresh 
 
 ' Set the param value. 
 objCmd(1) = "ALFKI" 
 
 ' Execute once and display... 
 Set objRs = objCmd.Execute 
 
 Debug.Print objParm1.Value 
 Do While Not objRs.EOF 
 Debug.Print vbTab & objRs(0) & vbTab & objRs(1) & vbTab & _ 
 objRs(2) & vbTab & objRs(3) 
 objRs.MoveNext 
 Loop 
 
 ' ...then set new param value, re-execute command, and display. 
 objCmd(1) = "CACTU" 
 Set objRs = objCmd.Execute 
 
 Debug.Print objParm1.Value 
 Do While Not objRs.EOF 
 Debug.Print vbTab & objRs(0) & vbTab & objRs(1) & vbTab & _ 
 objRs(2) & vbTab & objRs(3) 
 objRs.MoveNext 
 Loop 
 
 'clean up 
 objRs.Close 
 objConn.Close 
 Set objRs = Nothing 
 Set objConn = Nothing 
 Set objCmd = Nothing 
 Set objParm1 = Nothing 
 Exit Sub 
 
ErrHandler: 
 'clean up 
 If objRs.State = adStateOpen Then 
 objRs.Close 
 End If 
 
 If objConn.State = adStateOpen Then 
 objConn.Close 
 End If 
 
 Set objRs = Nothing 
 Set objConn = Nothing 
 Set objCmd = Nothing 
 Set objParm1 = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
'EndAutoParamCmd 
```

