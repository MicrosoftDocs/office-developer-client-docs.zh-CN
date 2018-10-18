---
<span data-ttu-id="fc62e-101"><<<<<<< 标头标题： Sort 属性示例 (VB) TOCTitle: Sort 属性示例 (VB) === 标题： Sort 属性示例 (VB) TOCTitle: Sort 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="fc62e-101"><<<<<<< HEAD title: Sort Property Example (VB) TOCTitle: Sort Property Example (VB) ======= title: Sort property example (VB) TOCTitle: Sort property example (VB)</span></span>
>>>>>>> <span data-ttu-id="fc62e-102">母版页 ms:assetid: 6f981e5e-7ee8-e1e7-bea9-7c2081400391 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249440(v=office.15) ms:contentKeyID: 48545539 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="fc62e-102">master ms:assetid: 6f981e5e-7ee8-e1e7-bea9-7c2081400391 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249440(v=office.15) ms:contentKeyID: 48545539 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="fc62e-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="fc62e-103"><<<<<<< HEAD</span></span>
# <a name="sort-property-example-vb"></a><span data-ttu-id="fc62e-104">Sort 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="fc62e-104">Sort Property Example (VB)</span></span>
=======
# <a name="sort-property-example-vb"></a><span data-ttu-id="fc62e-105">Sort 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="fc62e-105">Sort property example (VB)</span></span>
>>>>>>> <span data-ttu-id="fc62e-106">master</span><span class="sxs-lookup"><span data-stu-id="fc62e-106">master</span></span>


<span data-ttu-id="fc62e-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="fc62e-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="fc62e-108">此示例使用[Recordset](recordset-object-ado.md)对象的[Sort](sort-property-ado.md)属性重新排列**Recordset**派生自***Pubs***数据库的***Authors***表的行。</span><span class="sxs-lookup"><span data-stu-id="fc62e-108">This example uses the [Recordset](recordset-object-ado.md) object's [Sort](sort-property-ado.md) property to reorder the rows of a **Recordset** derived from the ***Authors*** table of the ***Pubs*** database.</span></span> <span data-ttu-id="fc62e-109">由辅助实用程序例程打印每行。</span><span class="sxs-lookup"><span data-stu-id="fc62e-109">A secondary utility routine prints each row.</span></span>

```vb 
 
'BeginSortVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 ' connection and recordset variables 
 Dim Cnxn As New ADODB.Connection 
 Dim rstAuthors As New ADODB.Recordset 
 Dim strCnxn As String 
 Dim strSQLAuthors As String 
 
 Dim strTitle As String 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' open client-side recordset to enable sort method 
 Set rstAuthors = New ADODB.Recordset 
 rstAuthors.CursorLocation = adUseClient 
 strSQLAuthors = "SELECT * FROM Authors" 
 rstAuthors.Open strSQLAuthors, Cnxn, adOpenStatic, adLockReadOnly, adCmdText 
 
 ' sort the recordset last name ascending 
 rstAuthors.Sort = "au_lname ASC, au_fname ASC" 
 ' show output 
 Debug.Print "Last Name Ascending:" 
 Debug.Print "First Name Last Name" & vbCr 
 
 rstAuthors.MoveFirst 
 Do Until rstAuthors.EOF 
 Debug.Print rstAuthors!au_fname & " " & rstAuthors!au_lname 
 rstAuthors.MoveNext 
 Loop 
 
 ' sort the recordset last name descending 
 rstAuthors.Sort = "au_lname DESC, au_fname ASC" 
 ' show output 
 Debug.Print "Last Name Descending" 
 Debug.Print "First Name Last Name" & vbCr 
 
 Do Until rstAuthors.EOF 
 Debug.Print rstAuthors!au_fname & " " & rstAuthors!au_lname 
 rstAuthors.MoveNext 
 Loop 
 
 ' clean up 
 rstAuthors.Close 
 Cnxn.Close 
 Set rstAuthors = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstAuthors Is Nothing Then 
 If rstAuthors.State = adStateOpen Then rstAuthors.Close 
 End If 
 Set rstAuthors = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndSortVB 
```

<span data-ttu-id="fc62e-110">这是打印给定标题以及所指定的 **Recordset** 的内容的辅助实用程序例程。</span><span class="sxs-lookup"><span data-stu-id="fc62e-110">This is the secondary utility routine that prints the given title, and the contents of the specified **Recordset**.</span></span>

```vb 
 
Attribute VB_Name = "Sort" 
```

