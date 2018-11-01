---
title: 将 Microsoft Access 用作 DDE 服务器
TOCTitle: Use Microsoft Access as a DDE Server
description: Microsoft Access 以目标（客户端）应用程序或源（服务器）应用程序形式支持动态数据交换 (DDE)。
ms:assetid: a3e82bf7-94b5-8eec-86bc-2d5387d66738
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821067(v=office.15)
ms:contentKeyID: 48546801
ms.date: 10/16/2018
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm5186349
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0e22eb03571d51f28344f6d41fdcaa47321f67af
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870917"
---
# <a name="use-microsoft-access-as-a-dde-server"></a><span data-ttu-id="1734f-103">将 Microsoft Access 用作 DDE 服务器</span><span class="sxs-lookup"><span data-stu-id="1734f-103">Use Microsoft Access as a DDE server</span></span>

<span data-ttu-id="1734f-104">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1734f-104">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="1734f-p101">Microsoft Access 以目标（客户端）应用程序或源（服务器）应用程序形式支持动态数据交换 (DDE)。例如，一个作为客户端的应用程序，如 Microsoft Word，可以通过 DDE 从一个作为服务器的 Microsoft Access 数据库请求数据。</span><span class="sxs-lookup"><span data-stu-id="1734f-p101">Microsoft Access supports dynamic data exchange (DDE) as either a destination (client) application or a source (server) application. For example, an application such as Microsoft Word, acting as a client, can request data through DDE from a Microsoft Access database that's acting as a server.</span></span>

> [!TIP]
> <span data-ttu-id="1734f-107">[!提示] 如果要从另一个应用程序中操纵 Microsoft Access 对象，可能需要考虑使用"自动化"。</span><span class="sxs-lookup"><span data-stu-id="1734f-107">If you need to manipulate Microsoft Access objects from another application, you may want to consider using Automation.</span></span>

<span data-ttu-id="1734f-108">客户端和服务器之间的 DDE 对话是建立在特定的主题上的。</span><span class="sxs-lookup"><span data-stu-id="1734f-108">A DDE conversation between a client and server is established on a particular topic.</span></span> <span data-ttu-id="1734f-109">主题可以是服务器应用程序所支持格式的数据文件，也可以是提供有关服务器应用程序本身信息的 System 主题。</span><span class="sxs-lookup"><span data-stu-id="1734f-109">A topic can be either a data file in the format supported by the server application, or it can be the System topic, which supplies information about the server application itself.</span></span> <span data-ttu-id="1734f-110">在特定的主题开始对话后，可以传送仅与该主题相关的数据项。</span><span class="sxs-lookup"><span data-stu-id="1734f-110">After a conversation has begun on a particular topic, only a data item associated with that topic can be transferred.</span></span>

<span data-ttu-id="1734f-p103">例如，假定您正在运行 Microsoft Word，并要将一个特定的 Microsoft Access 数据库中的数据插入到文档中。通过使用 **DDEInitiate** 函数将 DDE 通道打开，并指定数据库文件名称作为主题，即可开始与 Microsoft Access 的 DDE 对话，然后就可以通过该通道将数据库中的数据传送给 Microsoft Word。</span><span class="sxs-lookup"><span data-stu-id="1734f-p103">For example, suppose you are running Microsoft Word and want to insert data from a particular Microsoft Access database into a document. You begin a DDE conversation with Microsoft Access by opening a DDE channel with the **DDEInitiate** function and specifying the database file name as the topic. You can then transfer data from that database to Microsoft Word through that channel.</span></span>

<span data-ttu-id="1734f-114">作为 DDE 服务器，Microsoft Access 支持以下主题：</span><span class="sxs-lookup"><span data-stu-id="1734f-114">As a DDE server, Microsoft Access supports the following topics:</span></span>

- <span data-ttu-id="1734f-115">System 主题</span><span class="sxs-lookup"><span data-stu-id="1734f-115">The System topic</span></span>

