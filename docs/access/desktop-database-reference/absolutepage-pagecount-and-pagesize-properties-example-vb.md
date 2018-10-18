---
<span data-ttu-id="d3ff5-101"><<<<<<< 标头标题： AbsolutePage、 PageCount 和 PageSize 属性示例 (VB) TOCTitle: AbsolutePage、 PageCount 和 PageSize 属性示例 (VB) ms:assetid: bd13fb6c-8ee4-7475-ef2d-9067e30918de ms:mtpsurl: https://msdn.microsoft.com/library/JJ249911(v=office.15)ms:contentKeyID: 48547426 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="d3ff5-101"><<<<<<< HEAD title: AbsolutePage, PageCount, and PageSize Properties Example (VB) TOCTitle: AbsolutePage, PageCount, and PageSize Properties Example (VB) ms:assetid: bd13fb6c-8ee4-7475-ef2d-9067e30918de ms:mtpsurl: https://msdn.microsoft.com/library/JJ249911(v=office.15) ms:contentKeyID: 48547426 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-vb"></a><span data-ttu-id="d3ff5-102">AbsolutePage、PageCount 和 PageSize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="d3ff5-102">AbsolutePage, PageCount, and PageSize Properties Example (VB)</span></span>
<span data-ttu-id="d3ff5-103">=== 标题： AbsolutePage、 PageCount 和 PageSize 属性示例 (VB) TOCTitle: AbsolutePage、 PageCount 和 PageSize 属性示例 (VB) ms:assetid: bd13fb6c-8ee4-7475-ef2d-9067e30918de ms:mtpsurl: https://msdn.microsoft.com/library/JJ249911(v=office.15) ms:contentKeyID: 48547426ms.date: 10/17/2018 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="d3ff5-103">======= title: AbsolutePage, PageCount, and PageSize properties example (VB) TOCTitle: AbsolutePage, PageCount, and PageSize properties example (VB) ms:assetid: bd13fb6c-8ee4-7475-ef2d-9067e30918de ms:mtpsurl: https://msdn.microsoft.com/library/JJ249911(v=office.15) ms:contentKeyID: 48547426 ms.date: 10/17/2018 mtps_version: v=office.15</span></span>
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-vb"></a><span data-ttu-id="d3ff5-104">AbsolutePage、 PageCount 和 PageSize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="d3ff5-104">AbsolutePage, PageCount, and PageSize properties example (VB)</span></span>
>>>>>>> <span data-ttu-id="d3ff5-105">master</span><span class="sxs-lookup"><span data-stu-id="d3ff5-105">master</span></span>


<span data-ttu-id="d3ff5-106">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d3ff5-106">**Applies to**: Access 2013 | Office 2013</span></span>

<a name="-head"></a><span data-ttu-id="d3ff5-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d3ff5-107"><<<<<<< HEAD</span></span>
=======
<span data-ttu-id="d3ff5-108">此示例使用 [AbsolutePage](absolutepage-property-ado.md)、[PageCount](pagecount-property-ado.md) 和 [PageSize](pagesize-property-ado.md) 属性显示 ***Employees***（雇员）表中的姓名和雇用日期，每次显示五条记录。</span><span class="sxs-lookup"><span data-stu-id="d3ff5-108">This example uses the [AbsolutePage](absolutepage-property-ado.md), [PageCount](pagecount-property-ado.md), and [PageSize](pagesize-property-ado.md) properties to display names and hire dates from the ***Employees*** table, five records at a time.</span></span>

>>>>>>> <span data-ttu-id="d3ff5-109">master</span><span class="sxs-lookup"><span data-stu-id="d3ff5-109">master</span></span>
```vb 
 
'BeginAbsolutePageVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim rstEmployees As ADODB.Recordset 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strSQL As String 
 'record variables 
 Dim strMessage As String 
 Dim intPage As Integer 
 Dim intPageCount As Integer 
 Dim intRecord As Integer 
 
 'Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' Open employee recordset 
 ' Use client cursor to enable AbsolutePosition property 
 Set rstEmployees = New ADODB.Recordset 
 strSQL = "employee" 
 rstEmployees.Open strSQL, strCnxn, adUseClient, adLockReadOnly, adCmdTable 
 
 ' Display names and hire dates, five records at a time 
 rstEmployees.PageSize = 5 
 intPageCount = rstEmployees.PageCount 
 For intPage = 1 To intPageCount 
 rstEmployees.AbsolutePage = intPage 
 strMessage = "" 
 For intRecord = 1 To rstEmployees.PageSize 
 strMessage = strMessage & _ 
 rstEmployees!fname & " " & _ 
 rstEmployees!lname & " " & _ 
 rstEmployees!hire_date & vbCr 
 rstEmployees.MoveNext 
 If rstEmployees.EOF Then Exit For 
 Next intRecord 
 MsgBox strMessage 
 Next intPage 
 
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
'EndAbsolutePageVB 
```

