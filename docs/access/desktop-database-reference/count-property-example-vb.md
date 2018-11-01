---
title: Count 属性示例 (VB)
TOCTitle: Count property example (VB)
ms:assetid: 9fea66f7-a4ed-fe2e-c199-672b910fef47
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249734(v=office.15)
ms:contentKeyID: 48546695
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c47436a5c701abb9bff29fea718fa7119594cd1a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873619"
---
# <a name="count-property-example-vb"></a><span data-ttu-id="84f1a-102">Count 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="84f1a-102">Count property example (VB)</span></span>


<span data-ttu-id="84f1a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="84f1a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="84f1a-104">以下示例演示在***员工***数据库中的两个集合的[Count](count-property-ado.md)属性。</span><span class="sxs-lookup"><span data-stu-id="84f1a-104">This example demonstrates the [Count](count-property-ado.md) property with two collections in the ***Employee*** database.</span></span> <span data-ttu-id="84f1a-105">该属性获得每个集合中的对象数，并设置枚举这两个集合的循环的上限。</span><span class="sxs-lookup"><span data-stu-id="84f1a-105">The property obtains the number of objects in each collection, and sets the upper limit for loops that enumerate these collections.</span></span> <span data-ttu-id="84f1a-106">另一种不使用 **Count** 属性枚举这些集合的方式是使用语句。</span><span class="sxs-lookup"><span data-stu-id="84f1a-106">Another way to enumerate these collections without using the **Count** property would be to use statements.</span></span>

```vb 
 
'BeginCountVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' recordset and connection variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strSQLEmployees As String 
 Dim strCnxn As String 
 
 Dim intLoop As Integer 
 
 ' Open a connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Northwind';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open recordset with data from Employee table 
 Set rstEmployees = New ADODB.Recordset 
 strSQLEmployees = "Employees" 
 'rstEmployees.Open strSQLEmployee, Cnxn, , , adCmdTable 
 rstEmployees.Open strSQLEmployees, Cnxn, adOpenForwardOnly, adLockReadOnly, adCmdTable 
 'the above two lines opening the recordset are identical as 
 'the default values for CursorType and LockType arguments match those specified 
 
 ' Print information about Fields collection 
 Debug.Print rstEmployees.Fields.Count & " Fields in Employee" 
 
 For intLoop = 0 To rstEmployees.Fields.Count - 1 
 Debug.Print " " & rstEmployees.Fields(intLoop).Name 
 Next intLoop 
 
 ' Print information about Properties collection 
 Debug.Print rstEmployees.Properties.Count & " Properties in Employee" 
 
 For intLoop = 0 To rstEmployees.Properties.Count - 1 
 Debug.Print " " & rstEmployees.Properties(intLoop).Name 
 Next intLoop 
 
 ' clean up 
 rstEmployees.Close 
 Cnxn.Close 
 Set rstEmployees = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstEmployees Is Nothing Then 
 If rstEmployees.State = adStateOpen Then rstEmployees.Close 
 End If 
 Set rstEmployees = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndCountVB 
```

