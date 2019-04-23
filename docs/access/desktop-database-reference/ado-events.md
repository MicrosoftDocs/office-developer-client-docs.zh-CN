---
title: ActiveX 数据对象 (ADO) 事件
TOCTitle: ADO events
ms:assetid: 84ca9525-99cb-4ba6-2a4d-172414b8f0cc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249576(v=office.15)
ms:contentKeyID: 48546041
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cc2ef73798dca18e00c42768fde78da2abdb56a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283336"
---
# <a name="ado-events"></a><span data-ttu-id="d08b9-102">ADO 事件</span><span class="sxs-lookup"><span data-stu-id="d08b9-102">ADO events</span></span>

<span data-ttu-id="d08b9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d08b9-103">**Applies to**: Access 2013, Office 2013</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th><span data-ttu-id="d08b9-104">事件</span><span class="sxs-lookup"><span data-stu-id="d08b9-104">Event</span></span></th>
<th><span data-ttu-id="d08b9-105">说明</span><span class="sxs-lookup"><span data-stu-id="d08b9-105">Description</span></span></th>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-106"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-106"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">BeginTransComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-107">在 <strong>BeginTrans</strong> 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-107">Called after the <strong>BeginTrans</strong> operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-108"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">CommitTransComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-108"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">CommitTransComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-109">在 <strong>CommitTrans</strong> 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-109">Called after the <strong>CommitTrans</strong> operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-110"><a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-110"><a href="connectcomplete-and-disconnect-events-ado.md">ConnectComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-111">在连接开始之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-111">Called after a connection starts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-112"><a href="connectcomplete-and-disconnect-events-ado.md">Disconnect</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-112"><a href="connectcomplete-and-disconnect-events-ado.md">Disconnect</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-113">在连接结束之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-113">Called after a connection ends.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-114"><a href="endofrecordset-event-ado.md">EndOfRecordset</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-114"><a href="endofrecordset-event-ado.md">EndOfRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-115">在试图移动到超过 <strong>Recordset</strong> 末尾的行时调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-115">Called when there is an attempt to move to a row past the end of the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-116"><a href="executecomplete-event-ado.md">ExecuteComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-116"><a href="executecomplete-event-ado.md">ExecuteComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-117">在命令完成执行之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-117">Called after a command has finished executing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-118"><a href="fetchcomplete-event-ado.md">FetchComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-118"><a href="fetchcomplete-event-ado.md">FetchComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-119">在冗长的异步操作中的所有记录均已检索到 <strong>Recordset</strong> 中之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-119">Called after all the records in a lengthy asynchronous operation have been retrieved into the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-120"><a href="fetchprogress-event-ado.md">FetchProgress</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-120"><a href="fetchprogress-event-ado.md">FetchProgress</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-121">在冗长的异步操作期间定期调用，以报告当前有多少行已检索到 <strong>Recordset</strong> 中。</span><span class="sxs-lookup"><span data-stu-id="d08b9-121">Called periodically during a lengthy asynchronous operation to report how many rows have currently been retrieved into the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-122"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-122"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">FieldChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-123">在一个或多个 <strong>Field</strong> 对象的值已经更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-123">Called after the value of one or more <strong>Field</strong> objects has changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-124"><a href="infomessage-event-ado.md">InfoMessage</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-124"><a href="infomessage-event-ado.md">InfoMessage</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-125">在 <strong>ConnectionEvent</strong> 操作期间发生警告时调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-125">Called whenever a warning occurs during a <strong>ConnectionEvent</strong> operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-126"><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-126"><a href="willmove-and-movecomplete-events-ado.md">MoveComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-127"><strong>Recordset</strong> 中的当前位置发生更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-127">Called after the current position in the <strong>Recordset</strong> changes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-128"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-128"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">RecordChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-129">一个或多个记录发生更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-129">Called after one or more records change.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-130"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-130"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">RecordsetChangeComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-131"><strong>Recordset</strong> 已经更改之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-131">Called after the <strong>Recordset</strong> has changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-132"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">RollbackTransComplete</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-132"><a href="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md">RollbackTransComplete</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-133">在 <strong>RollbackTrans</strong> 操作之后调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-133">Called after the <strong>RollbackTrans</strong> operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-134"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-134"><a href="willchangefield-and-fieldchangecomplete-events-ado.md">WillChangeField</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-135">在挂起的操作更改 <strong>Recordset</strong> 中一个或多个 <strong>Field</strong> 对象的值之前调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-135">Called before a pending operation changes the value of one or more <strong>Field</strong> objects in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-136"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-136"><a href="willchangerecord-and-recordchangecomplete-events-ado.md">WillChangeRecord</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-137">在 <strong>Recordset</strong> 中一个或多个记录（行）发生更改之前调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-137">Called before one or more records (rows) in the <strong>Recordset</strong> change.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-138"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">WillChangeRecordset</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-138"><a href="willchangerecordset-and-recordsetchangecomplete-events-ado.md">WillChangeRecordset</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-139">在挂起的操作更改 <strong>Recordset</strong> 之前调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-139">Called before a pending operation changes the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-140"><a href="willconnect-event-ado.md">WillConnect</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-140"><a href="willconnect-event-ado.md">WillConnect</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-141">连接开始之前调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-141">Called before a connection starts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d08b9-142"><a href="willexecute-event-ado.md">WillExecute</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-142"><a href="willexecute-event-ado.md">WillExecute</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-143">正好在对此连接执行挂起的命令，让用户有机会检查和修改挂起的执行参数之前调用。</span><span class="sxs-lookup"><span data-stu-id="d08b9-143">Called just before a pending command executes on this connection and affords the user an opportunity to examine and modify the pending execution parameters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d08b9-144"><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></span><span class="sxs-lookup"><span data-stu-id="d08b9-144"><a href="willmove-and-movecomplete-events-ado.md">WillMove</a></span></span></p></td>
<td><p><span data-ttu-id="d08b9-145">在挂起的操作更改 <strong>Recordset</strong> 中的当前位置<em>之前</em>调用 <strong>WillMove</strong> 事件。</span><span class="sxs-lookup"><span data-stu-id="d08b9-145">The <strong>WillMove</strong> event is called <em>before</em> a pending operation changes the current position in the <strong>Recordset</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

<br/>
