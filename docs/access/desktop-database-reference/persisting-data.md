---
title: 保留数据 （访问桌面数据库参考 （英文）
TOCTitle: Persisting data
ms:assetid: cb8a32f7-2cdc-26ed-c6d4-dd93c1ac37ba
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250010(v=office.15)
ms:contentKeyID: 48547715
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f5788216a20e62cfc39fd2081f4f672bc4f9b808
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713959"
---
# <a name="persisting-data"></a><span data-ttu-id="f59f4-102">暂留数据</span><span class="sxs-lookup"><span data-stu-id="f59f4-102">Persisting data</span></span>


<span data-ttu-id="f59f4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f59f4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f59f4-p101">便携计算（例如，使用便携式计算机）需要在连接和断开状态下均可运行的应用程序。通过让开发人员能够将客户端游标 **Recordset** 保存到磁盘并随后重新加载它，ADO 已添加了对此功能的支持。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p101">Portable computing (for example, using laptops) has generated the need for applications that can run in both a connected and disconnected state. ADO has added support for this by giving the developer the ability to save a client cursor **Recordset** to disk and reload it later.</span></span>

<span data-ttu-id="f59f4-106">在几种情形下可以使用此类型的功能，包括：</span><span class="sxs-lookup"><span data-stu-id="f59f4-106">There are several scenarios in which you could use this type of feature, including the following:</span></span>

- <span data-ttu-id="f59f4-107">**旅行：** 在路途中取得应用程序时，重要的是能够进行更改并添加新记录，然后可以随后重新连接到数据库，并提交它们。</span><span class="sxs-lookup"><span data-stu-id="f59f4-107">**Traveling:** When taking the application on the road, it is vital to supply the ability to make changes and add new records that can then be reconnected to the database later and committed.</span></span>

- <span data-ttu-id="f59f4-p102">**很少更新的查找：** 在应用程序中，通常将表作为查找源，例如，州的税率表。它们很少更新，并且是只读的。应用程序每次启动时，并不需要从服务器重新读取此数据，而是可以直接从本地持久化的 **Recordset** 中加载数据。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p102">**Infrequently updated lookups:** Often in an application, tables are used as lookups — for example, state tax tables. They are infrequently updated and are read-only. Instead of rereading this data from the server each time the application is started, the application can simply load the data from a locally persisted **Recordset**.</span></span>

<span data-ttu-id="f59f4-111">在 ADO 中，若要保存并加载 **Recordset** ，请使用 ADO **Recordset** 对象的 **Recordset.Save** 和 **Recordset.Open(,,,,adCmdFile)** 方法。</span><span class="sxs-lookup"><span data-stu-id="f59f4-111">In ADO, to save and load **Recordsets**, use the **Recordset.Save** and **Recordset.Open(,,,,adCmdFile)** methods on the ADO **Recordset** object.</span></span>

<span data-ttu-id="f59f4-p103">可以使用 **Recordset** **Save** 方法将 ADO **Recordset** 持久化到磁盘文件中（还可以将 **Recordset** 保存到 ADO **Stream** 对象中。本指南随后会讨论 **Stream** 对象）。随后，在准备使用 **Recordset** 时，可以使用 **Open** 方法将它重新打开。默认情况下，ADO 将 **Recordset** 保存为私有的 Microsoft Advanced Data TableGram (ADTG) 格式。可以使用 **adPersistADTG** **PersistFormatEnum** 值来指定此二进制格式。或者，也可以选择使用 **adPersistXML** 将 **Recordset** 保存为 XML。有关将记录集保存为 XML 的详细信息，请参阅 [用 XML 格式持久化记录](persisting-records-in-xml-format.md)。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p103">You can use the **Recordset** **Save** method to persist your ADO **Recordset** to a file on a disk. (You can also save a **Recordset** to an ADO **Stream** object. **Stream** objects are discussed later in the guide.) Later, you can use the **Open** method to reopen the **Recordset** when you are ready to use it. By default, ADO saves the **Recordset** into the proprietary Microsoft Advanced Data TableGram (ADTG) format. This binary format is specified using the **adPersistADTG** **PersistFormatEnum** value. Alternatively, you may choose to save your **Recordset** out as XML instead using **adPersistXML**. For more information about saving Recordsets as XML, see [Persisting Records in XML Format](persisting-records-in-xml-format.md).</span></span>

<span data-ttu-id="f59f4-119">**Save** 方法的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="f59f4-119">The syntax of the **Save** method is as follows:</span></span>

`recordset.Save Destination, PersistFormat`

<span data-ttu-id="f59f4-p104">第一次保存 **Recordset** 时，可以选择指定 *Destination*。如果省略 *Destination*，系统将创建新文件，文件名为 **Recordset** 的 [Source](source-property-ado-recordset.md) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p104">The first time you save the **Recordset**, it is optional to specify *Destination*. If you omit *Destination*, a new file will be created with a name set to the value of the [Source](source-property-ado-recordset.md) property of the **Recordset**.</span></span>