- <span data-ttu-id="1734f-116">数据库的名称（*database* 主题）</span><span class="sxs-lookup"><span data-stu-id="1734f-116">The name of a database (*database* topic)</span></span>

- <span data-ttu-id="1734f-117">表的名称（*tablename* 主题）</span><span class="sxs-lookup"><span data-stu-id="1734f-117">The name of a table (*tablename* topic)</span></span>

- <span data-ttu-id="1734f-118">查询的名称（*queryname* 主题）</span><span class="sxs-lookup"><span data-stu-id="1734f-118">The name of a query (*queryname* topic)</span></span>

- <span data-ttu-id="1734f-119">Microsoft Access SQL 字符串（*sqlstring* 主题）</span><span class="sxs-lookup"><span data-stu-id="1734f-119">A Microsoft Access SQL string (*sqlstring* topic)</span></span>

<span data-ttu-id="1734f-120">已建立 DDE 会话后，您可以使用**DDEExecute**语句将命令从客户端发送到服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="1734f-120">After you've established a DDE conversation, you can use the **DDEExecute** statement to send a command from the client to the server application.</span></span> <span data-ttu-id="1734f-121">Microsoft Access 在用作 DDE 服务器时，将以下命令均识别为有效命令：</span><span class="sxs-lookup"><span data-stu-id="1734f-121">When used as a DDE server, Microsoft Access recognizes any of the following as a valid command:</span></span>

- <span data-ttu-id="1734f-122">当前数据库中的宏名称。</span><span class="sxs-lookup"><span data-stu-id="1734f-122">The name of a macro in the current database.</span></span>

- <span data-ttu-id="1734f-123">可在 Visual Basic 中使用 **DoCmd** 对象的某个方法执行的任何操作。</span><span class="sxs-lookup"><span data-stu-id="1734f-123">Any action that you can carry out in Visual Basic by using one of the methods of the **DoCmd** object.</span></span>

- <span data-ttu-id="1734f-p105">仅用于 DDE 运算的 OpenDatabase 和 CloseDatabase 操作。（有关如何使用这些操作的示例，请参阅本主题后面部分的示例。）</span><span class="sxs-lookup"><span data-stu-id="1734f-p105">The OpenDatabase and CloseDatabase actions, which are used only for DDE operations. (For an example of how to use these actions, see the example later in this topic.)</span></span>

> [!NOTE]
> <span data-ttu-id="1734f-p106">[!注释] 当将一个宏操作指定为 **DDEExecute** 语句时，该操作和所有参数均遵循 **DoCmd** 对象的语法且必须包含在方括号 ([ ]) 中。但支持 DDE 的应用程序并不识别 DDE 运算中的固有常量。同样，如果字符串包含逗号，则必须将该字符串参数包括在引号 (" ") 中。否则，就不需要引号。</span><span class="sxs-lookup"><span data-stu-id="1734f-p106">When you specify a macro action as a **DDEExecute** statement, the action and any arguments follow the **DoCmd** object syntax and must be enclosed in brackets ([ ]). However, applications that support DDE don't recognize intrinsic constants in DDE operations. Also, string arguments must be enclosed in quotation marks (" ") if the string contains a comma. Otherwise, quotation marks aren't required.</span></span>

<span data-ttu-id="1734f-130">通过打开的 DDE 通道，客户端应用程序可以使用 **DDERequest** 函数向服务器应用程序请求文本数据。</span><span class="sxs-lookup"><span data-stu-id="1734f-130">The client application can use the **DDERequest** function to request text data from the server application over an open DDE channel.</span></span> <span data-ttu-id="1734f-131">反之，客户端可以使用 **DDEPoke** 语句将数据发送到服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="1734f-131">Or the client can use the **DDEPoke** statement to send data to the server application.</span></span> <span data-ttu-id="1734f-132">数据传输完成后，客户端可使用**DDETerminate**语句关闭 DDE 通道或**DDETerminateAll**语句关闭所有打开的通道。</span><span class="sxs-lookup"><span data-stu-id="1734f-132">After the data transfer is complete, the client can use the **DDETerminate** statement to close the DDE channel, or the **DDETerminateAll** statement to close all open channels.</span></span>

