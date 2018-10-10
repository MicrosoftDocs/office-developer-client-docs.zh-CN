---
title: 命名命令
TOCTitle: Named Commands
ms:assetid: 1a4d77e0-1736-83ea-a3c6-f5398c0b01e1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248948(v=office.15)
ms:contentKeyID: 48543518
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 940e0ace8577e6fdb7dc01daf3cd67320dfbf18c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465533"
---
# <a name="named-commands"></a><span data-ttu-id="1fd60-102">命名命令</span><span class="sxs-lookup"><span data-stu-id="1fd60-102">Named Commands</span></span>


<span data-ttu-id="1fd60-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1fd60-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1fd60-p101">可以设置 **Command** 对象的 **Name** 属性，然后通过将该命令视为 **Command** 对象的 **ActiveConnection** 属性的方法来调用它，从而执行该命令。以下示例说明了这种情况，该示例将命令命名为 *GetCustomers*。注意，代码会将一个已声明和实例化的 **Recordset** 对象传递给 GetCustomers“方法”。如果 **Command** 需要参数，还可以向该“方法”传递参数。</span><span class="sxs-lookup"><span data-stu-id="1fd60-p101">You can set the **Name** property on a **Command** object and then execute the command by calling it as if it were a method on the **Command** object **ActiveConnection** property. This is illustrated in the following example, in which the command is named *GetCustomers*. Notice that the code passes in a declared and instantiated **Recordset** object to the GetCustomers "method." You can also pass in parameters to the "method" if they are required by the **Command**.</span></span>

```vb 
 
'BeginNamedCmd 
 On Error GoTo ErrHandler: 
 
 Dim objConn As New ADODB.Connection 
 Dim objCmd As New ADODB.Command 
 Dim objRs As New ADODB.Recordset 
 
 ' Connect to the data source. 
 Set objConn = GetNewConnection 
 
 objCmd.CommandText = "SELECT CustomerID, CompanyName FROM Customers" 
 objCmd.CommandType = adCmdText 
 
 'Name the command. 
 objCmd.Name = "GetCustomers" 
 
 objCmd.ActiveConnection = objConn 
 
 ' Execute using Command.Name from the Connection. 
 objConn.GetCustomers objRs 
 
 ' Display. 
 Do While Not objRs.EOF 
 Debug.Print objRs(0) & vbTab & objRs(1) 
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
'EndNamedCmd 
```

