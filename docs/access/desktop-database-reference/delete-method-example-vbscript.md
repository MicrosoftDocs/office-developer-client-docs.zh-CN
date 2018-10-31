---
title: Delete 方法示例 (VBScript)
TOCTitle: Delete method example (VBScript)
ms:assetid: aa647263-334b-152b-1d5e-2abe57bd7d73
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249788(v=office.15)
ms:contentKeyID: 48546947
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 77859e4800a9a14935e56a906a2a99393b7c4169
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860438"
---
# <a name="delete-method-example-vbscript"></a><span data-ttu-id="0924b-102">Delete 方法示例 (VBScript)</span><span class="sxs-lookup"><span data-stu-id="0924b-102">Delete method example (VBScript)</span></span>


<span data-ttu-id="0924b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0924b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0924b-104">本示例使用 [Delete](delete-method-ado-recordset.md) 方法从 [Recordset](recordset-object-ado.md) 中删除指定的记录。</span><span class="sxs-lookup"><span data-stu-id="0924b-104">This example uses the [Delete](delete-method-ado-recordset.md) method to remove a specified record from a [Recordset](recordset-object-ado.md).</span></span>

<span data-ttu-id="0924b-105">在 Active Server Page (ASP) 中使用下面的示例。</span><span class="sxs-lookup"><span data-stu-id="0924b-105">Use the following example in an Active Server Page (ASP).</span></span>

<span data-ttu-id="0924b-p101">使用 **Find** 来查找文件 Adovbs.inc 并将其放置在要使用的目录中。请将以下代码剪切并粘贴到记事本或其他文本编辑器中，然后将其保存为 **DeleteVBS.asp** 。您可以在任何客户端浏览器中查看结果。</span><span class="sxs-lookup"><span data-stu-id="0924b-p101">Use **Find** to locate the file Adovbs.inc and place it in the directory you plan to use. Cut and paste the following code into Notepad or another text editor, and save it as **DeleteVBS.asp**. You can view the result in any client browser.</span></span>

<span data-ttu-id="0924b-p102">若要演练本示例，请首先尝试使用 [AddNew](addnew-method-example-vbscript.md) 示例添加一些记录。然后可以尝试删除这些记录。可以在任何客户端浏览器中查看结果。</span><span class="sxs-lookup"><span data-stu-id="0924b-p102">To exercise the example, try using the [AddNew](addnew-method-example-vbscript.md) example first to add some records. Then you can try to delete them. View the result in any client browser.</span></span>

```vb 
 
<!-- BeginDeleteVBS --> 
<%@ Language=VBScript %> 
<% ' use this meta tag instead of ADOVBS.inc%> 
<!-- METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
<HTML> 
<HEAD> 
<TITLE>ADO Delete Method</TITLE> 
</HEAD> 
<STYLE> 
<!-- 
TH { 
 background-color: #008080; 
 font-family: 'Arial Narrow','Arial',sans-serif; 
 font-size: xx-small; 
 color: white; 
 } 
TD { 
 text-align: center; 
 background-color: #f7efde; 
 font-family: 'Arial Narrow','Arial',sans-serif; 
 font-size: xx-small; 
 } 
--> 
</STYLE> 
 
<BODY> 
<H3>ADO Delete Method</H3> 
 
<% 
 ' to integrate this code replace the DataSource value in the connection string 
 
 ' connection and recordset variables 
 Dim Cnxn, strCnxn 
 Dim rsCustomers, strSQLCustomers 
 
 ' create and open connection 
 Set Cnxn = Server.CreateObject("ADODB.Connection") 
 strCnxn="Provider='sqloledb';Data Source=" & _ 
 Request.ServerVariables("SERVER_NAME") & ";" & _ 
 "Integrated Security='SSPI';Initial Catalog='Northwind';" 
 Cnxn.Open strCnxn 
 ' create and open recordset 
 Set rsCustomers = Server.CreateObject("ADODB.Recordset") 
 strSQLCustomers = "Customers" 
 rsCustomers.Open strSQLCustomers, Cnxn, adOpenKeyset, adLockOptimistic, adCmdTable 
 
 ' Move to designated record and delete it 
 If Not IsEmpty(Request.Form("WhichRecord")) Then 
 'Get value to move from Form Post method 
 Moves = Request.Form("WhichRecord") 
 
 rsCustomers.Move CInt(Moves) 
 If Not rsCustomers.EOF or rsCustomers.BOF Then 
 ' handle any db errors 
 On Error Resume Next 
 rsCustomers.Delete 1 
 If Cnxn.Errors.Count <> 0 Then 
 Response.Write "Cannot delete since there are related records in other tables." 
 Response.End 
 End If 
 rsCustomers.MoveFirst 
 On Error GoTo 0 
 Else 
 Response.Write "Not a Valid Record Number" 
 rsCustomers.MoveFirst 
 End If 
 End If 
%> 
 
<!-- BEGIN column header row for Customer Table--> 
<TABLE COLSPAN=8 CELLPADDING=5 BORDER=0> 
<TR> 
 <TH>Rec. #</TH> 
 <TH>Company Name</TH> 
 <TH>Contact Name</TH> 
 <TH>City</TH> 
</TR> 
 
 <% 
 ' Display ADO Data from Customer Table 
 ' Loop through Recordset adding one row to HTML Table each pass 
 Dim iCount 
 iCount = 0 
 Do Until rsCustomers.EOF %> 
 <TR> 
 <TD> <%= CStr(iCount) %> 
 <TD> <%= rsCustomers("CompanyName")%> </TD> 
 <TD> <%= rsCustomers("ContactName")%> </TD> 
 <TD> <%= rsCustomers("City")%> </TD> 
 </TR> 
 <% 
 iCount = iCount + 1 
 rsCustomers.MoveNext 
 Loop 
 %> 
</TABLE> 
 
<!-- Do Client side Input Data Validation Move to named record and Delete it --> 
<Center> 
<H4>Clicking Button Will Remove Designated Record</H4> 
<H5>There are <%=rsCustomers.RecordCount%> Records in this Set</H5> 
 
<Form Method=Post Action="Deletevbs.asp" Name=Form> 
 <Input Type=Text Name="WhichRecord" Size=3> 
 <Input Type=Button Name=cmdDelete Value="Delete Record"> 
</Form> 
 
</BODY> 
 
<Script Language = "VBScript"> 
Sub cmdDelete_OnClick 
 If IsNumeric(Document.Form.WhichRecord.Value) Then 
 Document.Form.WhichRecord.Value = CInt(Document.Form.WhichRecord.Value) 
 Dim Response 
 Response = MsgBox("Are You Sure About Deleting This Record?", vbYesNo, "ADO-ASP Example") 
 
 If Response = vbYes Then 
 Document.Form.Submit 
 End If 
 Else 
 MsgBox "You Must Enter a Valid Record Number",,"ADO-ASP Example" 
 End If 
End Sub 
</Script> 
 
<% 
 ' clean up 
 If rsCustomers.State = adStateOpen then 
 rsCustomers.Close 
 End If 
 If Cnxn.State = adStateOpen then 
 Cnxn.Close 
 End If 
%> 
</HTML> 
<!-- EndDeleteVBS --> 
```

