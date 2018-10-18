---
<span data-ttu-id="53ba5-101"><<<<<<< 标头标题： 版本属性示例 (VB) TOCTitle： 版本属性示例 (VB) === 标题： Version 属性示例 (VB) TOCTitle: Version 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="53ba5-101"><<<<<<< HEAD title: Version Property Example (VB) TOCTitle: Version Property Example (VB) ======= title: Version property example (VB) TOCTitle: Version property example (VB)</span></span>
>>>>>>> <span data-ttu-id="53ba5-102">母版页 ms:assetid: ffb7b04a-55b9-fa2f-41ec-44af225bd15f ms:mtpsurl: https://msdn.microsoft.com/library/JJ250315(v=office.15) ms:contentKeyID: 48548968 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="53ba5-102">master ms:assetid: ffb7b04a-55b9-fa2f-41ec-44af225bd15f ms:mtpsurl: https://msdn.microsoft.com/library/JJ250315(v=office.15) ms:contentKeyID: 48548968 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="53ba5-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="53ba5-103"><<<<<<< HEAD</span></span>
# <a name="version-property-example-vb"></a><span data-ttu-id="53ba5-104">Version 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="53ba5-104">Version Property Example (VB)</span></span>
=======
# <a name="version-property-example-vb"></a><span data-ttu-id="53ba5-105">Version 属性示例 (VB)</span><span class="sxs-lookup"><span data-stu-id="53ba5-105">Version property example (VB)</span></span>
>>>>>>> <span data-ttu-id="53ba5-106">master</span><span class="sxs-lookup"><span data-stu-id="53ba5-106">master</span></span>


<span data-ttu-id="53ba5-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="53ba5-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="53ba5-p101">此示例使用 [Connection](version-property-ado.md) 对象的 [Version](connection-object-ado.md) 属性来显示当前的 ADO 版本。它还使用多个动态属性来显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="53ba5-p101">This example uses the [Version](version-property-ado.md) property of a [Connection](connection-object-ado.md) object to display the current ADO version. It also uses several dynamic properties to show:</span></span>

  - <span data-ttu-id="53ba5-110">当前的 DBMS 名称和版本。</span><span class="sxs-lookup"><span data-stu-id="53ba5-110">the current DBMS name and version.</span></span>

  - <span data-ttu-id="53ba5-111">OLE DB 版本。</span><span class="sxs-lookup"><span data-stu-id="53ba5-111">OLE DB version.</span></span>

  - <span data-ttu-id="53ba5-112">提供程序名称和版本。</span><span class="sxs-lookup"><span data-stu-id="53ba5-112">provider name and version.</span></span>

  - <span data-ttu-id="53ba5-113">ODBC 版本。</span><span class="sxs-lookup"><span data-stu-id="53ba5-113">ODBC version.</span></span>

  - <span data-ttu-id="53ba5-114">ODBC 驱动程序名称和版本。</span><span class="sxs-lookup"><span data-stu-id="53ba5-114">ODBC driver name and version.</span></span>

<!-- end list -->

```vb 
 
'BeginVersionVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 Dim Cnxn As ADODB.Connection 
 Dim strCnxn As String 
 Dim strVersionInfo As String 
 
 ' Open connection 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 strVersionInfo = "ADO Version: " & Cnxn.Version & vbCr 
 strVersionInfo = strVersionInfo & "DBMS Name: " & Cnxn.Properties("DBMS Name") & vbCr 
 strVersionInfo = strVersionInfo & "DBMS Version: " & Cnxn.Properties("DBMS Version") & vbCr 
 strVersionInfo = strVersionInfo & "OLE DB Version: " & Cnxn.Properties("OLE DB Version") & vbCr 
 strVersionInfo = strVersionInfo & "Provider Name: " & Cnxn.Properties("Provider Name") & vbCr 
 strVersionInfo = strVersionInfo & "Provider Version: " & Cnxn.Properties("Provider Version") & vbCr 
 
 MsgBox strVersionInfo 
 
 ' clean up 
 Cnxn.Close 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndVersionVB 
```

