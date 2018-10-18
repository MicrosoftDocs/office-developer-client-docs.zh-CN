---
<span data-ttu-id="7b551-101"><<<<<<< 标头标题： CacheSize 属性示例 (VB) TOCTitle: CacheSize 属性示例 (VB) === 标题： CacheSize 属性示例 (VB) TOCTitle: CacheSize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="7b551-101"><<<<<<< HEAD title: CacheSize Property Example (VB) TOCTitle: CacheSize Property Example (VB) ======= title: CacheSize property example (VB) TOCTitle: CacheSize property example (VB)</span></span>
>>>>>>> <span data-ttu-id="7b551-102">母版页 ms:assetid: 558b7718-d32d-45ea-554d-fce0e27d9504 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249287(v=office.15) ms:contentKeyID: 48544934 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="7b551-102">master ms:assetid: 558b7718-d32d-45ea-554d-fce0e27d9504 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249287(v=office.15) ms:contentKeyID: 48544934 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="7b551-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7b551-103"><<<<<<< HEAD</span></span>
# <a name="cachesize-property-example-vb"></a><span data-ttu-id="7b551-104">CacheSize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="7b551-104">CacheSize Property Example (VB)</span></span>
=======
# <a name="cachesize-property-example-vb"></a><span data-ttu-id="7b551-105">CacheSize 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="7b551-105">CacheSize property example (VB)</span></span>
>>>>>>> <span data-ttu-id="7b551-106">master</span><span class="sxs-lookup"><span data-stu-id="7b551-106">master</span></span>


<span data-ttu-id="7b551-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b551-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7b551-108">此示例使用 [CacheSize](cachesize-property-ado.md) 属性显示在使用和不使用 30 条记录大小的缓存的情况下执行一个操作时的性能差异。</span><span class="sxs-lookup"><span data-stu-id="7b551-108">This example uses the [CacheSize](cachesize-property-ado.md) property to show the difference in performance for an operation performed with and without a 30-record cache.</span></span>

```vb 
 
'BeginCacheSizeVB 
 
 'To integrate this code 
 'replace the data source and initial catalog values 
 'in the connection string 
 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'recordset and connection variables 
 Dim rstRoySched As ADODB.Recordset 
 Dim strSQLSched As String 
 Dim strCnxn As String 
 'record variables 
 Dim sngStart As Single 
 Dim sngEnd As Single 
 Dim sngNoCache As Single 
 Dim sngCache As Single 
 Dim intLoop As Integer 
 Dim strTemp As String 
 
 ' Open the connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 
 ' Open the RoySched Table 
 Set rstRoySched = New ADODB.Recordset 
 strSQLSched = "roysched" 
 rstRoySched.Open strSQLSched, strCnxn, , , adCmdTable 
 
 ' Enumerate the Recordset object twice and 
 ' record the elapsed time 
 sngStart = Timer 
 
 For intLoop = 1 To 2 
 rstRoySched.MoveFirst 
 
 If Not rstRoySched.EOF Then 
 ' Execute a simple operation for the 
 ' performance test 
 Do 
 strTemp = rstRoySched!title_id 
 rstRoySched.MoveNext 
 Loop Until rstRoySched.EOF 
 End If 
 Next intLoop 
 
 sngEnd = Timer 
 sngNoCache = sngEnd - sngStart 
 
 ' Cache records in groups of 30 records. 
 rstRoySched.MoveFirst 
 rstRoySched.CacheSize = 30 
 sngStart = Timer 
 
 ' Enumerate the Recordset object twice and record 
 ' the elapsed time 
 For intLoop = 1 To 2 
 rstRoySched.MoveFirst 
 Do While Not rstRoySched.EOF 
 ' Execute a simple operation for the 
 ' performance test 
 strTemp = rstRoySched!title_id 
 rstRoySched.MoveNext 
 Loop 
 Next intLoop 
 
 sngEnd = Timer 
 sngCache = sngEnd - sngStart 
 
 ' Display performance results. 
 MsgBox "Caching Performance Results:" & vbCr & _ 
 " No cache: " & Format(sngNoCache, "##0.000") & " seconds" & vbCr & _ 
 " 30-record cache: " & Format(sngCache, "##0.000") & " seconds" 
 
 ' clean up 
 rstRoySched.Close 
 Set rstRoySched = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rstRoySched Is Nothing Then 
 If rstRoySched.State = adStateOpen Then rstRoySched.Close 
 End If 
 Set rstRoySched = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndCacheSizeVB 
```

