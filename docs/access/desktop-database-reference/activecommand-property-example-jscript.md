---
title: ActiveCommand 属性示例 (JScript)
TOCTitle: ActiveCommand Property Example (JScript)
ms:assetid: ae67b69c-23d9-8c88-763a-a9a63499be32
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249824(v=office.15)
ms:contentKeyID: 48547070
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9d89547e56ddf6aa499a096b5991fc22cbf282e4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465921"
---
# <a name="activecommand-property-example-jscript"></a><span data-ttu-id="50281-102">ActiveCommand 属性示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="50281-102">ActiveCommand Property Example (JScript)</span></span>


<span data-ttu-id="50281-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="50281-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="50281-p101">此示例演示 [ActiveCommand](activecommand-property-ado.md) 属性。请将以下代码剪切并粘贴到"记事本"或其他文本编辑器中，并将其另存为 **ActiveCommandJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="50281-p101">This example demonstrates the [ActiveCommand](activecommand-property-ado.md) property. Cut and paste the following code to Notepad or another text editor, and save it as **ActiveCommandJS.asp**.</span></span>

```javascript
<!-- BeginActiveCommandJS --> 
<%@LANGUAGE="JScript" %> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<% 
 // user input 
 strName = new String(Request.Form("ContactName")) 
%> 
 
<html> 
 
<head> 
<title>ActiveCommand Property Example (JScript)</title> 
<style> 
<!-- 
BODY { 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 BACKGROUND-COLOR:white; 
 COLOR:black; 
 } 
--> 
</style> 
</head> 
 
<body bgcolor="White"> 
 
<h1>ActiveCommand Property Example (JScript)</h1> 
 
<% 
if (strName.length > 0) 
 { 
 // connection and recordset variables 
 var Cnxn = Server.CreateObject("ADODB.Connection") 
 var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='Northwind';Integrated Security='SSPI';"; 
 var cmdContact = Server.CreateObject("ADODB.Command"); 
 var rsContact = Server.CreateObject("ADODB.Recordset"); 
 // display variables 
 var strMessage; 
 
 try 
 { 
 // open connection 
 Cnxn.Open(strCnxn); 
 
 // Open a recordset using a command object 
 cmdContact.CommandText = "SELECT ContactName FROM Customers WHERE City = ?"; 
 cmdContact.ActiveConnection = Cnxn; 
 // create parameter and insert variable value 
 cmdContact.Parameters.Append(cmdContact.CreateParameter("ContactName", adChar, adParamInput, 30, strName)); 
 
 rsContact = cmdContact.Execute(); 
 
 while(!rsContact.EOF){ 
 // start new line 
 strMessage = "<P>"; 
 
 // get data 
 strMessage += rsContact("ContactName") 
 
 // end the line 
 strMessage += "</P>"; 
 
 // show data 
 Response.Write(strMessage); 
 
 // get next record 
 rsContact.MoveNext; 
 } 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // 'clean up 
 if (rsContact.State == adStateOpen) 
 rsContact.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsContact = null; 
 Cnxn = null; 
 } 
 } 
%> 
 
<hr> 
 
 
<form method="POST" action="ActiveCommandJS.asp"> 
 <p align="left">Enter city of customer to find (e.g., Paris): <input type="text" name="ContactName" size="40" value=""></p> 
 <p align="left"><input type="submit" value="Submit" name="B1"><input type="reset" value="Reset" name="B2"></p> 
</form> 
</body> 
 
</html> 
<!-- EndActiveCommandJS --> 
 
```
