---
title: 保留数据 （访问桌面数据库参考 （英文）
TOCTitle: Persisting data
ms:assetid: cb8a32f7-2cdc-26ed-c6d4-dd93c1ac37ba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250010(v=office.15)
ms:contentKeyID: 48547715
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9d72ba6d895fc5aac2612eb3f81ecc95ac032d49
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946746"
---
# <a name="persisting-data"></a>保留数据


**适用于**： Access 2013、 Office 2013

便携计算（例如，使用便携式计算机）需要在连接和断开状态下均可运行的应用程序。通过让开发人员能够将客户端游标 **Recordset** 保存到磁盘并随后重新加载它，ADO 已添加了对此功能的支持。

在几种情形下可以使用此类型的功能，包括：

- **旅行：** 在路途中取得应用程序时，重要的是能够进行更改并添加新记录，然后可以随后重新连接到数据库，并提交它们。

- **很少更新的查找：** 在应用程序中，通常将表作为查找源，例如，州的税率表。它们很少更新，并且是只读的。应用程序每次启动时，并不需要从服务器重新读取此数据，而是可以直接从本地持久化的 **Recordset** 中加载数据。

在 ADO 中，若要保存并加载 **Recordset** ，请使用 ADO **Recordset** 对象的 **Recordset.Save** 和 **Recordset.Open(,,,,adCmdFile)** 方法。

可以使用 **Recordset** **Save** 方法将 ADO **Recordset** 持久化到磁盘文件中（还可以将 **Recordset** 保存到 ADO **Stream** 对象中。本指南随后会讨论 **Stream** 对象）。随后，在准备使用 **Recordset** 时，可以使用 **Open** 方法将它重新打开。默认情况下，ADO 将 **Recordset** 保存为私有的 Microsoft Advanced Data TableGram (ADTG) 格式。可以使用 **adPersistADTG** **PersistFormatEnum** 值来指定此二进制格式。或者，也可以选择使用 **adPersistXML** 将 **Recordset** 保存为 XML。有关将记录集保存为 XML 的详细信息，请参阅 [用 XML 格式持久化记录](persisting-records-in-xml-format.md)。

**Save** 方法的语法如下所示：

`recordset.Save Destination, PersistFormat`

第一次保存 **Recordset** 时，可以选择指定 *Destination*。如果省略 *Destination*，系统将创建新文件，文件名为 **Recordset** 的 [Source](source-property-ado-recordset.md) 属性的值。

第一次保存后随后再调用 **Save** 时，请省略 *Destination*，否则将发生运行时错误。如果随后用新的 *Destination* 来调用 **Save**，**Recordset** 将保存到新的目标。但是，新的目标和原始目标都将打开。

**Save** 不会关闭 **Recordset** 或 *Destination*，所以可以继续处理 **Recordset** 并保存最新更改。*Destination* 将保持打开状态，直到 **Recordset** 关闭，在关闭期间，其他应用程序可以读取但不能写入 *Destination*。

由于安全原因， **Save** 方法只允许在 Microsoft Internet Explorer 执行的脚本中使用低安全设置和自定义安全设置。有关安全问题的详细说明，请参阅 Microsoft 数据访问技术文章中 ActiveX 数据对象 (ADO) 技术文章中的"Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题"。

如果在进行异步 **Recordset** 提取、执行或更新操作时调用 **Save** 方法，则会等到异步操作完成后再执行 **Save** 。

记录的保存是从 **Recordset** 的第一行开始的。 **Save** 方法完成之后，当前行位置被移到 **Recordset** 的第一行。

为了获得最佳效果，请在使用 [Save](cursorlocation-property-ado.md) 时将 **CursorLocation** 属性设置为 **adUseClient** 。如果提供程序不支持保存 **Recordset** 对象所需要的所有功能，则游标服务将提供该功能。

在将 **CursorLocation** 属性设置为 **adUseServer** 的情况下持久化 **Recordset** 时， **Recordset** 的更新功能是有限的。通常，只允许进行单表更新、插入和删除（取决于提供程序功能）。在此配置中， [Resync](resync-method-ado.md) 方法也不可用。

由于*Destination*参数可以接受支持 OLE DB **IStream**接口的任何对象，可以将**Recordset**保存到 ASP**响应**对象直接。

在以下示例中，使用 **Save** 和 **Open** 方法来持久化 **Recordset** ，并随后重新将它打开：

```vb 
 
'BeginPersist 
 conn.ConnectionString = _ 
 "Provider='SQLOLEDB';Data Source='MySqlServer';" _ 
 & "Integrated Security='SSPI';Initial Catalog='pubs'" 
 conn.Open 
 
 conn.Execute "create table testtable (dbkey int " & _ 
 "primary key, field1 char(10))" 
 conn.Execute "insert into testtable values (1, 'string1')" 
 
 Set rst.ActiveConnection = conn 
 rst.CursorLocation = adUseClient 
 
 rst.Open "select * from testtable", conn, adOpenStatic, _ 
 adLockBatchOptimistic 
 
 'Change the row on the client 
 rst!field1 = "NewValue" 
 
 'Save to a file--the .dat extension is an example; choose 
 'your own extension. The changes will be saved in the file 
 'as well as the original data. 
 MyFile = Dir("c:\temp\temptbl.dat") 
 If MyFile <> "" Then 
 Kill "c:\temp\temptbl.dat" 
 End If 
 
 rst.Save "c:\temp\temptbl.dat", adPersistADTG 
 rst.Close 
 Set rst = Nothing 
 
 'Now reload the data from the file 
 Set rst = New ADODB.Recordset 
 rst.Open "c:\temp\temptbl.dat", , adOpenStatic, _ 
 adLockBatchOptimistic, adCmdFile 
 
 Debug.Print "After Loading the file from disk" 
 Debug.Print " Current Edited Value: " & rst!field1.Value 
 Debug.Print " Value Before Editing: " & rst!field1.OriginalValue 
 
 'Note that you can reconnect to a connection and 
 'submit the changes to the data source 
 Set rst.ActiveConnection = conn 
 rst.UpdateBatch 
'EndPersist 
```

本节包括下列主题：

- [有关记录集暂留的详细信息](more-about-recordset-persistence.md)

- [暂留筛选和分层记录集](persisting-filtered-and-hierarchical-recordsets.md)

- [Persisting Records in XML Format (ADO)](persisting-records-in-xml-format.md)