---
<span data-ttu-id="c1d8e-101"><<<<<<< 标头标题： IsolationLevel 和模式属性示例 (VB) TOCTitle: IsolationLevel 和模式属性示例 (VB) === 标题： IsolationLevel 和模式属性示例 (VB) TOCTitle: IsolationLevel 和模式属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c1d8e-101"><<<<<<< HEAD title: IsolationLevel and Mode Properties Example (VB) TOCTitle: IsolationLevel and Mode Properties Example (VB) ======= title: IsolationLevel and Mode properties example (VB) TOCTitle: IsolationLevel and Mode properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="c1d8e-102">母版页 ms:assetid: ac3ec2e7-199c-723c-ff3e-2aaf3e10aa94 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249800(v=office.15) ms:contentKeyID: 48546999 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="c1d8e-102">master ms:assetid: ac3ec2e7-199c-723c-ff3e-2aaf3e10aa94 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249800(v=office.15) ms:contentKeyID: 48546999 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="c1d8e-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="c1d8e-103"><<<<<<< HEAD</span></span>
# <a name="isolationlevel-and-mode-properties-example-vb"></a><span data-ttu-id="c1d8e-104">IsolationLevel 和 Mode 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c1d8e-104">IsolationLevel and Mode Properties Example (VB)</span></span>
=======
# <a name="isolationlevel-and-mode-properties-example-vb"></a><span data-ttu-id="c1d8e-105">IsolationLevel 和模式属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="c1d8e-105">IsolationLevel and Mode properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="c1d8e-106">master</span><span class="sxs-lookup"><span data-stu-id="c1d8e-106">master</span></span>


<span data-ttu-id="c1d8e-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c1d8e-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c1d8e-108">本示例使用 [Mode](mode-property-ado.md) 属性打开一个独占连接，并使用 [IsolationLevel](isolationlevel-property-ado.md) 属性打开一个在其他事务的隔离级别上实施的事务。</span><span class="sxs-lookup"><span data-stu-id="c1d8e-108">This example uses the [Mode](mode-property-ado.md) property to open an exclusive connection, and the [IsolationLevel](isolationlevel-property-ado.md) property to open a transaction that is conducted in isolation of other transactions.</span></span>

```vb 
 
'BeginIsolationLevelVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim Cnxn As ADODB.Connection 
 Dim rstTitles As ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLTitles As String 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Mode = adModeShareExclusive 
 Cnxn.IsolationLevel = adXactIsolated 
 Cnxn.Open strCnxn 
 
 ' open Titles table 
 Set rstTitles = New ADODB.Recordset 
 strSQLTitles = "titles" 
 rstTitles.Open strSQLTitles, Cnxn, adOpenDynamic, adLockPessimistic, adCmdTable 
 
 Cnxn.BeginTrans 
 
 ' Display connection mode 
 If Cnxn.Mode = adModeShareExclusive Then 
 MsgBox "Connection mode is exclusive." 
 Else 
 MsgBox "Connection mode is not exclusive." 
 End If 
 
 ' Display isolation level 
 If Cnxn.IsolationLevel = adXactIsolated Then 
 MsgBox "Transaction is isolated." 
 Else 
 MsgBox "Transaction is not isolated." 
 End If 
 
 ' Change the type of psychology titles 
 Do Until rstTitles.EOF 
 If Trim(rstTitles!Type) = "psychology" Then 
 rstTitles!Type = "self_help" 
 rstTitles.Update 
 End If 
 rstTitles.MoveNext 
 Loop 
 
 ' Print current data in recordset 
 rstTitles.Requery 
 Do While Not rstTitles.EOF 
 Debug.Print rstTitles!Title & " - " & rstTitles!Type 
 rstTitles.MoveNext 
 Loop 
 
 ' clean up 
 rstTitles.Close 
 Cnxn.RollbackTrans 
 Cnxn.Close 
 Set rstTitles = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstTitles Is Nothing Then 
 If rstTitles.State = adStateOpen Then rstTitles.Close 
 End If 
 Set rstTitles = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then 
 Cnxn.RollbackTrans 
 Cnxn.Close 
 End If 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndIsolationLevelVB 
```

