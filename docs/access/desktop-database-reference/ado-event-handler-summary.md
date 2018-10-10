---
title: ADO 事件处理程序摘要
TOCTitle: ADO Event Handler Summary
ms:assetid: f50b9eb4-df6e-7b9d-0b3d-dca8945167a2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250247(v=office.15)
ms:contentKeyID: 48548701
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9042bdbf3271f5aed65f44d8c7f76f1dcbee1d9c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467169"
---
# <a name="ado-event-handler-summary"></a><span data-ttu-id="50931-102">ADO 事件处理程序摘要</span><span class="sxs-lookup"><span data-stu-id="50931-102">ADO Event Handler Summary</span></span>


<span data-ttu-id="50931-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="50931-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="50931-p101">两个 ADO 对象可以引发事件：[Connection](connection-object-ado.md) 对象和 [Recordset](recordset-object-ado.md) 对象。 **ConnectionEvent** 系列用于针对 **Connection** 对象的操作，而 **RecordsetEvent** 系列用于针对 **Recordset** 对象的操作。</span><span class="sxs-lookup"><span data-stu-id="50931-p101">Two ADO objects can raise events: the [Connection](connection-object-ado.md) object and the [Recordset](recordset-object-ado.md) object. The **ConnectionEvent** family pertains to operations on the **Connection** object, and the **RecordsetEvent** family pertains to operations on the **Recordset** object.</span></span>

  - <span data-ttu-id="50931-106">**连接事件** ：在以下情况下发出事件：当连接上的事务启动、提交或回滚时；当 [Command](command-object-ado.md) 执行时；当 **连接事件** 操作期间发生警告时；或者当 **Connection** 开始或结束时。</span><span class="sxs-lookup"><span data-stu-id="50931-106">**Connection Events**: Events are issued when a transaction on a connection begins, is committed, or is rolled back; when a [Command](command-object-ado.md) executes; when a warning occurs during a **Connection Event** operation; or when a **Connection** starts or ends.</span></span>

  - <span data-ttu-id="50931-107">**记录集事件** ：在以下情况下发出事件：在进行异步获取操作时，在 **Recordset** 对象的行中导航时，更改 **Recordset** 行中的字段时，更改 **Recordset** 中的行时，用服务器端游标打开 **Recordset** 时，关闭 **Recordset** 时，或在 **Recordset** 中进行任何更改时。</span><span class="sxs-lookup"><span data-stu-id="50931-107">**Recordset Events**: Events are issued around asynchronous fetch operations as well as when you navigate through the rows of a **Recordset** object, change a field in a row of a **Recordset**, change a row in a **Recordset**, open a **Recordset** with a server-side cursor, close a **Recordset**, or make any change whatsoever in the **Recordset**.</span></span>

<span data-ttu-id="50931-108">下表汇总了事件及其说明。</span><span class="sxs-lookup"><span data-stu-id="50931-108">The following tables summarize the events and their descriptions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="50931-109">ConnectionEvent</span><span class="sxs-lookup"><span data-stu-id="50931-109">ConnectionEvent</span></span></p></th>
<th><p><span data-ttu-id="50931-110">说明</span><span class="sxs-lookup"><span data-stu-id="50931-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50931-111"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a>、 CommitTransComplete RollbackTransComplete</span><span class="sxs-lookup"><span data-stu-id="50931-111"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a>, CommitTransComplete, RollbackTransComplete</span></span></p></td>
<td><p><span data-ttu-id="50931-112"><strong>事务管理</strong>
					 - 通知连接上的当前事务已经启动、提交或回滚。</span><span class="sxs-lookup"><span data-stu-id="50931-112"><strong>Transaction Management</strong> — Notification that the current transaction on the connection has started, committed, or rolled back.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50931-113"><a href="willconnect-event-ado.md">WillConnect</a>， <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete，断开连接</a></span><span class="sxs-lookup"><span data-stu-id="50931-113"><a href="willconnect-event-ado.md">WillConnect</a>, <a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete, Disconnect</a></span></span></p></td>
<td><p><span data-ttu-id="50931-114"><strong>连接管理</strong>
					 - 通知当前连接将开始、已经开始或已经结束。</span><span class="sxs-lookup"><span data-stu-id="50931-114"><strong>Connection Management</strong> — Notification that the current connection will start, has started, or has ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50931-115"><a href="willexecute-event-ado.md">WillExecute</a> <a href="executecomplete-event-ado.md">ExecuteComplete</a></span><span class="sxs-lookup"><span data-stu-id="50931-115"><a href="willexecute-event-ado.md">WillExecute</a>, <a href="executecomplete-event-ado.md">ExecuteComplete</a></span></span></p></td>
