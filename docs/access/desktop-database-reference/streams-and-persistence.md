---
title: 流和持久化
TOCTitle: Streams and Persistence
ms:assetid: 564fc098-52bf-77d7-9d48-75186483e3fe
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249289(v=office.15)
ms:contentKeyID: 48544949
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5a6f49368def305964119edcb06b5bcc80c278d2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709304"
---
# <a name="streams-and-persistence"></a>流和暂留


**适用于**： Access 2013、 Office 2013

[Recordset](recordset-object-ado.md) 对象的 [Save](save-method-ado.md) 方法用于将 **Recordset** 存储或*持久化*在文件中，[Open](open-method-ado-recordset.md) 方法用于从该文件中还原 **Recordset**。

通过 ADO 2.5， **Save** 和 **Open** 方法还可以将 **Recordset** 持久化到 [Stream](stream-object-ado.md) 对象。在使用远程数据服务 (RDS) 和 Active Server Pages (ASP) 时此功能尤为有用。

有关持久化如何在 ASP 页上自己使用的详细信息，请参阅当前的 ASP 文档。

以下几个方案显示了如何使用 **Stream** 对象和持久化。

## <a name="scenario-1"></a>方案 1

此方案只是将 **Recordset** 保存到文件，然后保存到 **Stream** 。随后，在另一个 **Recordset** 中打开持久化的流。

```vb 
 
Dim rs1 As ADODB.Recordset 
Dim rs2 As ADODB.Recordset 
Dim stm As ADODB.Stream 
 
Set rs1 = New ADODB.Recordset 
Set rs2 = New ADODB.Recordset 
Set stm = New ADODB.Stream 
 
rs1.Open "SELECT * FROM Customers", "Provider=sqloledb;" & _ 
 "Data Source=MyServer;Initial Catalog=Northwind;" & _ 
 "Integrated Security=SSPI;""", adopenStatic, adLockReadOnly, adCmdText 
rs1.Save "c:\myfolder\mysubfolder\myrs.xml", adPersistXML 
rs1.Save stm, adPersistXML 
rs2.Open stm 
```

## <a name="scenario-2"></a>方案 2

此方案将 **Recordset** 以 XML 格式持久化在 **Stream** 中。随后，将 **Stream** 读入一个您可以进行检查、操作或显示的字符串。

```vb 
 
Dim rs As ADODB.Recordset 
Dim stm As ADODB.Stream 
Dim strRst As String 
 
Set rs = New ADODB.Recordset 
Set stm = New ADODB.Stream 
 
' Open, save, and close the recordset. 
rs.Open "SELECT * FROM Customers", "Provider=sqloledb;" & _ 
 "Data Source=MyServer;Initial Catalog=Northwind;" & _ 
 "Integrated Security=SSPI;""" 
rs.Save stm, adPersistXML 
rs.Close 
Set rs = nothing 
 
' Put saved Recordset into a string variable. 
strRst = stm.ReadText(adReadAll) 
 
' Examine, manipulate, or display the XML data. 
... 
```

## <a name="scenario-3"></a>方案 3

以下示例代码显示了将 **Recordset** 作为 XML 直接持久化到 **Response** 对象的 ASP 代码：

```vb 
 
... 
<% 
response.ContentType = "text/xml" 
 
' Create and open a Recordset. 
Set rs = Server.CreateObject("ADODB.Recordset") 
rs.Open "select * from Customers", "Provider=sqloledb;" & _ 
 "Data Source=MyServer;Initial Catalog=Northwind;" & _ 
 "Integrated Security=SSPI;""" 
 
' Save Recordset directly into output stream. 
rs.Save Response, adPersistXML 
 
' Close Recordset. 
rs.Close 
Set rs = nothing 
%> 
... 
```

## <a name="scenario-4"></a>方案 4

在此方案中，ASP 代码将 ADTG 格式的 **Recordset** 的内容写入客户端。 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 可以使用此数据创建断开的 **Recordset** 。

RDS [DataControl](datacontrol-object-rds.md)、[URL](url-property-rds.md) 上的新属性指向生成 **Recordset** 的 .asp 页。这表明即使没有使用服务器端 **DataFactory** 对象的 RDS 或编写业务对象的用户，也可以获得 [Recordset](datafactory-object-rdsserver.md) 对象。这大大简化了 RDS 编程模型。

以下是名为 https://server/directory/recordset.asp: 的服务器端代码：

```vb 
 
<% 
Dim rs 
Set rs = Server.CreateObject("ADODB.Recordset") 
rs.Open "select au_fname, au_lname, phone from Authors", ""& _ 
 "Provider=sqloledb;Data Source=MyServer;" & _ 
 "Initial Catalog=Pubs;Integrated Security=SSPI;" 
response.ContentType = "multipart/mixed" 
rs.Save response, adPersistADTG 
%> 
```

客户端代码：

```html 
 
<HTML> 
<HEAD> 
<TITLE>RDS Query Page</TITLE> 
</HEAD> 
<body> 
<CENTER> 
<H1>Remote Data Service 2.5</H1> 
<TABLE DATASRC="#DC1"> 
 <TR> 
 <TD><SPAN DATAFLD="au_fname"></SPAN></TD> 
 <TD><SPAN DATAFLD="au_lname"></SPAN></TD> 
 <TD><SPAN DATAFLD="phone"></SPAN></TD> 
 </TR> 
</TABLE> 

<BR> 
 
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" 
 ID=DC1 HEIGHT=1 WIDTH = 1> 
 <PARAM NAME="URL" VALUE="https://server/directory/recordset.asp"> 
</OBJECT> 
 
</SCRIPT> 
</BODY> 
</HTML> 
```

开发人员还可以选择在客户端上使用 **Recordset** 对象：

```vb
... 
function GetRs() 
 { 
 rs = CreateObject("ADODB.Recordset"); 
 rs.Open "https://server/directory/recordset.asp" 
 DC1.SourceRecordset = rs; 
 } 
... 
```