<span data-ttu-id="f59f4-p105">第一次保存后随后再调用 **Save** 时，请省略 *Destination*，否则将发生运行时错误。如果随后用新的 *Destination* 来调用 **Save**，**Recordset** 将保存到新的目标。但是，新的目标和原始目标都将打开。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p105">Omit *Destination* when you subsequently call **Save** after the first save or a run-time error will occur. If you subsequently call **Save** with a new *Destination*, the **Recordset** is saved to the new destination. However, the new destination and the original destination will both be open.</span></span>

<span data-ttu-id="f59f4-p106">**Save** 不会关闭 **Recordset** 或 *Destination*，所以可以继续处理 **Recordset** 并保存最新更改。*Destination* 将保持打开状态，直到 **Recordset** 关闭，在关闭期间，其他应用程序可以读取但不能写入 *Destination*。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p106">**Save** does not close the **Recordset** or *Destination*, so you can continue to work with the **Recordset** and save your most recent changes. *Destination* remains open until the **Recordset** is closed, during which time other applications can read but not write to *Destination*.</span></span>

<span data-ttu-id="f59f4-p107">由于安全原因， **Save** 方法只允许在 Microsoft Internet Explorer 执行的脚本中使用低安全设置和自定义安全设置。有关安全问题的详细说明，请参阅 Microsoft 数据访问技术文章中 ActiveX 数据对象 (ADO) 技术文章中的"Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题"。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p107">For reasons of security, the **Save** method permits only the use of low and custom security settings from a script executed by Microsoft Internet Explorer. For a more detailed explanation of security issues, see "ADO and RDS Security Issues in Microsoft Internet Explorer" under ActiveX Data Objects (ADO) Technical Articles in Microsoft Data Access Technical Articles.</span></span>

<span data-ttu-id="f59f4-129">如果在进行异步 **Recordset** 提取、执行或更新操作时调用 **Save** 方法，则会等到异步操作完成后再执行 **Save** 。</span><span class="sxs-lookup"><span data-stu-id="f59f4-129">If the **Save** method is called while an asynchronous **Recordset** fetch, execute, or update operation is in progress, **Save** waits until the asynchronous operation is complete.</span></span>

<span data-ttu-id="f59f4-p108">记录的保存是从 **Recordset** 的第一行开始的。 **Save** 方法完成之后，当前行位置被移到 **Recordset** 的第一行。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p108">Records are saved beginning with the first row of the **Recordset**. When the **Save** method is finished, the current row position is moved to the first row of the **Recordset**.</span></span>

<span data-ttu-id="f59f4-p109">为了获得最佳效果，请在使用 [Save](cursorlocation-property-ado.md) 时将 **CursorLocation** 属性设置为 **adUseClient** 。如果提供程序不支持保存 **Recordset** 对象所需要的所有功能，则游标服务将提供该功能。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p109">For best results, set the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient** with **Save**. If your provider does not support all of the functionality necessary to save **Recordset** objects, the Cursor Service will provide that functionality.</span></span>

<span data-ttu-id="f59f4-p110">在将 **CursorLocation** 属性设置为 **adUseServer** 的情况下持久化 **Recordset** 时， **Recordset** 的更新功能是有限的。通常，只允许进行单表更新、插入和删除（取决于提供程序功能）。在此配置中， [Resync](resync-method-ado.md) 方法也不可用。</span><span class="sxs-lookup"><span data-stu-id="f59f4-p110">When a **Recordset** is persisted with the **CursorLocation** property set to **adUseServer**, the update capability for the **Recordset** is limited. Typically, only single-table updates, insertions, and deletions are allowed (dependent on provider functionality). The [Resync](resync-method-ado.md) method is also unavailable in this configuration.</span></span>

<span data-ttu-id="f59f4-137">由于*Destination*参数可以接受支持 OLE DB **IStream**接口的任何对象，可以将**Recordset**保存到 ASP**响应**对象直接。</span><span class="sxs-lookup"><span data-stu-id="f59f4-137">Because the *Destination* parameter can accept any object that supports the OLE DB **IStream** interface, you can save a **Recordset** directly to the ASP **Response** object.</span></span>

<span data-ttu-id="f59f4-138">在以下示例中，使用 **Save** 和 **Open** 方法来持久化 **Recordset** ，并随后重新将它打开：</span><span class="sxs-lookup"><span data-stu-id="f59f4-138">In the following example, the **Save** and **Open** methods are used to persist a **Recordset** and later reopen it:</span></span>

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

<span data-ttu-id="f59f4-139">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="f59f4-139">This section includes the following topics:</span></span>

- [<span data-ttu-id="f59f4-140">有关 Recordset 持久化的详细信息</span><span class="sxs-lookup"><span data-stu-id="f59f4-140">More About Recordset Persistence</span></span>](more-about-recordset-persistence.md)

- [<span data-ttu-id="f59f4-141">持久化筛选和分层记录集</span><span class="sxs-lookup"><span data-stu-id="f59f4-141">Persisting Filtered and Hierarchical Recordsets</span></span>](persisting-filtered-and-hierarchical-recordsets.md)

- [<span data-ttu-id="f59f4-142">Persisting Records in XML Format (ADO)</span><span class="sxs-lookup"><span data-stu-id="f59f4-142">Persisting Records in XML Format (ADO)</span></span>](persisting-records-in-xml-format.md)
