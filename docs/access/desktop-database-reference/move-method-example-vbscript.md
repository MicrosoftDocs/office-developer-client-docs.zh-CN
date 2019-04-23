---
title: Move 方法示例 (VBScript)
TOCTitle: Move method example (VBScript)
ms:assetid: 42f2eb08-47cf-f422-6176-badd414d0bfc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249198(v=office.15)
ms:contentKeyID: 48544489
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4ea9e65098637986de91b6eaf5d770f2a8cab5ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288839"
---
# <a name="move-method-example-vbscript"></a>Move 方法示例 (VBScript)


**适用于**：Access 2013、Office 2013

本示例使用 [Move](move-method-ado.md) 方法基于用户输入来定位记录指针。

在 Active Server Page (ASP) 中使用下面的示例。

使用 **Find** 来查找文件 Adovbs.inc 并将其放置在要使用的目录中。请将以下代码剪切并粘贴到记事本或其他文本编辑器中，然后将其保存为 **MoveVBS.asp** 。可以在任何浏览器中查看结果。

尝试输入一个字母或非整数值以查看错误处理方式。

```vb 
 
<!-- BeginMoveVBS --> 
<%@ Language=VBScript %> 
<%' use this meta tag instead of adovbs.inc%> 
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" --> 
<HTML> 
<HEAD> 
<TITLE>ADO Move Methods</TITLE> 
<STYLE> 
<!-- 
BODY { 
   font-family: "MS SANS SERIF",sans-serif; 
    } 
.thead1 { 
   background-color: #008080;  
   font-family: 'Arial Narrow','Arial',sans-serif;  
   font-size: x-small; 
   color: white; 
   } 
.tbody {  
   text-align: center; 
   background-color: #f7efde; 
   font-family: 'Arial Narrow','Arial',sans-serif;  
   font-size: x-small; 
    } 
--> 
</STYLE> 
</HEAD> 
<BODY>  
<H3>ADO Move Methods</H3> 
<% ' to integrate/test this code replace the  
   ' Data Source value in the Connection string%> 
<%  
    ' connection and recordset variables 
    Dim Cnxn, strCnxn 
    Dim rsCustomers, strSQLCustomers 
 
    ' open connection 
    Set Cnxn = Server.CreateObject("ADODB.Connection") 
    strCnxn = "Provider='sqloledb';Data Source=" & _ 
            Request.ServerVariables("SERVER_NAME") & ";" & _ 
            "Integrated Security='SSPI';Initial Catalog='Northwind';" 
 
    Cnxn.Open strCnxn 
         
     ' create and open Recordset using object refs 
    Set rsCustomers = Server.CreateObject("ADODB.Recordset") 
    strSQLCustomers = "Customers" 
     
    rsCustomers.ActiveConnection = Cnxn 
    rsCustomers.CursorLocation = adUseClient 
    rsCustomers.CursorType = adOpenKeyset 
    rsCustomers.LockType = adLockOptimistic 
    rsCustomers.Source = strSQLCustomers 
    rsCustomers.Open 
 
    'Check number of user moves this session and increment by entry 
    Session("Clicks") = Session("Clicks") + Request.Form("MoveAmount") 
    Clicks = Session("Clicks") 
    ' Move to last known recordset position plus amount passed  
    rsCustomers.Move CInt(Clicks) 
 
    'Error Handling 
    If rsCustomers.EOF Then 
        Session("Clicks") = rsCustomers.RecordCount 
        Response.Write "This is the Last Record" 
        rsCustomers.MoveLast 
    ElseIf rsCustomers.BOF Then 
        Session("Clicks") = 1 
        rsCustomers.MoveFirst 
        Response.Write "This is the First Record" 
    End If 
    %> 
 
    <H3>Current Record Number is <BR> 
    <%  
    If Session("Clicks") = 0 Then Session("Clicks") = 1 
    Response.Write(Session("Clicks") )%> of <%=rsCustomers.RecordCount%></H3> 
    <HR> 
 
 
    <TABLE COLSPAN=8 CELLPADDING=5 BORDER=0> 
 
    <!-- BEGIN column header row for Customer Table--> 
 
    <TR CLASS=thead1> 
       <TD>Company Name</TD> 
       <TD>Contact Name</TD> 
       <TD>City</TD> 
    </TR> 
        <% 'display%> 
        <TR CLASS=tbody> 
          <TD> <%= rsCustomers("CompanyName")%> </TD> 
          <TD> <%= rsCustomers("ContactName")%></TD> 
          <TD> <%= rsCustomers("City")%> </TD> 
        </TR>  
    </TABLE> 
 
    <HR> 
    <Input Type=Button Name=cmdDown  Value="&lt;  "> 
    <Input Type=Button Name=cmdUp Value=" &gt;"> 
    <H5>Click Direction Arrows for Previous or Next Record 
    <BR> <BR> 
 
    <FORM Method = Post Action="MoveVbs.asp" Name=Form> 
    <TABLE> 
        <TR> 
           <TD><Input Type="Button" Name=Move Value="Move Amount "></TD> 
           <TD></TD> 
           <TD><Input Type="Text" Size="4" Name="MoveAmount" Value=0></TD> 
        <TR> 
    </TABLE> 

    Click Move Amount to use Move Method<br> 
    Enter Number of Records to Move + or - </H5>    </FORM> 
</BODY> 
 
<Script Language = "VBScript"> 
 
Sub Move_OnClick 
   ' Make sure move value entered is an integer 
   If IsNumeric(Document.Form.MoveAmount.Value)Then 
      Document.Form.MoveAmount.Value = CInt(Document.Form.MoveAmount.Value) 
      Document.Form.Submit 
   Else 
      MsgBox "You Must Enter a Number", ,"ADO-ASP Example" 
      Document.Form.MoveAmount.Value = 0 
   End If 
End Sub 
 
Sub cmdDown_OnClick 
   Document.Form.MoveAmount.Value = -1 
   Document.Form.Submit 
End Sub 
 
Sub cmdUp_OnClick 
   Document.Form.MoveAmount.Value = 1 
   Document.Form.Submit 
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
<!-- EndMoveVBS --> 
```