> [!NOTE]
> <span data-ttu-id="1734f-133">[!注释] 当客户端应用程序通过 DDE 通道接收完数据后，应关闭该通道以节省内存资源。</span><span class="sxs-lookup"><span data-stu-id="1734f-133">When your client application has finished receiving data over a DDE channel, it should close that channel to conserve memory resources.</span></span>

<span data-ttu-id="1734f-p108">下面的示例将演示如何用 Visual Basic 创建 Microsoft Word 过程，并将 Microsoft Access 用作 DDE 服务器。（必须正在运行 Microsoft Access，才能使该示例工作。）</span><span class="sxs-lookup"><span data-stu-id="1734f-p108">The following example demonstrates how to create a Microsoft Word procedure with Visual Basic that uses Microsoft Access as a DDE server. (For this example to work, Microsoft Access must be running.)</span></span>

```vb
    Sub AccessDDE() 
        Dim intChan1 As Integer, intChan2 As Integer 
        Dim strQueryData As String 
     
        ' Use System topic to open Northwind sample database. 
        ' Database must be open before using other DDE topics. 
        intChan1 = DDEInitiate("MSAccess", "System") 
        ' You may need to change this path to point to actual location 
        ' of Northwind sample database. 
        DDEExecute intChan1, "[OpenDatabase C:\Access\Samples\Northwind.mdb]" 
     
        ' Get all data from Ten Most Expensive Products query. 
        intChan2 = DDEInitiate("MSAccess", "Northwind.mdb;" _ 
            & "QUERY Ten Most Expensive Products") 
        strQueryData = DDERequest(intChan2, "All") 
        DDETerminate intChan2 
     
        ' Close database. 
        DDEExecute intChan1, "[CloseDatabase]" 
        DDETerminate intChan1 
     
        ' Print retrieved data to Debug Window. 
        Debug.Print strQueryData 
    End Sub
```

<br/>

<span data-ttu-id="1734f-136">以下章节提供有关 Microsoft Access 支持的有效 DDE 主题的信息。</span><span class="sxs-lookup"><span data-stu-id="1734f-136">The following sections provide information about the valid DDE topics supported by Microsoft Access.</span></span>

## <a name="the-system-topic"></a><span data-ttu-id="1734f-137">System 主题</span><span class="sxs-lookup"><span data-stu-id="1734f-137">The System topic</span></span>

<span data-ttu-id="1734f-138">System 主题是标准的所有 Microsoft – 基于 Windows 的应用程序主题。</span><span class="sxs-lookup"><span data-stu-id="1734f-138">The System topic is a standard topic for all Microsoft Windows–based applications.</span></span> <span data-ttu-id="1734f-139">它提供有关支持的应用程序的其他主题的信息。</span><span class="sxs-lookup"><span data-stu-id="1734f-139">It supplies information about the other topics supported by the application.</span></span> <span data-ttu-id="1734f-140">若要访问此信息，您的代码必须首先调用**DDEInitiate**函数与*topic*参数，然后使用*item*参数提供下列选项之一执行**DDERequest**语句。</span><span class="sxs-lookup"><span data-stu-id="1734f-140">To access this information, your code must first call the **DDEInitiate** function with the *topic* argument, and then execute the **DDERequest** statement with one of the following supplied for the *item* argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1734f-141">Item</span><span class="sxs-lookup"><span data-stu-id="1734f-141">Item</span></span></p></th>
<th><p><span data-ttu-id="1734f-142">返回</span><span class="sxs-lookup"><span data-stu-id="1734f-142">Returns</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1734f-143">SysItems</span><span class="sxs-lookup"><span data-stu-id="1734f-143">SysItems</span></span></p></td>
<td><p><span data-ttu-id="1734f-144">Microsoft Access 中 System 主题所支持的项目的列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-144">A list of items supported by the System topic in Microsoft Access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-145">Formats</span><span class="sxs-lookup"><span data-stu-id="1734f-145">Formats</span></span></p></td>
<td><p><span data-ttu-id="1734f-146">Microsoft Access 可以复制到“剪贴板”上的格式的列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-146">A list of the formats Microsoft Access can copy onto the Clipboard.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-147">Status</span><span class="sxs-lookup"><span data-stu-id="1734f-147">Status</span></span></p></td>
<td><p><span data-ttu-id="1734f-148">&quot;忙&quot;或&quot;准备&quot;。</span><span class="sxs-lookup"><span data-stu-id="1734f-148">&quot;Busy&quot; or &quot;Ready&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-149">Topics</span><span class="sxs-lookup"><span data-stu-id="1734f-149">Topics</span></span></p></td>
<td><p><span data-ttu-id="1734f-150">所有已打开的数据库的列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-150">A list of all open databases.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="1734f-151">下面的示例说明如何使用带有 System 主题的 **DDEInitiate** 和 **DDERequest** 函数：</span><span class="sxs-lookup"><span data-stu-id="1734f-151">The following example demonstrates the use of the **DDEInitiate** and **DDERequest** functions with the System topic:</span></span>

