---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VBScript)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious Methods Example (VBScript)
ms:assetid: e1780013-5e11-aa8a-1be5-4d6d4273e72a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250148(v=office.15)
ms:contentKeyID: 48548261
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 934be9801a1c73c737e32623a7fe9d2792dca9ed
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465925"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-example-vbscript"></a><span data-ttu-id="0a1f5-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法示例 (VBScript)</span><span class="sxs-lookup"><span data-stu-id="0a1f5-102">MoveFirst, MoveLast, MoveNext, and MovePrevious Methods Example (VBScript)</span></span>


<span data-ttu-id="0a1f5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0a1f5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0a1f5-104">本示例使用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)、[MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 和 [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法基于提供的命令移动 [Recordset](recordset-object-ado.md) 的记录指针。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-104">This example uses the [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveLast](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveNext](movefirst-movelast-movenext-and-moveprevious-methods-ado.md), and [MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) methods to move the record pointer of a [Recordset](recordset-object-ado.md) based on the supplied command.</span></span>

<span data-ttu-id="0a1f5-p101">请将以下代码剪切并粘贴到记事本或其他文本编辑器中，然后将其保存为 **MoveFirstVBS.asp** 。可以在任何浏览器中查看结果。</span><span class="sxs-lookup"><span data-stu-id="0a1f5-p101">Cut and paste the following code into Notepad or another text editor, and save it as **MoveFirstVBS.asp**. You can view the result in any browser.</span></span>

```vb 
 
<!-- BeginMoveFirstVBS --> 
<%@ Language=VBScript %> 
<%' use this meta tag instead of adovbs.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
<HTML> 
<HEAD> 
<TITLE>ADO MoveNext, MovePrevious, MoveLast, MoveFirst Methods</TITLE> 
 
<SCRIPT LANGUAGE="VBScript"> 
<!-- 
   Sub cmdDown_OnClick 
      'Set Values in Form Input Boxes and Submit Form 
      Document.form.MoveAction.Value = "MovePrev" 
      Document.Form.Submit 
   End Sub 
 
   Sub cmdUp_OnClick 
      Document.form.MoveAction.Value = "MoveNext" 
      Document.Form.Submit 
   End Sub 
 
   Sub cmdFirst_OnClick 
      Document.form.MoveAction.Value = "MoveFirst" 
      Document.Form.Submit 
   End Sub 
 
   Sub cmdLast_OnClick 
      Document.form.MoveAction.Value = "MoveLast" 
      Document.Form.Submit 
   End Sub 
//--> 
</SCRIPT> 
</HEAD> 
 
<body bgcolor="white">  
<h1 align="center">ADO MoveNext, MovePrevious <br> MoveLast & MoveFirst Methods</h1> 
<% ' to integrate/test this code replace the  
   ' Data Source value in the Connection string%> 
<%  
   ' connection and recordset variables 
   Dim Cnxn, strCnxn 
   Dim rsEmployees, strSQLEmployees 
 
   ' open connection 
    Set Cnxn = Server.CreateObject("ADODB.Connection") 
    strCnxn = "Provider='sqloledb';Data Source=" & _ 
            Request.ServerVariables("SERVER_NAME") & ";" & _ 
            "Integrated Security='SSPI';Initial Catalog='Northwind';" 
    Cnxn.Open strCnxn 
       
    ' create and open Recordset using object refs 
   Set rsEmployees = Server.CreateObject("ADODB.Recordset") 
   strSQLEmployees = "Employees" 
    
   rsEmployees.ActiveConnection = Cnxn 
   rsEmployees.CursorLocation = adUseClient 
   rsEmployees.CursorType = adOpenKeyset 
   rsEmployees.LockType = adLockOptimistic 
   rsEmployees.Source = strSQLEmployees 
   rsEmployees.Open 
 
   rsEmployees.MoveFirst 
 
   If Not IsEmpty(Request.Form("MoveAction")) Then 
      strAction = Request.Form("MoveAction") 
      varPosition  = Request.Form("Position") 
       
      rsEmployees.AbsolutePosition = varPosition 
       
      Select Case strAction 
       
        Case "MoveNext" 
         
         rsEmployees.MoveNext 
         If rsEmployees.EOF Then 
            rsEmployees.MoveLast 
            strMessage = "Can't move beyond the last record." 
         End If 
         
        Case "MovePrev" 
         
         rsEmployees.MovePrevious 
         If rsEmployees.BOF Then 
            rsEmployees.MoveFirst 
            strMessage = "Can't move beyond the first record." 
         End If 
 
        Case "MoveLast" 
       
         rsEmployees.MoveLast 
       
        Case "MoveFirst" 
       
         rsEmployees.MoveFirst 
       
      End Select 
   End If 
       
%> 
 
<!-- Display Current Record Number and Recordset Size --> 
<h2>Record Number <%=rsEmployees.AbsolutePosition%> of <%=rsEmployees.RecordCount%></H2> 
<hr> 
<table cellpadding=5 border=0> 
<!-- BEGIN column header row for Customer Table--> 
<tr> 
   <th>Name</th> 
   <th>Hire Date</th> 
</tr> 
 
<!--Display ADO Data from Customer Table--> 
<tr> 
  <td><%= rsEmployees("LastName") & ", " %>  
      <%= rsEmployees("FirstName") & " " %></td> 
  <td><%= rsEmployees("HireDate")%></td> 
</tr>  
<tr> 
  <td colspan=2><%=strMessage%></td> 
</tr> 
</table> 
 
<hr> 
 
<form Name="Form" Method="Post" Action="MoveFirstVbs.asp"> 
<Input Type=Button Name=cmdDown Value="<"> 
<Input Type=Button Name=cmdUp Value=">"> 
<BR> 
<H3>Click Direction Arrows to Use MovePrevious or MoveNext</H3> 
<Input Type=Button Name=cmdFirst Value="First Record"> 
<Input Type=Button Name=cmdLast Value="Last Record"> 
 
 
<!-- Use Hidden Form Fields to record values to send to Server --> 
 
<input Type="Hidden" Size="4" Name="MoveAction" Value="Move"> 
<input Type="Hidden" Size="4" Name="Position" Value="<%= rsEmployees.AbsolutePosition%>"> 
</form> 
 
<HR> 
</BODY> 
 
<% 
    ' clean up 
    If rsEmployees.State = adStateOpen then 
        rsEmployees.Close 
    End If 
    If Cnxn.State = adStateOpen then 
        Cnxn.Close 
    End If 
%> 
</HTML> 
<!-- EndMoveFirstVBS --> 
 
```
