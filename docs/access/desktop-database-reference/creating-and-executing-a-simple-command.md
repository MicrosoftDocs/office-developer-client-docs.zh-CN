---
title: 创建和执行简单命令
TOCTitle: Creating and executing a simple command
ms:assetid: 9ace1abe-cfae-0677-bc57-5cbda85b79db
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249699(v=office.15)
ms:contentKeyID: 48546547
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 333f8481958914eadbd830600c08035acc92b031
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947474"
---
# <a name="creating-and-executing-a-simple-command"></a><span data-ttu-id="82731-102">创建和执行简单命令</span><span class="sxs-lookup"><span data-stu-id="82731-102">Creating and executing a simple command</span></span>


<span data-ttu-id="82731-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="82731-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="82731-p101">以下代码演示使用 **Command** 对象针对数据源执行命令的基本方法，尽管这不是 **Command** 对象的典型用法。在这种情况下，它是返回行的命令，因此它将命令的执行结果返回到 **Recordset** 对象中。</span><span class="sxs-lookup"><span data-stu-id="82731-p101">Though not a typical usage of the **Command** object, the following code shows the basic method of using the **Command** object to execute a command against a data source. In this case, it is a row-returning command, so it returns the results of the command execution into a **Recordset** object.</span></span>

```vb 
 
 'BeginBasicCmd 
 On Error GoTo ErrHandler: 
 
 Dim objConn As New ADODB.Connection 
 Dim objCmd As New ADODB.Command 
 Dim objRs As New ADODB.Recordset 
 
 objCmd.CommandText = "SELECT OrderID, OrderDate, " & _ 
 "RequiredDate, ShippedDate " & _ 
 "FROM Orders " & _ 
 "WHERE CustomerID = 'ALFKI' " & _ 
 "ORDER BY OrderID" 
 objCmd.CommandType = adCmdText 
 
 ' Connect to the data source. 
 Set objConn = GetNewConnection 
 objCmd.ActiveConnection = objConn 
 
 ' Execute once and display... 
 Set objRs = objCmd.Execute 
 
 Debug.Print "ALFKI" 
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
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
'EndBasicCmd 
```

<span data-ttu-id="82731-106">可以用 **CommandText** 属性指定要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="82731-106">The command to be executed is specified with the **CommandText** property.</span></span>


> [!NOTE]
> <span data-ttu-id="82731-107">本节中的几个示例调用的实用工具函数， **GetNewConnection**，建立与数据提供程序的连接。</span><span class="sxs-lookup"><span data-stu-id="82731-107">Several examples in this section call a utility function, **GetNewConnection**, to establish a connection with the data provider.</span></span> <span data-ttu-id="82731-108">若要避免冗余，它列出了仅执行一次：</span><span class="sxs-lookup"><span data-stu-id="82731-108">To avoid redundancy, it is listed only once:</span></span>

```vb 
 
'BeginNewConnection 
Private Function GetNewConnection() As ADODB.Connection 
 Dim oCn As New ADODB.Connection 
 Dim sCnStr As String 
 
 sCnStr = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _ 
 "Integrated Security='SSPI';Database='Northwind';" 
 oCn.Open sCnStr 
 
 If oCn.State = adStateOpen Then 
 Set GetNewConnection = oCn 
 End If 
 
End Function 
'EndNewConnection 
```

