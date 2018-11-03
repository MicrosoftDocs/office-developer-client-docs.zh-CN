---
title: 流和持久化
TOCTitle: Streams and Persistence
ms:assetid: 564fc098-52bf-77d7-9d48-75186483e3fe
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249289(v=office.15)
ms:contentKeyID: 48544949
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a90031ac2f6d573631063edb0faf4893c2320d03
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944380"
---
# <a name="streams-and-persistence"></a><span data-ttu-id="14655-102">流和持久化</span><span class="sxs-lookup"><span data-stu-id="14655-102">Streams and persistence</span></span>


<span data-ttu-id="14655-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="14655-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="14655-104">[Recordset](recordset-object-ado.md) 对象的 [Save](save-method-ado.md) 方法用于将 **Recordset** 存储或*持久化*在文件中，[Open](open-method-ado-recordset.md) 方法用于从该文件中还原 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="14655-104">The [Recordset](recordset-object-ado.md) object [Save](save-method-ado.md) method stores, or *persists*, a **Recordset** in a file, and the [Open](open-method-ado-recordset.md) method restores the **Recordset** from that file.</span></span>

<span data-ttu-id="14655-p101">通过 ADO 2.5， **Save** 和 **Open** 方法还可以将 **Recordset** 持久化到 [Stream](stream-object-ado.md) 对象。在使用远程数据服务 (RDS) 和 Active Server Pages (ASP) 时此功能尤为有用。</span><span class="sxs-lookup"><span data-stu-id="14655-p101">With ADO 2.5, the **Save** and **Open** methods can persist a **Recordset** to a [Stream](stream-object-ado.md) object as well. This feature is especially useful when working with Remote Data Service (RDS) and Active Server Pages (ASP).</span></span>

<span data-ttu-id="14655-107">有关持久化如何在 ASP 页上自己使用的详细信息，请参阅当前的 ASP 文档。</span><span class="sxs-lookup"><span data-stu-id="14655-107">For more information about how persistence can be used by itself on ASP pages, see the current ASP documentation.</span></span>

<span data-ttu-id="14655-108">以下几个方案显示了如何使用 **Stream** 对象和持久化。</span><span class="sxs-lookup"><span data-stu-id="14655-108">The following are a few scenarios that show how **Stream** objects and persistence can be used.</span></span>

## <a name="scenario-1"></a><span data-ttu-id="14655-109">方案 1</span><span class="sxs-lookup"><span data-stu-id="14655-109">Scenario 1</span></span>

<span data-ttu-id="14655-p102">此方案只是将 **Recordset** 保存到文件，然后保存到 **Stream** 。随后，在另一个 **Recordset** 中打开持久化的流。</span><span class="sxs-lookup"><span data-stu-id="14655-p102">This scenario simply saves a **Recordset** to a file and then to a **Stream**. It then opens the persisted stream into another **Recordset**.</span></span>

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

## <a name="scenario-2"></a><span data-ttu-id="14655-112">方案 2</span><span class="sxs-lookup"><span data-stu-id="14655-112">Scenario 2</span></span>

<span data-ttu-id="14655-p103">此方案将 **Recordset** 以 XML 格式持久化在 **Stream** 中。随后，将 **Stream** 读入一个您可以进行检查、操作或显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="14655-p103">This scenario persists a **Recordset** into a **Stream** in XML format. It then reads the **Stream** into a string that you can examine, manipulate, or display.</span></span>

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

## <a name="scenario-3"></a><span data-ttu-id="14655-115">方案 3</span><span class="sxs-lookup"><span data-stu-id="14655-115">Scenario 3</span></span>

<span data-ttu-id="14655-116">以下示例代码显示了将 **Recordset** 作为 XML 直接持久化到 **Response** 对象的 ASP 代码：</span><span class="sxs-lookup"><span data-stu-id="14655-116">This example code shows ASP code persisting a **Recordset** as XML directly to the **Response** object:</span></span>

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

## <a name="scenario-4"></a><span data-ttu-id="14655-117">方案 4</span><span class="sxs-lookup"><span data-stu-id="14655-117">Scenario 4</span></span>

<span data-ttu-id="14655-p104">在此方案中，ASP 代码将 ADTG 格式的 **Recordset** 的内容写入客户端。 [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) 可以使用此数据创建断开的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="14655-p104">In this scenario, ASP code writes the contents of the **Recordset** in ADTG format to the client. The [Microsoft Cursor Service for OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md) can use this data to create a disconnected **Recordset**.</span></span>

<span data-ttu-id="14655-p105">RDS [DataControl](datacontrol-object-rds.md)、[URL](url-property-rds.md) 上的新属性指向生成 **Recordset** 的 .asp 页。这表明即使没有使用服务器端 **DataFactory** 对象的 RDS 或编写业务对象的用户，也可以获得 [Recordset](datafactory-object-rdsserver.md) 对象。这大大简化了 RDS 编程模型。</span><span class="sxs-lookup"><span data-stu-id="14655-p105">A new property on the RDS [DataControl](datacontrol-object-rds.md), [URL](url-property-rds.md), points to the .asp page that generates the **Recordset**. This means a **Recordset** object can be obtained without RDS using the server-side [DataFactory](datafactory-object-rdsserver.md) object or the user writing a business object. This simplifies the RDS programming model significantly.</span></span>

<span data-ttu-id="14655-123">以下是名为 https://server/directory/recordset.asp: 的服务器端代码：</span><span class="sxs-lookup"><span data-stu-id="14655-123">Server-side code, named https://server/directory/recordset.asp:</span></span>

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

<span data-ttu-id="14655-124">客户端代码：</span><span class="sxs-lookup"><span data-stu-id="14655-124">Client-side code:</span></span>

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

<span data-ttu-id="14655-125">开发人员还可以选择在客户端上使用 **Recordset** 对象：</span><span class="sxs-lookup"><span data-stu-id="14655-125">Developers also have the option of using a **Recordset** object on the client:</span></span>

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