```vb
    ' In Visual Basic, initiate DDE conversation with Microsoft Access. 
    Dim intChan1 As Integer, strResults As String 
    intChan1 = DDEInitiate("MSAccess", "System") 
    ' Request list of topics supported by System topic. 
    strResults = DDERequest(intChan1, "SysItems") 
    ' Run OpenDatabase action to open Northwind.mdb. 
    ' You may need to change this path to point to actual location 
    ' of Northwind sample database. 
    DDEExecute intChan1, "[OpenDatabase C:\Access\Samples\Northwind.mdb]"
```

## <a name="the-database-topic"></a><span data-ttu-id="1734f-152">Database 主题</span><span class="sxs-lookup"><span data-stu-id="1734f-152">The database topic</span></span>

<span data-ttu-id="1734f-153">*Database*主题是数据库的一个现有的文件名。</span><span class="sxs-lookup"><span data-stu-id="1734f-153">The *database* topic is the file name of an existing database.</span></span> <span data-ttu-id="1734f-154">您可以键入刚的基名称 (Northwind) 或其路径和.mdb 扩展名 (c:\\访问\\示例\\Northwind.mdb)。</span><span class="sxs-lookup"><span data-stu-id="1734f-154">You can type either just the base name (Northwind), or its path and .mdb extension (C:\\Access\\Samples\\Northwind.mdb).</span></span> <span data-ttu-id="1734f-155">在开始与该数据库的 DDE 对话以后，可以请求该数据库中的对象列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-155">After you start a DDE conversation with the database, you can request a list of the objects in that database.</span></span>

> [!NOTE]
> <span data-ttu-id="1734f-156">[!注释] 不能使用 DDE 来查询 Microsoft Access 工作组信息文件。</span><span class="sxs-lookup"><span data-stu-id="1734f-156">You can't use DDE to query the Microsoft Access workgroup information file.</span></span>

