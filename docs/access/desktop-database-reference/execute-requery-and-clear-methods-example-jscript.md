---
title: Execute、Requery 和 Clear 方法示例 (JScript)
TOCTitle: Execute, Requery, and Clear methods example (JScript)
ms:assetid: 3c1f1913-f168-b8a9-8791-f4a0b1aa8273
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249157(v=office.15)
ms:contentKeyID: 48544306
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1eec2b3da623f983f8e16e41c32b0a219ddd7931
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862149"
---
# <a name="execute-requery-and-clear-methods-example-jscript"></a><span data-ttu-id="9c396-102">Execute、Requery 和 Clear 方法示例 (JScript)</span><span class="sxs-lookup"><span data-stu-id="9c396-102">Execute, Requery, and Clear methods example (JScript)</span></span>


<span data-ttu-id="9c396-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9c396-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9c396-p101">本示例演示同时从 **Command** 对象和 [Connection](command-object-ado.md) 对象运行时的 [Execute](connection-object-ado.md) 方法。本示例还使用 [Requery](requery-method-ado.md) 方法来检索 [Recordset](recordset-object-ado.md) 中的当前数据，并使用 [Clear](clear-method-ado.md) 方法来清除 [Errors](errors-collection-ado.md) 集合的内容。（可以通过 **Recordset** 的 **ActiveConnection** 属性的 [Connection](activeconnection-property-ado.md) 对象访问 [Errors](recordset-object-ado.md) 集合。）将文件命名为 **ExecuteJS.asp** 。</span><span class="sxs-lookup"><span data-stu-id="9c396-p101">This example demonstrates the **Execute** method when run from both a [Command](command-object-ado.md) object and a [Connection](connection-object-ado.md) object. It also uses the [Requery](requery-method-ado.md) method to retrieve current data in a [Recordset](recordset-object-ado.md), and the [Clear](clear-method-ado.md) method to clear the contents of the [Errors](errors-collection-ado.md) collection. (The **Errors** collection is accessed via the **Connection** object of the [ActiveConnection](activeconnection-property-ado.md) property of the [Recordset](recordset-object-ado.md).) Name the file **ExecuteJS.asp**.</span></span>

```javascript 
 
<!-- BeginExecuteJS --> 
<%@LANGUAGE="JScript"%> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<% 
 strLastName = new String(Request.Form("AuthorLName")); 
 
 if (strLastName.indexOf("undefined") > -1) 
 strLastName = ""; 
%> 
 
<html> 
 
<head> 
<title>Execute, Requery and Clear methods example (JScript)</title> 
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
<h1>Execute, Requery and Clear methods example (JScript)</h1> 
<% 
 if (strLastName.length > 0) 
 { 
 // command and recordset variables 
 var Connect = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='pubs';Integrated Security='SSPI';"; 
 var Cnxn = Server.CreateObject("ADODB.Connection"); 
 var cmdAuthor = Server.CreateObject("ADODB.Command"); 
 var rsAuthor = Server.CreateObject("ADODB.Recordset"); 
 var rsAuthor2 = Server.CreateObject("ADODB.Recordset"); 
 var SQLAuthor2, strMessage, strMessage2; 
 var Err, ErrCount; 
 
 try 
 { 
 // open connection 
 Cnxn.Open(Connect); 
 
 // command object parameters 
 cmdAuthor.CommandText = "SELECT * FROM Authors WHERE au_lname = ?"; 
 cmdAuthor.Parameters.Append(cmdAuthor.CreateParameter("Last Name", adChar, adParamInput, 20, strLastName)); 
 cmdAuthor.ActiveConnection = Cnxn; 
 
 // recordset from command.execute 
 rsAuthor = cmdAuthor.Execute(); 
 
 // recordset from connection.execute 
 SQLAuthor2 = "SELECT * FROM Authors"; 
 rsAuthor2 = Cnxn.Execute(SQLAuthor2); 
 
 // check for errors 
 ErrCount = Cnxn.errors.count; 
 if(ErrCount !== 0) //write the errors 
 { 
 for(Err = 0; Err = ErrCount; Err++){ 
 Err = Cnxn.errors.item; 
 Response.Write(Err); 
 } 
 // clean out any existing errors 
 Cnxn.Errors.Clear; 
 } 
 
 // show the data 
 Response.Write("<HR><HR>"); 
 
 // first recordset 
 Response.Write("<b>Command.Execute results</b>") 
 while (!rsAuthor.EOF) 
 { 
 // build output string by starting a new line 
 strMessage = "<P>"; 
 strMessage += "<br>"; 
 
 // recordset data 
 strMessage += rsAuthor("au_fname") + " "; 
 strMessage += rsAuthor("au_lname") + " "; 
 
 // end the line 
 strMessage += "</P>"; 
 
 // show the results 
 Response.Write(strMessage); 
 
 // get next record 
 rsAuthor.MoveNext; 
 } 
 
 Response.Write("<HR><HR>"); 
 
 // second recordset 
 Response.Write("<b>Connection.Execute results</b>") 
 while (!rsAuthor2.EOF) 
 { 
 // start a new line 
 strMessage2 = "<P>"; 
 
 // first and last name are in first column 
 strMessage2 += rsAuthor2("au_fname") + " " 
 strMessage2 += rsAuthor2("au_lname") + " "; 
 
 // end the line 
 strMessage2 += "</P>"; 
 
 // show results 
 Response.Write(strMessage2); 
 
 // get next record 
 rsAuthor2.MoveNext; 
 } 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // clean up 
 if (rsAuthor.State == adStateOpen) 
 rsAuthor.Close; 
 if (rsAuthor2.State == adStateOpen) 
 rsAuthor2.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsAuthor1 = null; 
 rsAuthor2 = null; 
 Cnxn = null; 
 } 
 } 
%> 
 
<hr> 
 
 
<form method="POST" action="ExecuteJS.asp" id=form1 name=form1> 
 <p align="left">Enter last name of author to find (e.g., Ringer): <input type="text" name="AuthorLName" size="40"></p> 
 <p align="left"><input type="submit" value="Submit" name="B1"><input type="reset" value="Reset" name="B2"></p> 
</form> 
</body> 
 
</html> 
<!-- EndExecuteJS --> 
 
```