<td><p><span data-ttu-id="50931-116"><strong>命令执行管理</strong>
					 - 通知将开始对连接执行当前命令，或已经结束。</span><span class="sxs-lookup"><span data-stu-id="50931-116"><strong>Command Execution Management</strong> — Notification that the execution of the current command on the connection will start or has ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50931-117"><a href="infomessage-event-ado.md">InfoMessage</a></span><span class="sxs-lookup"><span data-stu-id="50931-117"><a href="infomessage-event-ado.md">InfoMessage</a></span></span></p></td>
<td><p><span data-ttu-id="50931-118"><strong>信息</strong>
					 - 通知存在有关当前操作的其他信息。</span><span class="sxs-lookup"><span data-stu-id="50931-118"><strong>Informational</strong> — Notification that there is additional information about the current operation.</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="50931-119">RecordsetEvent</span><span class="sxs-lookup"><span data-stu-id="50931-119">RecordsetEvent</span></span></p></th>
<th><p><span data-ttu-id="50931-120">说明</span><span class="sxs-lookup"><span data-stu-id="50931-120">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50931-121"><a href="fetchprogress-event-ado.md">FetchProgress</a> <a href="fetchcomplete-event-ado.md">FetchComplete</a></span><span class="sxs-lookup"><span data-stu-id="50931-121"><a href="fetchprogress-event-ado.md">FetchProgress</a>, <a href="fetchcomplete-event-ado.md">FetchComplete</a></span></span></p></td>
<td><p><span data-ttu-id="50931-p102"><strong>检索状态</strong>
					 - 通知数据检索操作的进度或检索操作已经完成。只有当 <strong>Recordset</strong> 是使用客户端游标打开时，这些事件才可用。</span><span class="sxs-lookup"><span data-stu-id="50931-p102"><strong>Retrieval Status</strong> — Notification of the progress of a data retrieval operation, or that the retrieval operation has completed. These events are only available if the <strong>Recordset</strong> was opened using a client-side cursor.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50931-124"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField FieldChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="50931-124"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField, FieldChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="50931-125"><strong>字段更改管理</strong>
					 - 通知当前字段的值将更改或已经更改。</span><span class="sxs-lookup"><span data-stu-id="50931-125"><strong>Field Change Management</strong> — Notification that the value of the current field will change, or has changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50931-126"><a href="willmove-and-movecomplete-events-ado.md">WillMove、 MoveComplete</a> <a href="endofrecordset-event-ado.md">EndOfRecordset</a></span><span class="sxs-lookup"><span data-stu-id="50931-126"><a href="willmove-and-movecomplete-events-ado.md">WillMove, MoveComplete</a>, <a href="endofrecordset-event-ado.md">EndOfRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="50931-127"><strong>导航管理</strong>
					 - 通知 <strong>Recordset</strong> 中的当前行位置将更改、已经更改或已经到达 <strong>Recordset</strong> 的末尾。</span><span class="sxs-lookup"><span data-stu-id="50931-127"><strong>Navigation Management</strong> — Notification that the current row position in a <strong>Recordset</strong> will change, has changed, or has reached the end of the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50931-128"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord RecordChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="50931-128"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord, RecordChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="50931-129"><strong>行更改管理</strong>
					 - 通知 <strong>Recordset</strong> 的当前行中的某些内容将更改或已经更改。</span><span class="sxs-lookup"><span data-stu-id="50931-129"><strong>Row Change Management</strong> — Notification that something in the current row of the <strong>Recordset</strong> will change, or has changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50931-130"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">在 WillChangeRecordset RecordsetChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="50931-130"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">WillChangeRecordset, RecordsetChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="50931-131"><strong>记录集更改管理</strong>
					 - 通知当前 <strong>Recordset</strong> 中的某些内容将更改或已经更改。</span><span class="sxs-lookup"><span data-stu-id="50931-131"><strong>Recordset Change Management</strong> — Notification that something in the current <strong>Recordset</strong> will change, or has changed.</span></span></p></td>
</tr>
</tbody>
</table>