<span data-ttu-id="1734f-157">*database* 主题支持以下项目。</span><span class="sxs-lookup"><span data-stu-id="1734f-157">The *database* topic supports the following items.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1734f-158">Item</span><span class="sxs-lookup"><span data-stu-id="1734f-158">Item</span></span></p></th>
<th><p><span data-ttu-id="1734f-159">返回</span><span class="sxs-lookup"><span data-stu-id="1734f-159">Returns</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1734f-160">TableList</span><span class="sxs-lookup"><span data-stu-id="1734f-160">TableList</span></span></p></td>
<td><p><span data-ttu-id="1734f-161">表的列表</span><span class="sxs-lookup"><span data-stu-id="1734f-161">A list of tables</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-162">QueryList</span><span class="sxs-lookup"><span data-stu-id="1734f-162">QueryList</span></span></p></td>
<td><p><span data-ttu-id="1734f-163">查询列表</span><span class="sxs-lookup"><span data-stu-id="1734f-163">A list of queries</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-164">FormList</span><span class="sxs-lookup"><span data-stu-id="1734f-164">FormList</span></span></p></td>
<td><p><span data-ttu-id="1734f-165">窗体列表</span><span class="sxs-lookup"><span data-stu-id="1734f-165">A list of forms</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-166">ReportList</span><span class="sxs-lookup"><span data-stu-id="1734f-166">ReportList</span></span></p></td>
<td><p><span data-ttu-id="1734f-167">报表的列表</span><span class="sxs-lookup"><span data-stu-id="1734f-167">A list of reports</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-168">MacroList</span><span class="sxs-lookup"><span data-stu-id="1734f-168">MacroList</span></span></p></td>
<td><p><span data-ttu-id="1734f-169">宏列表</span><span class="sxs-lookup"><span data-stu-id="1734f-169">A list of macros</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-170">ModuleList</span><span class="sxs-lookup"><span data-stu-id="1734f-170">ModuleList</span></span></p></td>
<td><p><span data-ttu-id="1734f-171">模块列表</span><span class="sxs-lookup"><span data-stu-id="1734f-171">A list of modules</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-172">ViewList</span><span class="sxs-lookup"><span data-stu-id="1734f-172">ViewList</span></span></p></td>
<td><p><span data-ttu-id="1734f-173">视图列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-173">A list of views</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-174">StoredProcedureList</span><span class="sxs-lookup"><span data-stu-id="1734f-174">StoredProcedureList</span></span></p></td>
<td><p><span data-ttu-id="1734f-175">存储过程列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-175">A list of stored procedures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-176">DatabaseDiagramList</span><span class="sxs-lookup"><span data-stu-id="1734f-176">DatabaseDiagramList</span></span></p></td>
<td><p><span data-ttu-id="1734f-177">数据库图表列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-177">A list of database diagrams</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="1734f-178">下面的示例显示如何从 Visual Basic 过程中打开“罗斯文”示例数据库中的“雇员”窗体：</span><span class="sxs-lookup"><span data-stu-id="1734f-178">The following example shows how you can open the Employees form in the Northwind sample database from a Visual Basic procedure:</span></span>

```vb
    ' In Visual Basic, initiate DDE conversation with 
    ' Northwind sample database. 
    ' Make sure database is open. 
    intChan2 = DDEInitiate("MSAccess", "Northwind") 
    ' Request list of forms in Northwind sample database. 
    strResponse = DDERequest(intChan2, "FormList") 
    ' Run OpenForm action and arguments to open Employees form. 
    DDEExecute intChan2, "[OpenForm Employees,0,,,1,0]"
```

## <a name="the-table-topic"></a><span data-ttu-id="1734f-179">表主题</span><span class="sxs-lookup"><span data-stu-id="1734f-179">The TABLE topic</span></span>

<span data-ttu-id="1734f-180">这些主题使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1734f-180">These topics use the following syntax:</span></span>

<span data-ttu-id="1734f-181">_databasename_ ;**表**_tablename_</span><span class="sxs-lookup"><span data-stu-id="1734f-181">_databasename_ ; **TABLE** _tablename_</span></span>

<span data-ttu-id="1734f-182">_databasename_ ;**查询**_查询_</span><span class="sxs-lookup"><span data-stu-id="1734f-182">_databasename_ ; **QUERY** _queryname_</span></span>

