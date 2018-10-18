---
<span data-ttu-id="f0934-101"><<<<<<< 标头标题： AbsolutePage、 PageCount 和 PageSize 属性示例 (JScript) TOCTitle: AbsolutePage、 PageCount 和 PageSize 属性示例 (JScript) ms:assetid: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl:https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID: 48545506 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="f0934-101"><<<<<<< HEAD title: AbsolutePage, PageCount, and PageSize Properties Example (JScript) TOCTitle: AbsolutePage, PageCount, and PageSize Properties Example (JScript) ms:assetid: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID: 48545506 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-jscript"></a><span data-ttu-id="f0934-102">AbsolutePage、PageCount 和 PageSize 属性示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="f0934-102">AbsolutePage, PageCount, and PageSize Properties Example (JScript)</span></span>

<span data-ttu-id="f0934-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0934-103">**Applies to**: Access 2013 | Office 2013</span></span>

<a name="this-example-demonstrates-the-absolutepage-pagecount-and-pagesize-properties-cut-and-paste-the-following-code-to-notepad-or-another-text-editor-and-save-it-as-absolutepagejsasp"></a><span data-ttu-id="f0934-104">以下示例演示 AbsolutePage、 PageCount 和 PageSize 属性。</span><span class="sxs-lookup"><span data-stu-id="f0934-104">This example demonstrates the AbsolutePage, PageCount, and PageSize properties.</span></span> <span data-ttu-id="f0934-105">请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **AbsolutePageJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="f0934-105">Cut and paste the following code to Notepad or another text editor, and save it as **AbsolutePageJS.asp**.</span></span>
=======
<span data-ttu-id="f0934-106">标题： AbsolutePage、 PageCount 和 PageSize 属性示例 (JScript) TOCTitle: AbsolutePage、 PageCount 和 PageSize 属性示例 (JScript) ms:assetid: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID:48545506 ms.date: 10/17/2018 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="f0934-106">title: AbsolutePage, PageCount, and PageSize properties example (JScript) TOCTitle: AbsolutePage, PageCount, and PageSize properties example (JScript) ms:assetid: 6df29022-16f2-c7d8-d45b-b9998e929030 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249434(v=office.15) ms:contentKeyID: 48545506 ms.date: 10/17/2018 mtps_version: v=office.15</span></span>
---

# <a name="absolutepage-pagecount-and-pagesize-properties-example-jscript"></a><span data-ttu-id="f0934-107">AbsolutePage、 PageCount 和 PageSize 属性示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="f0934-107">AbsolutePage, PageCount, and PageSize properties example (JScript)</span></span>

<span data-ttu-id="f0934-108">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0934-108">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f0934-109">此示例使用 [AbsolutePage](absolutepage-property-ado.md)、[PageCount](pagecount-property-ado.md) 和 [PageSize](pagesize-property-ado.md) 属性显示 ***Employees***（雇员）表中的姓名和雇用日期，每次显示五条记录。</span><span class="sxs-lookup"><span data-stu-id="f0934-109">This example uses the [AbsolutePage](absolutepage-property-ado.md), [PageCount](pagecount-property-ado.md), and [PageSize](pagesize-property-ado.md) properties to display names and hire dates from the ***Employees*** table, five records at a time.</span></span> <span data-ttu-id="f0934-110">请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **AbsolutePageJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="f0934-110">Cut and paste the following code to Notepad or another text editor, and save it as **AbsolutePageJS.asp**.</span></span>
>>>>>>> <span data-ttu-id="f0934-111">master</span><span class="sxs-lookup"><span data-stu-id="f0934-111">master</span></span>

```javascript
<!-- BeginAbsolutePageJS --> 
<%@LANGUAGE="JScript" %> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<html> 
 
<head> 
<title>AbsolutePage, PageSize, and PageSize Properties (JScript)</title> 
<style> 
<!-- 
BODY { 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 BACKGROUND-COLOR:white; 
 COLOR:black; 
 } 
.thead2 { 
 background-color: #800000; 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 font-size: x-small; 
 color: white; 
 } 
.tbody { 
 text-align: center; 
 background-color: #f7efde; 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 font-size: x-small; 
 } 
--> 
</style> 
</head> 
 
<body bgcolor="White"> 
<h1>AbsolutePage, PageSize, and PageSize Properties (JScript)</h1> 
<% 
 // connection and recordset variables 
 var Cnxn = Server.CreateObject("ADODB.Connection") 
 var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='Northwind';Integrated Security='SSPI';"; 
 var rsEmployee = Server.CreateObject("ADODB.Recordset"); 
 // display variables 
 var strMessage, iRecord, iPageCount; 
 
 try 
 { 
 // open connection 
 Cnxn.Open(strCnxn); 
 
 // Open a recordset on the Employee table using 
 // a client-side cursor to enable AbsolutePage property. 
 rsEmployee.CursorLocation = adUseClient; 
 rsEmployee.Open("employees", strCnxn, adOpenStatic, adLockOptimistic, adCmdTable); 
 
 // Set PageSize to five to display names and hire dates of five employees at a time 
 rsEmployee.PageSize = 5; 
 iPageCount = rsEmployee.PageCount; 
 
 // Write header information to the document 
 Response.Write('<p align="center">There are ' + iPageCount); 
 Response.Write(" pages, each containing "); 
 Response.Write(rsEmployee.PageSize + " or fewer records.</p>"); 
 Response.Write('<table border="0" align="center">'); 
 Response.Write('<tr class="thead2">'); 
 Response.Write("<th>Page</th><th>Name</th><th>Hire Date</th></tr>"); 
 
 for (var i=1; i<=iPageCount; i++) 
 { 
 rsEmployee.AbsolutePage = i; 
 
 for (iRecord = 1; iRecord <= rsEmployee.PageSize; iRecord++) 
 { 
 strMessage = ""; 
 
 // Start a new table row. 
 strMessage = '<tr class="tbody">'; 
 
 // First column in row contains page number on 
 // first record of each page. Otherwise, the column 
 // contains a non-breaking space. 
 if (iRecord == 1) 
 strMessage += "<td>Page " + i + " of " + rsEmployee.PageCount + "</td>" 
 else 
 strMessage += "<td>&nbsp;</td>"; 
 
 // First and last name are in first column. 
 strMessage += "<TD>" + rsEmployee.Fields("FirstName") + " "; 
 strMessage += rsEmployee.Fields("LastName") + " " + "</td>"; 
 
 // Hire date in second column. 
 strMessage += "<td>" + rsEmployee.Fields("HireDate") + "</td>"; 
 
 // End the row. 
 strMessage += "</tr>"; 
 
 // Write line to document. 
 Response.Write(strMessage); 
 
 // Get next record. 
 rsEmployee.MoveNext; 
 
 if (rsEmployee.EOF) 
 break; 
 } 
 } 
 
 // Finish writing table. 
 Response.Write("</table>"); 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // 'clean up 
 if (rsEmployee.State == adStateOpen) 
 rsEmployee.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsEmployee = null; 
 Cnxn = null; 
 } 
%> 
 
</body> 
 
</html> 
<!-- EndAbsolutePageJS --> 
```

