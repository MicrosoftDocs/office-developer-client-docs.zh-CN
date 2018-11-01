---
title: ExecuteOptionEnum （访问桌面数据库参考 （英文）
TOCTitle: ExecuteOptionEnum
ms:assetid: bd6d44a3-e471-7aa0-3e65-6775334de2ff
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249915(v=office.15)
ms:contentKeyID: 48547438
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 8fa81d535a10aa0f359ba6e03b0f47048713671f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867851"
---
# <a name="executeoptionenum"></a><span data-ttu-id="5c7db-102">ExecuteOptionEnum</span><span class="sxs-lookup"><span data-stu-id="5c7db-102">ExecuteOptionEnum</span></span>

<span data-ttu-id="5c7db-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5c7db-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5c7db-104">指定提供程序应当如何执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7db-104">Specifies how a provider should execute a command.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5c7db-105">常量</span><span class="sxs-lookup"><span data-stu-id="5c7db-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="5c7db-106">值</span><span class="sxs-lookup"><span data-stu-id="5c7db-106">Value</span></span></p></th>
<th><p><span data-ttu-id="5c7db-107">说明</span><span class="sxs-lookup"><span data-stu-id="5c7db-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-108"><strong>adAsyncExecute</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-108"><strong>adAsyncExecute</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-109">0x10</span><span class="sxs-lookup"><span data-stu-id="5c7db-109">0x10</span></span></p></td>
<td><p><span data-ttu-id="5c7db-110">指示命令应异步执行。
</span><span class="sxs-lookup"><span data-stu-id="5c7db-110">Indicates that the command should execute asynchronously.</span></span> <span data-ttu-id="5c7db-111">此值不能与 <a href="commandtypeenum.md">CommandTypeEnum</a> 值 <strong>adCmdTableDirect</strong> 结合使用。</span><span class="sxs-lookup"><span data-stu-id="5c7db-111">This value cannot be combined with the <a href="commandtypeenum.md">CommandTypeEnum</a> value <strong>adCmdTableDirect</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7db-112"><strong>adAsyncFetch</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-112"><strong>adAsyncFetch</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-113">0x20</span><span class="sxs-lookup"><span data-stu-id="5c7db-113">0x20</span></span></p></td>
<td><p><span data-ttu-id="5c7db-114">指示应异步检索在 <a href="cachesize-property-ado.md">CacheSize</a> 属性中指定的初始数量之后剩余的行。</span><span class="sxs-lookup"><span data-stu-id="5c7db-114">Indicates that the remaining rows after the initial quantity specified in the <a href="cachesize-property-ado.md">CacheSize</a> property should be retrieved asynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-115"><strong>持久性</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-115"><strong>adAsyncFetchNonBlocking</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-116">0x40</span><span class="sxs-lookup"><span data-stu-id="5c7db-116">0x40</span></span></p></td>
<td><p><span data-ttu-id="5c7db-p102">指示主线程在检索期间永不阻塞。如果未检索到请求的行，当前行将自动移动到文件的末尾。
</span><span class="sxs-lookup"><span data-stu-id="5c7db-p102">Indicates that the main thread never blocks while retrieving. If the requested row has not been retrieved, the current row automatically moves to the end of the file.</span></span></p><p><span data-ttu-id="5c7db-119">如果从包含永久存储的 <strong>Recordset</strong> 的 <a href="stream-object-ado.md">Stream</a> 中打开 <a href="recordset-object-ado.md">Recordset</a>，<strong>adAsyncFetchNonBlocking</strong> 将无效；操作将同步且阻塞。</span><span class="sxs-lookup"><span data-stu-id="5c7db-119">If you open a <a href="recordset-object-ado.md">Recordset</a> from a <a href="stream-object-ado.md">Stream</a> containing a persistently stored <strong>Recordset</strong>, <strong>adAsyncFetchNonBlocking</strong> will not have an effect; the operation will be synchronous and blocking.</span></span> <span data-ttu-id="5c7db-120">当使用 <a href="commandtypeenum.md">adCmdTableDirect</a> 选项来打开 <strong>Recordset</strong> 时，<strong>adAsynchFetchNonBlocking</strong> 无效。</span><span class="sxs-lookup"><span data-stu-id="5c7db-120"><strong>adAsynchFetchNonBlocking</strong> has no effect when the <a href="commandtypeenum.md">adCmdTableDirect</a> option is used to open the <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7db-121"><strong>adExecuteNoRecords</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-121"><strong>adExecuteNoRecords</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-122">0x80</span><span class="sxs-lookup"><span data-stu-id="5c7db-122">0x80</span></span></p></td>
<td><p><span data-ttu-id="5c7db-123">指示命令文本的命令或存储的过程的不返回行 （例如，仅在插入数据的命令）。</span><span class="sxs-lookup"><span data-stu-id="5c7db-123">Indicates that the command text is a command or stored procedure that does not return rows (for example, a command that only inserts data).</span></span> <span data-ttu-id="5c7db-124">如果检索任何行时，它们是丢弃，并且不会返回。</span><span class="sxs-lookup"><span data-stu-id="5c7db-124">If any rows are retrieved, they are discarded and not returned.</span></span> <span data-ttu-id="5c7db-125"><strong>adExecuteNoRecords</strong>到<strong>Command</strong>或<strong>Connection</strong> <strong>Execute</strong>方法只能作为可选参数传递。</span><span class="sxs-lookup"><span data-stu-id="5c7db-125"><strong>adExecuteNoRecords</strong> can only be passed as an optional parameter to the <strong>Command</strong> or <strong>Connection</strong> <strong>Execute</strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-126"><strong>adExecuteStream</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-126"><strong>adExecuteStream</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-127">0x400</span><span class="sxs-lookup"><span data-stu-id="5c7db-127">0x400</span></span></p></td>
<td><p><span data-ttu-id="5c7db-128">指示命令执行的结果应作为流返回。
</span><span class="sxs-lookup"><span data-stu-id="5c7db-128">Indicates that the results of a command execution should be returned as a stream.</span></span> <span data-ttu-id="5c7db-129"><strong>adExecuteStream</strong>到<strong>命令</strong> <strong>Execute</strong>方法只能作为可选参数传递。</span><span class="sxs-lookup"><span data-stu-id="5c7db-129"><strong>adExecuteStream</strong> can only be passed as an optional parameter to the <strong>Command</strong> <strong>Execute</strong> method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7db-130"><strong>adExecuteRecord</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-130"><strong>adExecuteRecord</strong></span></span></p></td>
<td><p><br />
</p></td>
<td><p><span data-ttu-id="5c7db-131">指示 <strong>CommandText</strong> 是返回单个行（它应该作为 <strong>Record</strong> 对象返回）的命令或存储过程。</span><span class="sxs-lookup"><span data-stu-id="5c7db-131">Indicates that the <strong>CommandText</strong> is a command or stored procedure that returns a single row which should be returned as a <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-132"><strong>adOptionUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="5c7db-132"><strong>adOptionUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="5c7db-133">-1</span><span class="sxs-lookup"><span data-stu-id="5c7db-133">-1</span></span></p></td>
<td><p><span data-ttu-id="5c7db-134">指示未指定命令。</span><span class="sxs-lookup"><span data-stu-id="5c7db-134">Indicates that the command is unspecified.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="5c7db-135">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="5c7db-135">ADO/WFC equivalent</span></span>

<span data-ttu-id="5c7db-136">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="5c7db-136">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5c7db-137">常量</span><span class="sxs-lookup"><span data-stu-id="5c7db-137">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-138">AdoEnums.ExecuteOption.ASYNCEXECUTE</span><span class="sxs-lookup"><span data-stu-id="5c7db-138">AdoEnums.ExecuteOption.ASYNCEXECUTE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7db-139">AdoEnums.ExecuteOption.ASYNCFETCH</span><span class="sxs-lookup"><span data-stu-id="5c7db-139">AdoEnums.ExecuteOption.ASYNCFETCH</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-140">AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING</span><span class="sxs-lookup"><span data-stu-id="5c7db-140">AdoEnums.ExecuteOption.ASYNCFETCHNONBLOCKING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c7db-141">AdoEnums.ExecuteOption.NORECORDS</span><span class="sxs-lookup"><span data-stu-id="5c7db-141">AdoEnums.ExecuteOption.NORECORDS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c7db-142">AdoEnums.ExecuteOption.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="5c7db-142">AdoEnums.ExecuteOption.UNSPECIFIED</span></span></p></td>
</tr>
</tbody>
</table>