<span data-ttu-id="1734f-183">_databasename_ ;**SQL**[ _sqlstring_ ]</span><span class="sxs-lookup"><span data-stu-id="1734f-183">_databasename_ ; **SQL** [ _sqlstring_ ]</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1734f-184">部分</span><span class="sxs-lookup"><span data-stu-id="1734f-184">Part</span></span></p></th>
<th><p><span data-ttu-id="1734f-185">说明</span><span class="sxs-lookup"><span data-stu-id="1734f-185">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1734f-186"><em>databasename</em></span><span class="sxs-lookup"><span data-stu-id="1734f-186"><em>databasename</em></span></span></p></td>
<td><p><span data-ttu-id="1734f-p111">表或查询所在的数据库或 SQL 语句应用到的数据库的名称，后跟一个分号 (;)。数据库名称可以只是基本名称 (Northwind)，也可以外加完整路径和 .mdb 扩展名 (C:\Access\Samples\Northwind.mdb)。</span><span class="sxs-lookup"><span data-stu-id="1734f-p111">The name of the database that the table or query is in or that the SQL statement applies to, followed by a semicolon (;). The database name can be just the base name (Northwind) or its full path and .mdb extension (C:\Access\Samples\Northwind.mdb).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-189"><em>tablename</em></span><span class="sxs-lookup"><span data-stu-id="1734f-189"><em>tablename</em></span></span></p></td>
<td><p><span data-ttu-id="1734f-190">某个已有表的名称。</span><span class="sxs-lookup"><span data-stu-id="1734f-190">The name of an existing table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-191"><em>queryname</em></span><span class="sxs-lookup"><span data-stu-id="1734f-191"><em>queryname</em></span></span></p></td>
<td><p><span data-ttu-id="1734f-192">某个已有查询的名称。</span><span class="sxs-lookup"><span data-stu-id="1734f-192">The name of an existing query.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-193"><em>sqlstring</em></span><span class="sxs-lookup"><span data-stu-id="1734f-193"><em>sqlstring</em></span></span></p></td>
<td><p><span data-ttu-id="1734f-194">最多 256 个字符之间，用分号结束有效的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1734f-194">A valid SQL statement up to 256 characters long, ending with a semicolon.</span></span> <span data-ttu-id="1734f-195">Exchange 超过 256 个字符，忽略此参数，而是使用连续<strong>DDEPoke</strong>语句来建立 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1734f-195">To exchange more than 256 characters, omit this argument and instead use successive <strong>DDEPoke</strong> statements to build an SQL statement.</span></span> <span data-ttu-id="1734f-196">例如，以下 Visual Basic 代码使用 <strong>DDEPoke</strong> 语句来建立 SQL 语句，然后请求查询结果。</span><span class="sxs-lookup"><span data-stu-id="1734f-196">For example, the following Visual Basic code uses the <strong>DDEPoke</strong> statement to build an SQL statement and then request the results of the query.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="1734f-197">下表列出了 TABLE *tablename*、QUERY *queryname* 和 SQL *sqlstring* 主题的有效项目。</span><span class="sxs-lookup"><span data-stu-id="1734f-197">The following table lists the valid items for the TABLE *tablename*, QUERY *queryname*, and SQL *sqlstring* topics.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1734f-198">Item</span><span class="sxs-lookup"><span data-stu-id="1734f-198">Item</span></span></p></th>
<th><p><span data-ttu-id="1734f-199">返回</span><span class="sxs-lookup"><span data-stu-id="1734f-199">Returns</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1734f-200">All</span><span class="sxs-lookup"><span data-stu-id="1734f-200">All</span></span></p></td>
<td><p><span data-ttu-id="1734f-201">表中的所有数据，包括字段名。</span><span class="sxs-lookup"><span data-stu-id="1734f-201">All the data in the table, including field names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-202">Data</span><span class="sxs-lookup"><span data-stu-id="1734f-202">Data</span></span></p></td>
<td><p><span data-ttu-id="1734f-203">所有数据行，不含字段名。</span><span class="sxs-lookup"><span data-stu-id="1734f-203">All rows of data, without field names.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-204">FieldNames</span><span class="sxs-lookup"><span data-stu-id="1734f-204">FieldNames</span></span></p></td>
<td><p><span data-ttu-id="1734f-205">字段名单行列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-205">A single-row list of field names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-206">FieldNames;T</span><span class="sxs-lookup"><span data-stu-id="1734f-206">FieldNames;T</span></span></p></td>
<td><p><span data-ttu-id="1734f-207">字段名（第一行）及其数据类型（第二行）的双行列表。</span><span class="sxs-lookup"><span data-stu-id="1734f-207">A two-row list of field names (first row) and their data types (second row).</span></span></p>
<p><span data-ttu-id="1734f-208">下面是返回的值：</span><span class="sxs-lookup"><span data-stu-id="1734f-208">These are the values returned:</span></span></p>
<p><span data-ttu-id="1734f-209">值</span><span class="sxs-lookup"><span data-stu-id="1734f-209">Value</span></span></p>
<p><ul>
<li><span data-ttu-id="1734f-210">0</span><span class="sxs-lookup"><span data-stu-id="1734f-210">0</span></span></li>
<li><span data-ttu-id="1734f-211">1</span><span class="sxs-lookup"><span data-stu-id="1734f-211">1</span></span></li>
<li><span data-ttu-id="1734f-212">2</span><span class="sxs-lookup"><span data-stu-id="1734f-212">2</span></span></li>
<li><span data-ttu-id="1734f-213">3</span><span class="sxs-lookup"><span data-stu-id="1734f-213">3</span></span></li>
<li><span data-ttu-id="1734f-214">4</span><span class="sxs-lookup"><span data-stu-id="1734f-214">4</span></span></li>
<li><span data-ttu-id="1734f-215">5</span><span class="sxs-lookup"><span data-stu-id="1734f-215">5</span></span></li>
<li><span data-ttu-id="1734f-216">6</span><span class="sxs-lookup"><span data-stu-id="1734f-216">6</span></span></li>
<li><span data-ttu-id="1734f-217">7</span><span class="sxs-lookup"><span data-stu-id="1734f-217">7</span></span></li>
<li><span data-ttu-id="1734f-218">8</span><span class="sxs-lookup"><span data-stu-id="1734f-218">8</span></span></li>
<li><span data-ttu-id="1734f-219">9</span><span class="sxs-lookup"><span data-stu-id="1734f-219">9</span></span></li>
<li><span data-ttu-id="1734f-220">10</span><span class="sxs-lookup"><span data-stu-id="1734f-220">10</span></span></li>
<li><span data-ttu-id="1734f-221">11</span><span class="sxs-lookup"><span data-stu-id="1734f-221">11</span></span></li>
<li><span data-ttu-id="1734f-222">12</span><span class="sxs-lookup"><span data-stu-id="1734f-222">12</span></span></li>
</ul>
</p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-223">NextRow</span><span class="sxs-lookup"><span data-stu-id="1734f-223">NextRow</span></span></p></td>
<td><p><span data-ttu-id="1734f-p113">表或查询中下一行的数据。当打开一个通道时，NextRow 返回第一行中的数据。如果当前行是最后一条记录并运行 NextRow，则请求会失败。</span><span class="sxs-lookup"><span data-stu-id="1734f-p113">The data in the next row in the table or query. When you open a channel, NextRow returns the data in the first row. If the current row is the last record and you run NextRow, the request fails.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-227">PrevRow</span><span class="sxs-lookup"><span data-stu-id="1734f-227">PrevRow</span></span></p></td>
<td><p><span data-ttu-id="1734f-p114">表或查询中上一行的数据。如果 PrevRow 是新通道中的第一个请求，该表或查询的最后一行中的数据返回。如果第一条记录是当前行，则 PrevRow 请求会失败。</span><span class="sxs-lookup"><span data-stu-id="1734f-p114">The data in the previous row in the table or query. If PrevRow is the first request on a new channel, the data in the last row of the table or query is returned. If the first record is the current row, the request for PrevRow fails.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-231">FirstRow</span><span class="sxs-lookup"><span data-stu-id="1734f-231">FirstRow</span></span></p></td>
<td><p><span data-ttu-id="1734f-232">表或查询中第一行的数据。</span><span class="sxs-lookup"><span data-stu-id="1734f-232">The data in the first row of the table or query.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-233">LastRow</span><span class="sxs-lookup"><span data-stu-id="1734f-233">LastRow</span></span></p></td>
<td><p><span data-ttu-id="1734f-234">表或查询中最后一行的数据。</span><span class="sxs-lookup"><span data-stu-id="1734f-234">The data in the last row of the table or query.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-235">FieldCount</span><span class="sxs-lookup"><span data-stu-id="1734f-235">FieldCount</span></span></p></td>
<td><p><span data-ttu-id="1734f-236">表或查询中字段的数目。</span><span class="sxs-lookup"><span data-stu-id="1734f-236">The number of fields in the table or query.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1734f-237">SQLText</span><span class="sxs-lookup"><span data-stu-id="1734f-237">SQLText</span></span></p></td>
<td><p><span data-ttu-id="1734f-238">表示表或查询的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1734f-238">An SQL statement representing the table or query.</span></span> <span data-ttu-id="1734f-239">对于表，此项返回的 SQL 语句形式&quot;选择`*`从<em>表</em>;&quot;.</span><span class="sxs-lookup"><span data-stu-id="1734f-239">For tables, this item returns an SQL statement in the form &quot;SELECT `*` FROM <em>table</em>;&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1734f-240">SQLText;<em>n</em></span><span class="sxs-lookup"><span data-stu-id="1734f-240">SQLText;<em>n</em></span></span></p></td>
<td><p><span data-ttu-id="1734f-241">SQL 语句， <em>n</em>-字符块大小，表示表或查询，其中<em>n</em>是最多 256 的整数。</span><span class="sxs-lookup"><span data-stu-id="1734f-241">An SQL statement, in <em>n</em>-character chunks, representing the table or query, where <em>n</em> is an integer up to 256.</span></span> <span data-ttu-id="1734f-242">例如，假设查询由以下 SQL 语句： 项目&quot;SQLText; 7&quot;返回以下以制表符分隔的块： 项目&quot;SQLText; 7&quot;返回以下以制表符分隔的块：</span><span class="sxs-lookup"><span data-stu-id="1734f-242">For example, suppose a query is represented by the following SQL statement: The item &quot;SQLText;7&quot; returns the following tab-delimited chunks: The item &quot;SQLText;7&quot; returns the following tab-delimited chunks:</span></span></p></td>
</tr>
</tbody>
</table>

