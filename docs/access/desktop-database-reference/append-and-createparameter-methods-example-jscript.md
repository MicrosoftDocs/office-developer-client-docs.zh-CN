---
title: Append 和 CreateParameter 方法示例 (JScript)
TOCTitle: Append and CreateParameter methods example (JScript)
ms:assetid: 77de4191-12f1-cd6b-1805-02546fe0a942
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249494(v=office.15)
ms:contentKeyID: 48545737
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 844cb85e4e760f9d6c92fdc4d6ec8996fcc167ac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297142"
---
# <a name="append-and-createparameter-methods-example-jscript"></a>Append 和 CreateParameter 方法示例 (JScript)


**适用于**：Access 2013、Office 2013

以下示例使用 [Append](append-method-ado.md) 和 [CreateParameter](createparameter-method-ado.md) 方法执行带输入参数的存储过程。将以下代码剪切并粘贴到记事本或其他文本编辑器，并另存为 **AppendJS.asp** 。

```javascript 
 
<!-- BeginAppendJS --> 
<%@LANGUAGE="JScript" %> 
<%// use this meta tag instead of adojavas.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
 
<html> 
<head> 
 <title>Append and CreateParameter methods example (JScript)</title> 
<style> 
<!-- 
body { 
 font-family: 'Verdana','Arial','Helvetica',sans-serif; 
 BACKGROUND-COLOR:white; 
 COLOR:black; 
 } 
--> 
</style> 
</head> 
 
<body> 
<h1>Append and CreateParameter methods example (JScript)</h1> 
<% 
 // verify user-input 
 var iRoyalty = parseInt(Request.Form("RoyaltyValue")); 
 if (iRoyalty > -1) 
 { 
 
 // connection, recordset and command variables 
 var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" + 
 "Initial Catalog='pubs';Integrated Security='SSPI';"; 
 var Cnxn = Server.CreateObject("ADODB.Connection"); 
 var cmdByRoyalty = Server.CreateObject("ADODB.Command"); 
 var rsByRoyalty = Server.CreateObject("ADODB.Recordset"); 
 var rsAuthor = Server.CreateObject("ADODB.Recordset"); 
 // display variables 
 var strMessage; 
 
 try 
 { 
 // open connection and set cursor location 
 Cnxn.Open(strCnxn); 
 Cnxn.CursorLocation = adUseClient; 
 
 // command object initial parameters 
 cmdByRoyalty.CommandText = "byroyalty"; 
 cmdByRoyalty.CommandType = adCmdStoredProc; 
 
 // create the new parameter and append to 
 // the Command object's parameters collection 
 var prmByRoyalty = cmdByRoyalty.CreateParameter("percentage", adInteger, adParamInput); 
 cmdByRoyalty.Parameters.Append(prmByRoyalty); 
 prmByRoyalty.Value = iRoyalty; 
 
 cmdByRoyalty.ActiveConnection = Cnxn; 
 
 // execute command 
 rsByRoyalty = cmdByRoyalty.Execute(); 
 
 // display results 
 rsAuthor.Open("Authors", Cnxn); 
 
 
 while (!rsByRoyalty.EOF) 
 { 
 rsAuthor.Filter = "au_id='" + rsByRoyalty.Fields("au_id") + "'"; 
 
 // start new line 
 strMessage = "<P>"; 
 
 // recordset data 
 strMessage += rsAuthor.Fields("au_fname") + " "; 
 strMessage += rsAuthor.Fields("au_lname") + " "; 
 
 // end the line 
 strMessage += "</P>"; 
 
 // show result 
 Response.Write(strMessage); 
 
 // et next record 
 rsByRoyalty.MoveNext; 
 } 
 } 
 catch (e) 
 { 
 Response.Write(e.message); 
 } 
 finally 
 { 
 // clean up 
 if (rsByRoyalty.State == adStateOpen) 
 rsByRoyalty.Close; 
 if (rsAuthor.State == adStateOpen) 
 rsAuthor.Close; 
 if (Cnxn.State == adStateOpen) 
 Cnxn.Close; 
 rsByRoyalty = null; 
 rsAuthor = null; 
 Cnxn = null; 
 } 
 } 
%> 
 
<hr> 
 
 
<form method="POST" action="AppendJS.asp" id=form1 name=form1> 
 <p align="left">Enter royalty percentage to find (e.g., 40): <input type="text" name="RoyaltyValue" size="5"></p> 
 <p align="left"><input type="submit" value="Submit" name="B1"><input type="reset" value="Reset" name="B2"></p> 
</form> 
&nbsp; 
 
 
</body> 
 
</html> 
<!-- EndAppendJS --> 
 
```

