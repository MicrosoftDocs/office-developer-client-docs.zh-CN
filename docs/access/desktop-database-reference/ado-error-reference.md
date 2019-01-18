---
title: ADO 错误参考
TOCTitle: ADO error reference
ms:assetid: 21cec161-664a-4c18-4458-8117f4f63845
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248997(v=office.15)
ms:contentKeyID: 48543690
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6a7f756af1422588d99fcffe1ae1413422131b70
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717235"
---
# <a name="ado-error-reference"></a><span data-ttu-id="7e442-102">ADO 错误参考</span><span class="sxs-lookup"><span data-stu-id="7e442-102">ADO error reference</span></span>

<span data-ttu-id="7e442-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e442-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7e442-p101">**ErrorValueEnum** 常量描述 ADO 的错误值。若要获得这些枚举常量（包括值）的完整列表，请参阅 [附录 B：ADO 错误](appendix-b-ado-errors.md)。本部分将分析一些更有意思的错误并说明可能引发这些错误的某些特定情况或解决问题的解决方案。下面列出了 **ErrorValueEnum** 常量和短型正小数。</span><span class="sxs-lookup"><span data-stu-id="7e442-p101">The **ErrorValueEnum** constant describes the ADO error values. For a complete listing of these enumerated constants, including values, see [Appendix B: ADO Errors](appendix-b-ado-errors.md). This section will examine some of the more interesting errors and explain some specific situations that can raise them, or solutions to fix the problem. Both the **ErrorValueEnum** constant and the short positive decimal number are listed.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7e442-108">编号</span><span class="sxs-lookup"><span data-stu-id="7e442-108">Number</span></span></p></th>
<th><p><span data-ttu-id="7e442-109">ErrorValueEnum 常量</span><span class="sxs-lookup"><span data-stu-id="7e442-109">ErrorValueEnum constant</span></span></p></th>
<th><p><span data-ttu-id="7e442-110">说明/可能的原因</span><span class="sxs-lookup"><span data-stu-id="7e442-110">Description/Possible causes</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e442-111"><strong>3000</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-111"><strong>3000</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-112"><strong>adErrProviderFailed</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-112"><strong>adErrProviderFailed</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-113">提供程序未能执行请求的操作。</span><span class="sxs-lookup"><span data-stu-id="7e442-113">Provider failed to perform the requested operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-114"><strong>3001</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-114"><strong>3001</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-115"><strong>adErrInvalidArgument</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-115"><strong>adErrInvalidArgument</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p102">参数类型不正确，或不在可以接受的范围之内，或与其他参数冲突。此错误通常是由 SQL SELECT 语句中的录入错误导致的。例如，拼错的字段名称或表名称可能会导致此错误。当 SELECT 语句中指定的字段或表在数据存储区中不存在时也会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="7e442-p102">Arguments are of the wrong type, are out of acceptable range, or are in conflict with one another. This error is often caused by a typographical error in an SQL SELECT statement. For example, a misspelled field name or table name can generate this error. This error can also occur when a field or table named in a SELECT statement does not exist in the data store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-120"><strong>3002</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-120"><strong>3002</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-121"><strong>adErrOpeningFile</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-121"><strong>adErrOpeningFile</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p103">无法打开文件。指定的文件名拼写错误，或者文件已被移动、重命名或删除。在网络上，驱动器可能临时不可用，或网络流量可能阻止了连接。</span><span class="sxs-lookup"><span data-stu-id="7e442-p103">File could not be opened. A misspelled file name was specified, or a file has been moved, renamed, or deleted. Over a network, the drive might be temporarily unavailable or network traffic might be preventing a connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-125"><strong>3003</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-125"><strong>3003</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-126"><strong>adErrReadFile</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-126"><strong>adErrReadFile</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p104">无法读取文件。没有正确指定文件名称，文件可能已被移动或删除，或者文件可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="7e442-p104">File could not be read. The name of the file is specified incorrectly, the file might have been moved or deleted, or the file might have become corrupted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-129"><strong>3004</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-129"><strong>3004</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-130"><strong>adErrWriteFile</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-130"><strong>adErrWriteFile</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p105">写入文件失败。您可能在已经关闭文件后试图向其中写入，或者文件可能损坏。如果文件位于网络驱动器上，网络短时间的不稳定可能阻止写入网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="7e442-p105">Write to file failed. You might have closed a file and then tried to write to it, or the file might be corrupted. If the file is located on a network drive, transient network conditions might prevent writing to a network drive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-134"><strong>3021</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-134"><strong>3021</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-135"><strong>adErrNoCurrentRecord</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-135"><strong>adErrNoCurrentRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p106">可以是 <strong>BOF</strong> 或 <strong>EOF</strong> 为 True，或者是当前记录已被删除。请求的操作需要当前记录。通过使用 <strong>Find</strong> 或 <strong>Seek</strong> 将记录指针移动到所需的记录来尝试更新记录。如果找不到所需的记录， <strong>EOF</strong> 将为 True。在 <strong>AddNew</strong> 或 <strong>Delete</strong> 失败后，也可能发生此错误，因为这些方法失败时，不存在当前记录。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p106">Either <strong>BOF</strong> or <strong>EOF</strong> is True, or the current record has been deleted. Requested operation requires a current record. An attempt was made to update records by using <strong>Find</strong> or <strong>Seek</strong> to move the record pointer to the desired record. If the record is not found, <strong>EOF</strong> will be True. This error can also occur after a failed <strong>AddNew</strong> or <strong>Delete</strong> because there is no current record when these methods fail.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-141"><strong>3219</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-141"><strong>3219</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-142"><strong>adErrIllegalOperation</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-142"><strong>adErrIllegalOperation</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-143">此上下文中不允许操作。</span><span class="sxs-lookup"><span data-stu-id="7e442-143">Operation is not allowed in this context.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-144"><strong>3220</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-144"><strong>3220</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-145"><strong>adErrCantChangeProvider</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-145"><strong>adErrCantChangeProvider</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-146">所提供的提供程序与正在使用的提供程序不同。</span><span class="sxs-lookup"><span data-stu-id="7e442-146">Supplied provider is different from the one already in use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-147"><strong>3246</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-147"><strong>3246</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-148"><strong>adErrInTransaction</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-148"><strong>adErrInTransaction</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p107">在事务处理过程中，不能显式关闭 <strong>Connection</strong> 对象。不能关闭当前参与事务的 <strong>Recordset</strong> 或 <strong>Connection</strong> 对象。请在关闭该对象前调用 <strong>RollbackTrans</strong> 或 <strong>CommitTrans</strong> 。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p107"><strong>Connection</strong> object cannot be explicitly closed while in a transaction. A <strong>Recordset</strong> or <strong>Connection</strong> object that is currently participating in a transaction cannot be closed. Call either <strong>RollbackTrans</strong> or <strong>CommitTrans</strong> before closing the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-152"><strong>3251</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-152"><strong>3251</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-153"><strong>adErrFeatureNotAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-153"><strong>adErrFeatureNotAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p108">对象或提供程序不能执行请求的操作。某些操作依赖于特定的提供程序版本。</span><span class="sxs-lookup"><span data-stu-id="7e442-p108">The object or provider is not capable of performing the requested operation. Some operations depend on a particular provider version.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-156"><strong>3265</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-156"><strong>3265</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-157"><strong>adErrItemNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-157"><strong>adErrItemNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p109">在对应于所请求的名称或序号的集合中没有找到项。指定的字段名或表名错误。</span><span class="sxs-lookup"><span data-stu-id="7e442-p109">Item cannot be found in the collection corresponding to the requested name or ordinal. An incorrect field or table name has been specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-160"><strong>3367</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-160"><strong>3367</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-161"><strong>adErrObjectInCollection</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-161"><strong>adErrObjectInCollection</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p110">对象已在集合中。不能追加。一个对象不能向同一集合添加两次。</span><span class="sxs-lookup"><span data-stu-id="7e442-p110">Object is already in collection. Cannot append. An object cannot be added to the same collection twice.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-165"><strong>3420</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-165"><strong>3420</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-166"><strong>adErrObjectNotSet</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-166"><strong>adErrObjectNotSet</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-167">对象不再有效。</span><span class="sxs-lookup"><span data-stu-id="7e442-167">Object is no longer valid.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-168"><strong>3421</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-168"><strong>3421</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-169"><strong>adErrDataConversion</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-169"><strong>adErrDataConversion</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p111">应用程序在当前操作中使用了错误类型的值。例如，您可能为需要数据流的操作提供了一个字符串。</span><span class="sxs-lookup"><span data-stu-id="7e442-p111">Application uses a value of the wrong type for the current operation. You might have supplied a string to an operation that expects a stream, for example.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-172"><strong>3704</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-172"><strong>3704</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-173"><strong>adErrObjectClosed</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-173"><strong>adErrObjectClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p112">对象关闭时不允许操作。 <strong>Connection</strong> 或 <strong>Recordset</strong> 已关闭。例如，某个其他例程可能已经关闭了全局对象。在尝试操作前，可以通过检查 <strong>State</strong> 属性来防止此错误。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p112">Operation is not allowed when the object is closed. The <strong>Connection</strong> or <strong>Recordset</strong> has been closed. For example, some other routine might have closed a global object. You can prevent this error by checking the <strong>State</strong> property before you attempt an operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-178"><strong>3705</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-178"><strong>3705</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-179"><strong>adErrObjectOpen</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-179"><strong>adErrObjectOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p113">对象打开时不允许操作。不能打开已打开的对象。不能将字段追加到打开的 <strong>Recordset</strong> 。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p113">Operation is not allowed when the object is open. An object that is open cannot be opened. Fields cannot be appended to an open <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-183"><strong>3706</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-183"><strong>3706</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-184"><strong>adErrProviderNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-184"><strong>adErrProviderNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p114">找不到提供程序。可能没有正确安装该提供程序。可能没有正确指定该提供程序的名称，指定的提供程序可能没有安装在执行代码的计算机上，或者安装可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="7e442-p114">Provider cannot be found. It may not be properly installed. The name of the provider might be incorrectly specified, the specified provider might not be installed on the computer where your code is being executed, or the installation might have become corrupted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-188"><strong>3707</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-188"><strong>3707</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-189"><strong>adErrBoundToCommand</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-189"><strong>adErrBoundToCommand</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p115">不能更改将 <strong>Command</strong> 对象作为源的 <strong>Recordset</strong> 对象的 <strong>ActiveConnection</strong> 属性。应用程序试图将新的 <strong>Connection</strong> 对象分配给将 <strong>Command</strong> 对象作为源的 <strong>Recordset</strong> 。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p115">The <strong>ActiveConnection</strong> property of a <strong>Recordset</strong> object, which has a <strong>Command</strong> object as its source, cannot be changed. The application attempted to assign a new <strong>Connection</strong> object to a <strong>Recordset</strong> that has a <strong>Command</strong> object as its source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-192"><strong>3708</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-192"><strong>3708</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-193"><strong>adErrInvalidParamInfo</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-193"><strong>adErrInvalidParamInfo</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p116">没有正确定义 <strong>Parameter</strong> 对象。提供的信息不一致或不完整。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p116"><strong>Parameter</strong> object is improperly defined. Inconsistent or incomplete information was provided.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-196"><strong>3709</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-196"><strong>3709</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-197"><strong>adErrInvalidConnection</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-197"><strong>adErrInvalidConnection</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p117">该连接无法用于执行此操作。它已关闭或在此上下文中无效。</span><span class="sxs-lookup"><span data-stu-id="7e442-p117">The connection cannot be used to perform this operation. It is either closed or invalid in this context.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-200"><strong>3710</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-200"><strong>3710</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-201"><strong>adErrNotReentrant</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-201"><strong>adErrNotReentrant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p118">在处理事件的过程中，无法执行操作。不能在导致事件再次触发的事件处理程序中执行操作。例如，不应该从 <strong>WillMove</strong> 事件处理程序中调用 navigation 方法。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p118">Operation cannot be performed while processing event. An operation cannot be performed within an event handler that causes the event to fire again. For example, navigation methods should not be called from within a <strong>WillMove</strong> event handler.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-205"><strong>3711</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-205"><strong>3711</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-206"><strong>adErrStillExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-206"><strong>adErrStillExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-207">在异步执行时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="7e442-207">Operation cannot be performed while executing asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-208"><strong>3712</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-208"><strong>3712</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-209"><strong>adErrOperationCancelled</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-209"><strong>adErrOperationCancelled</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p119">用户已取消操作。应用程序已调用了 <strong>CancelUpdate</strong> 或 <strong>CancelBatch</strong> 方法，当前操作已被取消。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p119">Operation has been canceled by the user. The application has called the <strong>CancelUpdate</strong> or <strong>CancelBatch</strong> method and the current operation has been canceled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-212"><strong>3713</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-212"><strong>3713</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-213"><strong>adErrStillConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-213"><strong>adErrStillConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-214">异步连接时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="7e442-214">Operation cannot be performed while connecting asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-215"><strong>3714</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-215"><strong>3714</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-216"><strong>adErrInvalidTransaction</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-216"><strong>adErrInvalidTransaction</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-217">协调事务无效或未开始。</span><span class="sxs-lookup"><span data-stu-id="7e442-217">Coordinating transaction is invalid or has not started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-218"><strong>3715</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-218"><strong>3715</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-219"><strong>adErrNotExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-219"><strong>adErrNotExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-220">没有执行时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="7e442-220">Operation cannot be performed while not executing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-221"><strong>3716</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-221"><strong>3716</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-222"><strong>adErrUnsafeOperation</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-222"><strong>adErrUnsafeOperation</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-223">此计算机上的安全设置禁止访问其他域上的数据源。</span><span class="sxs-lookup"><span data-stu-id="7e442-223">Safety settings on this computer prohibit accessing a data source on another domain.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-224"><strong>3717</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-224"><strong>3717</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-225"><strong>adWrnSecurityDialog</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-225"><strong>adWrnSecurityDialog</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p120">仅供内部使用。不要使用。（为了完整性而包括此项。此错误不应出现在您的代码中。）</span><span class="sxs-lookup"><span data-stu-id="7e442-p120">For internal use only. Don't use. (Entry was included for the sake of completeness. This error should not appear in your code.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-230"><strong>3718</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-230"><strong>3718</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-231"><strong>adWrnSecurityDialogHeader</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-231"><strong>adWrnSecurityDialogHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p121">仅供内部使用。不要使用。（为了完整性而包括此项。此错误不应出现在您的代码中。）</span><span class="sxs-lookup"><span data-stu-id="7e442-p121">For internal use only. Don't use. (Entry included for the sake of completeness. This error should not appear in your code.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-236"><strong>3719</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-236"><strong>3719</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-237"><strong>adErrIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-237"><strong>adErrIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p122">数据值与字段的完整性约束冲突。 <strong>Field</strong> 的新值会导致重复键。构成两条记录之间关系的一方的值可能无法更新。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p122">Data value conflicts with the integrity constraints of the field. A new value for a <strong>Field</strong> would cause a duplicate key. A value that forms one side of a relationship between two records might not be updatable.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-241"><strong>3720</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-241"><strong>3720</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-242"><strong>adErrPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-242"><strong>adErrPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p123">权限不足，无法写入字段。在连接字符串中指定的用户没有适当的权限写入 <strong>字段</strong> 。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p123">Insufficient permission prevents writing to the field. The user named in the connection string does not have the proper permissions to write to a <strong>Field</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-245"><strong>3721</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-245"><strong>3721</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-246"><strong>adErrDataOverflow</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-246"><strong>adErrDataOverflow</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p124">数据值过大，无法以字段数据类型表示。为要使用的字段指定的数值过大。例如，将长整型值赋值给短整型字段。</span><span class="sxs-lookup"><span data-stu-id="7e442-p124">Data value is too large to be represented by the field data type. A numeric value that is too large for the intended field was assigned. For example, a long integer value was assigned to a short integer field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-250"><strong>3722</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-250"><strong>3722</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-251"><strong>adErrSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-251"><strong>adErrSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p125">数据值与数据类型或字段的约束冲突。数据存储区具有不同于 <strong>Field</strong> 值的有效性约束。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p125">Data value conflicts with the data type or constraints of the field. The data store has validation constraints that differ from the <strong>Field</strong> value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-254"><strong>3723</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-254"><strong>3723</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-255"><strong>adErrSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-255"><strong>adErrSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-256">转换失败，原因是数据值有符号，而提供程序所使用的字段数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="7e442-256">Conversion failed because the data value was signed and the field data type used by the provider was unsigned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-257"><strong>3724</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-257"><strong>3724</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-258"><strong>adErrCantConvertvalue</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-258"><strong>adErrCantConvertvalue</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p126">由于符号不匹配或数据溢出以外的其他原因，数据值无法转换。例如，转换会截断数据。</span><span class="sxs-lookup"><span data-stu-id="7e442-p126">Data value cannot be converted for reasons other than sign mismatch or data overflow. For example, conversion would have truncated data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-261"><strong>3725</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-261"><strong>3725</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-262"><strong>adErrCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-262"><strong>adErrCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-263">因为字段数据类型未知，或提供程序没有足够的资源执行该操作，无法设置或检索数据值。</span><span class="sxs-lookup"><span data-stu-id="7e442-263">Data value cannot be set or retrieved because the field data type was unknown, or the provider had insufficient resources to perform the operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-264"><strong>3726</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-264"><strong>3726</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-265"><strong>adErrColumnNotOnThisRow</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-265"><strong>adErrColumnNotOnThisRow</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p127">记录不包含此字段。指定的字段名称不正确，或所引用字段不是当前记录的 <strong>Fields</strong> 集合中的字段。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p127">Record does not contain this field. An incorrect field name was specified or a field not in the <strong>Fields</strong> collection of the current record was referenced.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-268"><strong>3727</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-268"><strong>3727</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-269"><strong>adErrURLDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-269"><strong>adErrURLDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-270">源 URL 或目标 URL 的父级不存在。</span><span class="sxs-lookup"><span data-stu-id="7e442-270">Either the source URL or the parent of the destination URL does not exist.</span></span> <span data-ttu-id="7e442-271">源或目标 URL 中没有发生打字错误。</span><span class="sxs-lookup"><span data-stu-id="7e442-271">There is a typographical error in either the source or destination URL.</span></span> <span data-ttu-id="7e442-272">您可能必须https://mysite/photo/myphoto.jpg时，可能键入了https://mysite/photos/myphoto.jpg相反。</span><span class="sxs-lookup"><span data-stu-id="7e442-272">You might have https://mysite/photo/myphoto.jpg when you should actually have https://mysite/photos/myphoto.jpg instead.</span></span> <span data-ttu-id="7e442-273">在父 URL （在此情况下，而不是<em>照片</em><em>照片</em>） 发生打字错误已导致错误。</span><span class="sxs-lookup"><span data-stu-id="7e442-273">The typographical error in the parent URL (in this case, <em>photo</em> instead of <em>photos</em>) has caused the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-274"><strong>3728</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-274"><strong>3728</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-275"><strong>adErrTreePermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-275"><strong>adErrTreePermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p129">权限不足，无法访问树或子树。连接字符串中指定的用户没有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="7e442-p129">Permissions are insufficient to access tree or subtree. The user named in the connection string does not have the appropriate permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-278"><strong>3729</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-278"><strong>3729</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-279"><strong>adErrInvalidURL</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-279"><strong>adErrInvalidURL</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p130">URL 包含无效字符。请确保键入的 URL 正确。URL 遵循注册到当前提供程序的架构（例如，为 http 注册了 Internet Publishing Provider）。</span><span class="sxs-lookup"><span data-stu-id="7e442-p130">URL contains invalid characters. Make sure the URL is typed correctly. The URL follows the scheme registered to the current provider (for example, Internet Publishing Provider is registered for http).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-283"><strong>3730</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-283"><strong>3730</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-284"><strong>adErrResourceLocked</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-284"><strong>adErrResourceLocked</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p131">由指定的 URL 表示的对象被一个或多个其他进程锁定。请等待该进程完成，然后重试该操作。试图访问的对象已被其他用户或应用程序中的其他进程锁定。在多用户环境中，很可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="7e442-p131">Object represented by the specified URL is locked by one or more other processes. Wait until the process has finished and attempt the operation again. The object you are trying to access has been locked by another user or by another process in your application. This is most likely to arise in a multi-user environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-289"><strong>3731</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-289"><strong>3731</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-290"><strong>adErrResourceExists</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-290"><strong>adErrResourceExists</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p132">无法执行复制操作。由目标 URL 命名的对象已经存在。指定 <strong>adCopyOverwrite</strong> 替换该对象。如果在复制目录中的文件时不指定 <strong>adCopyOverwrite</strong> ，则在试图复制已存在于目标位置的项时，复制会失败。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p132">Copy operation cannot be performed. Object named by destination URL already exists. Specify <strong>adCopyOverwrite</strong> to replace the object. If you do not specify <strong>adCopyOverwrite</strong> when copying the files in a directory, the copy fails when you try to copy an item that already exists in the destination location.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-295"><strong>3732</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-295"><strong>3732</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-296"><strong>adErrCannotComplete</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-296"><strong>adErrCannotComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p133">服务器无法完成该操作。这可能是由于服务器忙于其他操作，或者服务器资源不足。</span><span class="sxs-lookup"><span data-stu-id="7e442-p133">The server cannot complete the operation. This might be because the server is busy with other operations or it might be low on resources.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-299"><strong>3733</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-299"><strong>3733</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-300"><strong>adErrVolumeNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-300"><strong>adErrVolumeNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p134">提供程序找不到 URL 指定的存储设备。请确保键入的 URL 正确。存储设备的 URL 可能不正确，但其他原因也可能引起此错误。设备可能处于脱机状态，或者大量的网络流量可能会阻止建立连接。</span><span class="sxs-lookup"><span data-stu-id="7e442-p134">Provider cannot locate the storage device indicated by the URL. Make sure the URL is typed correctly. The URL of the storage device might be incorrect, but this error can occur for other reasons. The device might be offline or a large volume of network traffic might prevent the connection from being made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-305"><strong>3734</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-305"><strong>3734</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-306"><strong>adErrOutOfSpace</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-306"><strong>adErrOutOfSpace</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p135">无法执行操作。提供程序无法获取足够的存储空间。RAM 或硬盘空间不足，无法满足服务器上临时文件的需求。</span><span class="sxs-lookup"><span data-stu-id="7e442-p135">Operation cannot be performed. Provider cannot obtain enough storage space. There might not be enough RAM or hard-drive space for temporary files on the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-310"><strong>3735</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-310"><strong>3735</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-311"><strong>adErrResourceOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-311"><strong>adErrResourceOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-312">源 URL 或目标 URL 在当前记录的范围之外。</span><span class="sxs-lookup"><span data-stu-id="7e442-312">Source or destination URL is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-313"><strong>3736</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-313"><strong>3736</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-314"><strong>adErrUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-314"><strong>adErrUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p136">操作未能完成，状态不可用。可能是字段不可用或未尝试任何操作。其他用户可能已经更改或删除了您试图访问的字段。</span><span class="sxs-lookup"><span data-stu-id="7e442-p136">Operation failed to complete and the status is unavailable. The field may be unavailable or the operation was not attempted. Another user might have changed or deleted the field you are trying to access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-318"><strong>3737</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-318"><strong>3737</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-319"><strong>adErrURLNamedRowDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-319"><strong>adErrURLNamedRowDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p137">此 URL 指定的记录不存在。在试图使用 <strong>Record</strong> 对象打开文件时，文件名或文件路径拼写错误。  </span><span class="sxs-lookup"><span data-stu-id="7e442-p137">Record named by this URL does not exist. While attempting to open a file using a <strong>Record</strong> object, either the file name or the path to the file was misspelled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-322"><strong>3738</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-322"><strong>3738</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-323"><strong>adErrDelResOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-323"><strong>adErrDelResOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-324">要删除的对象的 URL 位于当前记录的范围之外。</span><span class="sxs-lookup"><span data-stu-id="7e442-324">The URL of the object to be deleted is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-325"><strong>3747</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-325"><strong>3747</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-326"><strong>adErrCatalogNotSet</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-326"><strong>adErrCatalogNotSet</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-327">操作需要一个有效的 <strong>ParentCatalog</strong> 。</span><span class="sxs-lookup"><span data-stu-id="7e442-327">Operation requires a valid <strong>ParentCatalog</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-328"><strong>3748</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-328"><strong>3748</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-329"><strong>adErrCantChangeConnection</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-329"><strong>adErrCantChangeConnection</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p138">连接被拒绝。所请求的新连接与已使用的连接具有不同的特征。</span><span class="sxs-lookup"><span data-stu-id="7e442-p138">Connection was denied. The new connection you requested has different characteristics than the one already in use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-332"><strong>3749</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-332"><strong>3749</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-333"><strong>adErrFieldsUpdateFailed</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-333"><strong>adErrFieldsUpdateFailed</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-334">字段更新失败。</span><span class="sxs-lookup"><span data-stu-id="7e442-334">Fields update failed.</span></span> <span data-ttu-id="7e442-335">有关详细信息，请检查单个 field 对象的<strong>Status</strong>属性。</span><span class="sxs-lookup"><span data-stu-id="7e442-335">For further information, examine the <strong>Status</strong> property of individual field objects.</span></span> <span data-ttu-id="7e442-336">两种情况下会出现此错误： 时更改在更改或添加记录到数据库; 过程中的<strong>Field</strong>对象的值和时更改<strong>Field</strong>对象本身的属性。</span><span class="sxs-lookup"><span data-stu-id="7e442-336">This error can occur in two situations: when changing a <strong>Field</strong> object's value in the process of changing or adding a record to the database; and when changing the properties of the <strong>Field</strong> object itself.</span></span> <span data-ttu-id="7e442-337">由于问题中当前记录的字段的一个失败的<strong>Record</strong>或<strong>Recordset</strong>的更新。</span><span class="sxs-lookup"><span data-stu-id="7e442-337">The <strong>Record</strong> or <strong>Recordset</strong> update failed due to a problem with one of the fields in the current record.</span></span> <span data-ttu-id="7e442-338">枚举的<strong>字段</strong>集合，并检查每个字段，以确定问题的原因的<strong>状态</strong>属性。</span><span class="sxs-lookup"><span data-stu-id="7e442-338">Enumerate the <strong>Fields</strong> collection and check the <strong>Status</strong> property of each field to determine the cause of the problem.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e442-339"><strong>3750</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-339"><strong>3750</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-340"><strong>adErrDenyNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-340"><strong>adErrDenyNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p140">提供程序不支持共享限制。试图限制文件共享，但您的提供程序不支持该概念。</span><span class="sxs-lookup"><span data-stu-id="7e442-p140">Provider does not support sharing restrictions. An attempt was made to restrict file sharing and your provider does not support the concept.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e442-343"><strong>3751</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-343"><strong>3751</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-344"><strong>adErrDenyTypeNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="7e442-344"><strong>adErrDenyTypeNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="7e442-p141">提供程序不支持所请求的共享限制类型。试图建立特殊类型的文件共享限制，您的提供程序不支持该限制。请参阅提供程序的文档以确定所支持的文件共享限制。</span><span class="sxs-lookup"><span data-stu-id="7e442-p141">Provider does not support the requested kind of sharing restriction. An attempt was made to establish a particular type of file-sharing restriction that is not supported by your provider. See the provider's documentation to determine what file-sharing restrictions are supported.</span></span></p></td>
</tr>
</tbody>
</table>