<br/>

<span data-ttu-id="1734f-243">下面的示例显示在 Visual Basic 过程中如何使用 DDE 请求"罗斯文"示例数据库的表中的数据，并将该数据插入到文本文件中：</span><span class="sxs-lookup"><span data-stu-id="1734f-243">The following example shows how you can use DDE in a Visual Basic procedure to request data from a table in the Northwind sample database and insert that data into a text file:</span></span>

```vb
    Sub NorthwindDDE 
        Dim intChan1 As Integer, intChan2 As Integer, intChan3 As Integer 
        Dim strResp1 As Variant, strResp2 As Variant, strResp3 As Variant 
     
        ' In a Visual Basic module, get data from Categories table, 
        ' Catalog query, and Orders table in Northwind.mdb. 
        ' Make sure database is open first. 
        intChan1 = DDEInitiate("MSAccess", "Northwind;TABLE Shippers") 
        intChan2 = DDEInitiate("MSAccess", "Northwind;QUERY Catalog") 
        intChan3 = DDEInitiate("MSAccess", "Northwind;SQL SELECT * " _ 
            & "FROM Orders " _ 
            & "WHERE OrderID > 10050;") 
     
        strResp1 = DDERequest(intChan1, "All") 
        strResp2 = DDERequest(intChan2, "FieldNames;T") 
        strResp3 = DDERequest(intChan3, "FieldNames;T") 
        DDETerminate intChan1 
        DDETerminate intChan2 
        DDETerminate intChan3 
     
        ' Insert data into text file. 
        Open "C:\DATA.TXT" For Append As #1 
        Print #1, strResp1 
        Print #1, strResp2 
        Print #1, strResp3 
        Close #1 
    End Sub
```
