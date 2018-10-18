---
<span data-ttu-id="e7a59-101"><<<<<<< 标头标题： Seek 方法和 Index 属性示例 (VB) TOCTitle: Seek 方法和 Index 属性示例 (VB) === 标题： Seek 方法和 Index 属性示例 (VB) TOCTitle: Seek 方法和 Index 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="e7a59-101"><<<<<<< HEAD title: Seek Method and Index Property Example (VB) TOCTitle: Seek Method and Index Property Example (VB) ======= title: Seek Method and Index property example (VB) TOCTitle: Seek Method and Index property example (VB)</span></span>
>>>>>>> <span data-ttu-id="e7a59-102">母版页 ms:assetid: c3ddb72c-2b19-53c8-9779-2c503486e44e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249957(v=office.15) ms:contentKeyID: 48547577 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="e7a59-102">master ms:assetid: c3ddb72c-2b19-53c8-9779-2c503486e44e ms:mtpsurl: https://msdn.microsoft.com/library/JJ249957(v=office.15) ms:contentKeyID: 48547577 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="e7a59-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="e7a59-103"><<<<<<< HEAD</span></span>
# <a name="seek-method-and-index-property-example-vb"></a><span data-ttu-id="e7a59-104">Seek 方法和 Index 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="e7a59-104">Seek Method and Index Property Example (VB)</span></span>
=======
# <a name="seek-method-and-index-property-example-vb"></a><span data-ttu-id="e7a59-105">Seek 方法和 Index 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="e7a59-105">Seek Method and Index property example (VB)</span></span>
>>>>>>> <span data-ttu-id="e7a59-106">master</span><span class="sxs-lookup"><span data-stu-id="e7a59-106">master</span></span>


<span data-ttu-id="e7a59-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e7a59-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e7a59-108">以下示例将 [Recordset](recordset-object-ado.md) 对象的 [Seek](seek-method-ado.md) 方法和 [Index](index-property-ado.md) 属性与给定的 ***Employee ID***（雇员 ID）结合起来使用，以便在 Nwind.mdb 数据库的 ***Employees***（雇员）表中查找雇员的姓名。</span><span class="sxs-lookup"><span data-stu-id="e7a59-108">This example uses the [Recordset](recordset-object-ado.md) object's [Seek](seek-method-ado.md) method and [Index](index-property-ado.md) property in conjunction with a given ***Employee ID***, to locate the employee's name in the ***Employees*** table of the Nwind.mdb database.</span></span>

```vb 
 
'BeginSeekVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' To integrate this code replace the data source 
 ' in the connection string 
 
 'recordset and connection variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQLEmployees As String 
 
 Dim strID As String 
 Dim strPrompt As String 
 strPrompt = "Enter an EmployeeID (e.g., 1 to 9)" 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='Microsoft.Jet.OLEDB.4.0';" & _ 
 "Data Source='c:\Program Files\Microsoft Office\Office\Samples\northwind.mdb';" 
 Cnxn.Open strCnxn 
 
 ' open recordset server-side for indexing 
 Set rstEmployees = New ADODB.Recordset 
 rstEmployees.CursorLocation = adUseServer 
 strSQLEmployees = "employees" 
 rstEmployees.Open strSQLEmployees, strCnxn, adOpenKeyset, adLockReadOnly, adCmdTableDirect 
 
 ' Does this provider support Seek and Index? 
 If rstEmployees.Supports(adIndex) And rstEmployees.Supports(adSeek) Then 
 rstEmployees.Index = "PrimaryKey" 
 ' Display all the employees 
 rstEmployees.MoveFirst 
 Do While rstEmployees.EOF = False 
 Debug.Print rstEmployees!EmployeeId; ": "; rstEmployees!firstname; " "; _ 
 rstEmployees!LastName 
 rstEmployees.MoveNext 
 Loop 
 
 ' Prompt the user for an EmployeeID between 1 and 9 
 rstEmployees.MoveFirst 
 Do 
 strID = LCase(Trim(InputBox(strPrompt, "Seek Example"))) 
 ' Quit if strID is a zero-length string (CANCEL, null, etc.) 
 If Len(strID) = 0 Then Exit Do 
 If Len(strID) = 1 And strID >= "1" And strID <= "9" Then 
 rstEmployees.Seek Array(strID), adSeekFirstEQ 
 If rstEmployees.EOF Then 
 Debug.Print "Employee not found." 
 Else 
 Debug.Print strID; ": Employee='"; rstEmployees!firstname; " "; _ 
 rstEmployees!LastName; "'" 
 End If 
 End If 
 Loop 
 End If 
 
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
'EndSeekVB 
```

