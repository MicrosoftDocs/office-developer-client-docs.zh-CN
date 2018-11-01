---
title: Find 方法示例 (JScript)
TOCTitle: Find method example (JScript)
ms:assetid: 87db96d6-4ed4-0807-8bff-62d978d4a008
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249589(v=office.15)
ms:contentKeyID: 48546116
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 21d123d61c18f28adc8380f1eb45bbadc585ee9d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877308"
---
# <a name="find-method-example-jscript"></a><span data-ttu-id="16179-102">Find 方法示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="16179-102">Find method example (JScript)</span></span>


<span data-ttu-id="16179-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="16179-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="16179-104">此示例使用[Recordset](recordset-object-ado.md)对象的[Find](find-method-ado.md)方法查找和公司中显示***罗斯文***数据库名称开头的字母 G.剪切并粘贴到记事本或其他文本编辑器，下面的代码，将其保存为**FindJS.asp**。</span><span class="sxs-lookup"><span data-stu-id="16179-104">This example uses the [Recordset](recordset-object-ado.md) object's [Find](find-method-ado.md) method to locate and display the companies in the ***Northwind*** database whose name begins with the letter G. Cut and paste the following code to Notepad or another text editor, and save it as **FindJS.asp**.</span></span>

```javascript 
 
<!-- BeginFindJS --> 
<%@ Language=JavaScript %> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<html> 
 
<head> 
<title>ADO Recordset.Find Example</title> 
<style> 
<!-- 
BODY { 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 BACKGROUND-COLOR:white; 
 COLOR:black; 
 } 
.thead { 
 background-color: #008080; 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 font-size: x-small; 
 color: white; 
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
 
<body bgcolor="white"> 
 
<h1>ADO Recordset.Find Example</h1> 
<% 
 // connection and recordset variables 
 var Cnxn = Server.CreateObject("ADODB.Connection"); 
 var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='Northwind';Integrated Security='SSPI';"; 
 var rsCustomers = Server.CreateObject("ADODB.Recordset"); 
 // display string 
 var strMessage; 
 var strFind; 
 
 try 
 { 
 // open connection 
 Cnxn.Open(strCnxn); 
 
 //create recordset using object refs 
 SQLCustomers = "select * from Customers;"; 
 
 rsCustomers.ActiveConnection = Cnxn; 
 rsCustomers.CursorLocation = adUseClient; 
 rsCustomers.CursorType = adOpenKeyset; 
 rsCustomers.LockType = adLockOptimistic; 
 rsCustomers.Source = SQLCustomers; 
 
 rsCustomers.Open(); 
 rsCustomers.MoveFirst(); 
 
 //find criteria 
 strFind = "CompanyName like 'g%'" 
 rsCustomers.Find(strFind); 
 
 if (rsCustomers.EOF) { 
 Response.Write("No records matched "); 
 Response.Write(SQLCustomers & "So cannot make table..."); 
 Cnxn.Close(); 
 Response.End(); 
 } 
 else { 
 Response.Write('<table width="100%" border="2">'); 
 Response.Write('<tr class="thead2">'); 
 // Put Headings On The Table for each Field Name 
 for (thisField = 0; thisField < rsCustomers.Fields.Count; thisField++) { 
 fieldObject = rsCustomers.Fields(thisField); 
 Response.Write('<th width="' + Math.floor(100 / rsCustomers.Fields.Count) + '%">' + fieldObject.Name + "</th>"); 
 } 
 Response.Write("</tr>"); 
 
 while (!rsCustomers.EOF) { 
 Response.Write('<tr class="tbody">'); 
 for(thisField=0; thisField<rsCustomers.Fields.Count; thisField++) { 
 fieldObject = rsCustomers.Fields(thisField); 
 strField = fieldObject.Value; 
 if (strField == null) 
 strField = "-Null-"; 
 if (strField == "") 
 strField = ""; 
 Response.Write("<td>" + strField + "</td>"); 
 } 
 rsCustomers.Find(strFind, 1, adSearchForward) 
 Response.Write("</tr>"); 
 } 
 Response.Write("</table>"); 
 } 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // clean up 
 if (rsCustomers.State == adStateOpen) 
 rsCustomers.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsCustomers = null; 
 Cnxn = null; 
 } 
%> 
 
</body> 
 
</html> 
<!-- EndFindJS --> 
 
```

