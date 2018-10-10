---
title: Execute、Requery 和 Clear 方法示例 (VBScript)
TOCTitle: Execute, Requery, and Clear Methods Example (VBScript)
ms:assetid: 3999d3d8-693b-99ee-421a-7c67ff0e3cbf
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249142(v=office.15)
ms:contentKeyID: 48544252
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e8518c7923c2334711891a9b3e02b2f010599357
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468480"
---
# <a name="execute-requery-and-clear-methods-example-vbscript"></a>Execute、Requery 和 Clear 方法示例 (VBScript)


**适用于**： Access 2013 |Office 2013

本示例演示同时从 **Command** 对象和 [Connection](command-object-ado.md) 对象运行时的 [Execute](connection-object-ado.md) 方法。本示例还使用 [Requery](requery-method-ado.md) 方法来检索 [Recordset](recordset-object-ado.md) 中的当前数据，并使用 [Clear](clear-method-ado.md) 方法来清除 [Errors](errors-collection-ado.md) 集合的内容。若要使该过程运行，需要 ExecuteCommand 和 PrintOutput 过程。

在 Active Server Page (ASP) 中使用下面的示例。使用 **Find** 来查找文件 Adovbs.inc 并将其放置在要使用的目录中。将以下代码剪切并粘贴到记事本或其他文本编辑器中，然后将其保存为 **ExecuteVBS.asp** 。可以在任何客户端浏览器中查看结果。

```vb 
 
<!-- BeginExecuteVBS --> 
<%@ Language=VBScript %> 
<% ' use this meta tag instead of ADOVBS.inc%> 
<!-- METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4"  --> 
<HTML> 
<HEAD> 
<META name="VI60_DefaultClientScript"  content=VBScript> 
<META NAME="GENERATOR" Content="Microsoft Visual Studio 6.0"> 
<title>ADO Execute Method</title> 
<STYLE> 
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
</STYLE> 
</HEAD> 
 
<BODY> 
<H3>ADO Execute Method</H3> 
<HR> 
<H4>Recordset Retrieved Using Connection Object</H4> 
<!--- Recordsets retrieved using Execute method of Connection and Command Objects--> 
<%  
     ' connection, command and recordset variables 
    Dim Cnxn, strCnxn 
    Dim rsCustomers, strSQLCustomers 
    Dim Cmd  
    Dim rsProducts, strSQLProducts 
 
    ' create and open connection 
    Set Cnxn = Server.CreateObject("ADODB.Connection")  
    strCnxn="Provider='sqloledb';Data Source=" & _ 
            Request.ServerVariables("SERVER_NAME") & ";" & _ 
            "Integrated Security='SSPI';Initial Catalog='Northwind';" 
    Cnxn.Open  strCnxn 
    ' create and open recordset 
    Set rsCustomers = Server.CreateObject("ADODB.Recordset") 
    strSQLCustomers = "Customers" 
    rsCustomers.Open strSQLCustomers, Cnxn, adOpenKeyset, adLockOptimistic, adCmdTable 
 
    '1st Recordset using Connection - Execute 
    Set rsCustomers = Cnxn.Execute(strSQLCustomers)  
 
    Set Cmd = Server.CreateObject("ADODB.Command") 
    Cmd.ActiveConnection = Cnxn 
    strSQLProducts = "SELECT * From Products" 
    Cmd.CommandText = strSQLProducts 
 
    '2nd Recordset Cmd - execute  
    Set rsProducts = Cmd.Execute 
    %> 
    <TABLE COLSPAN=8 CELLPADDING=5 BORDER=0 ALIGN=CENTER> 
    <!-- BEGIN column header row for Customer Table--> 
    <TR CLASS=thead> 
      <TH>Company Name</TH> 
      <TH>Contact Name</TH> 
      <TH>City</TH> 
    </TR> 
 
    <!--Display ADO Data from Customer Table--> 
    <%  
    Do While Not rsCustomers.EOF %> 
      <TR CLASS=tbody> 
        <TD>  
        <%= rsCustomers("CompanyName")%>  
        </TD> 
        <TD> 
        <%= rsCustomers("ContactName") %>  
        </TD> 
        <TD>  
        <%= rsCustomers("City")%>  
        </TD> 
      </TR>  
      <%  
    rsCustomers.MoveNext  
    Loop  
    %> 
</TABLE> 
 
<HR> 
<H4>Recordset Retrieved Using Command Object</H4> 
 
<TABLE CELLPADDING=5 BORDER=0 ALIGN=CENTER WIDTH="80%"> 
 
<!-- BEGIN column header row for Product List Table--> 
<TR CLASS=thead2> 
  <TH>Product Name</TH> 
  <TH>Unit Price</TH> 
</TR> 
 
<!-- Display ADO Data Product List--> 
<% Do Until rsProducts.EOF %> 
  <TR CLASS=tbody> 
    <TD> 
    <%= rsProducts("ProductName")%>   
    </TD> 
    <TD>  
    <%= rsProducts("UnitPrice")%>  
    </TD> 
<%  
    rsProducts.MoveNext  
    Loop 
  
    ' clean up 
    If rsCustomers.State = adStateOpen then 
        rsCustomers.Close 
    End If 
    If rsProducts.State = adStateOpen then 
        rsProducts.Close 
    End If 
    If Cnxn.State = adStateOpen then 
        Cnxn.Close 
    End If 
    Set Cmd = Nothing 
    Set rsCustomers = Nothing 
    Set rsProducts = Nothing 
    Set Cnxn = Nothing 
%> 
</TABLE> 
 
</BODY> 
</HTML> 
<!-- EndExecuteVBS --> 
```

