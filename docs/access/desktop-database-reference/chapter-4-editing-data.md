---
title: 第 4 章：编辑数据
TOCTitle: 'Chapter 4: Editing data'
ms:assetid: 822b7365-0926-6411-6fb4-30de032570f8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249563(v=office.15)
ms:contentKeyID: 48545974
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b954cf8b730a74fb7e630fbafb96c046491c6f46
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701142"
---
# <a name="chapter-4-editing-data"></a><span data-ttu-id="24708-102">第 4 章：编辑数据</span><span class="sxs-lookup"><span data-stu-id="24708-102">Chapter 4: Editing data</span></span>

<span data-ttu-id="24708-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="24708-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="24708-p101">前面两章解释了如何使用 ADO 来连接数据源，执行命令，获取 **Recordset** 对象中的结果以及在 **Recordset** 中进行导航。本章重点介绍下一个基本 ADO 操作：编辑数据。</span><span class="sxs-lookup"><span data-stu-id="24708-p101">The preceding two chapters explained how use ADO to connect to a data source, execute a command, get the results in a **Recordset** object, and navigate within the **Recordset**. This chapter focuses on the next fundamental ADO operation: editing data.</span></span>

<span data-ttu-id="24708-p102">本章继续使用第 3 章中引入的示例 **Recordset** - 但有一项重要更改。使用以下代码打开 **Recordset** ：</span><span class="sxs-lookup"><span data-stu-id="24708-p102">This chapter continues to use the sample **Recordset** introduced in Chapter 3 — with one important change. The following code is used to open the **Recordset**:</span></span>

```vb 
 
 . . . 
'BeginEditIntro 
 Dim strSQL As String 
 Dim objRs1 As ADODB.Recordset 
 
 strSQL = "SELECT * FROM Shippers" 
 
 Set objRs1 = New ADODB.Recordset 
 
 objRs1.Open strSQL, GetNewConnection, adOpenStatic, _ 
 adLockBatchOptimistic, adCmdText 
 
 ' Disconnect the Recordset from the Connection object. 
 Set objRs1.ActiveConnection = Nothing 
'EndEditIntro 
 
 
 . . . 
```

<span data-ttu-id="24708-p103">对代码的重要更改涉及在 GetNewConnection 函数中将 **Connection** 对象的 **CursorLocation** 属性设置为等于 **adUseClient** （如下所示），以指示客户端游标的使用情况。有关客户端和服务器端游标之间的差异的详细信息，请参阅 [第 8 章：了解游标和锁定](chapter-8-understanding-cursors-and-locks.md)。</span><span class="sxs-lookup"><span data-stu-id="24708-p103">The important change to the code involves setting the **Connection** object's **CursorLocation** property equal to **adUseClient** in the GetNewConnection function (shown below), which indicates the use of a client cursor. For more information about the differences between client-side and server-side cursors, see [Chapter 8: Understanding Cursors and Locks](chapter-8-understanding-cursors-and-locks.md).</span></span>

<span data-ttu-id="24708-p104">**CursorLocation** 属性的 **adUseClient** 设置会将游标位置从数据源（在本例中是 SQL Server）移动到客户端代码所指示的位置（桌面工作站）。此设置将强制 ADO 调用客户端上的 OLE DB 客户端游标引擎来创建和管理游标。</span><span class="sxs-lookup"><span data-stu-id="24708-p104">The **CursorLocation** property's **adUseClient** setting moves the location of the cursor from the data source (the SQL Server, in this case) to the location of the client code (the desktop workstation). This setting forces ADO to invoke the Client Cursor Engine for OLE DB on the client in order to create and manage the cursor.</span></span>

<span data-ttu-id="24708-p105">您还可能注意到 **Open** 方法的 **LockType** 参数已更改为 **adLockBatchOptimistic** ，这样将在批模式下打开游标。（提供程序会缓存多个更改，只有当您调用 **UpdateBatch** 方法时，才会将它们写入基础数据源。）只有在调用 **UpdateBatch** 方法后，对 **Recordset** 的更改才会更新到数据库中。</span><span class="sxs-lookup"><span data-stu-id="24708-p105">You might also have noticed that the **LockType** parameter of the **Open** method changed to **adLockBatchOptimistic**. This opens the cursor in batch mode. (The provider caches multiple changes and writes them to the underlying data source only when you call the **UpdateBatch** method.) Changes made to the **Recordset** will not be updated in the database until the **UpdateBatch** method is called.</span></span>

<span data-ttu-id="24708-p106">最后，本章中的代码将使用第 2 章引入的 GetNewConnection 函数版本，但会稍作修改。该函数的这个版本现在将返回一个客户端游标。该函数类似于：</span><span class="sxs-lookup"><span data-stu-id="24708-p106">Finally, the code in this chapter uses a modified version of the GetNewConnection function, introduced in Chapter 2. This version of the function now returns a client-side cursor. The function looks like this:</span></span>

```vb 
 
'BeginNewConnection 
Public Function GetNewConnection() As ADODB.Connection 
 Dim objConn1 As ADODB.Connection 
 Set objConn1 = New ADODB.Connection 
 
 strConnStr = "Provider=SQLOLEDB;Initial Catalog=Northwind;" & _ 
 "Data Source=MySrvr;Integrated Security=SSPI;" 
 
 objConn1.ConnectionString = strConnStr 
 objConn1.CursorLocation = adUseClient 
 objConn1.Open 
 
 Set GetNewConnection = objConn1 
End Function 
'EndNewConnection 
```

<span data-ttu-id="24708-118">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="24708-118">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="24708-119">编辑现有记录</span><span class="sxs-lookup"><span data-stu-id="24708-119">Editing existing records</span></span>](editing-existing-records.md)
- [<span data-ttu-id="24708-120">确定什么受支持</span><span class="sxs-lookup"><span data-stu-id="24708-120">Determining what is supported</span></span>](determining-what-is-supported.md)
- [<span data-ttu-id="24708-121">使用 Delete 方法删除记录</span><span class="sxs-lookup"><span data-stu-id="24708-121">Deleting records using the Delete method</span></span>](deleting-records-using-the-delete-method.md)
- [<span data-ttu-id="24708-122">替代方法： 使用 SQL 语句</span><span class="sxs-lookup"><span data-stu-id="24708-122">Alternatives: using SQL statements</span></span>](alternatives-using-sql-statements.md)
- [<span data-ttu-id="24708-123">添加记录 (ADO)</span><span class="sxs-lookup"><span data-stu-id="24708-123">Adding records (ADO)</span></span>](adding-records.md)
