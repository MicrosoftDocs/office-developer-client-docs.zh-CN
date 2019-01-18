---
title: 批模式 （访问桌面数据库参考 （英文）
TOCTitle: Batch mode
ms:assetid: b73921f6-5a12-9b26-ea65-99b32dd763f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249883(v=office.15)
ms:contentKeyID: 48547294
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ac5f14d035a4e11cce67f01ca6636f3ebd39963e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717809"
---
# <a name="batch-mode"></a><span data-ttu-id="1e3be-102">批处理模式</span><span class="sxs-lookup"><span data-stu-id="1e3be-102">Batch mode</span></span>

<span data-ttu-id="1e3be-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1e3be-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1e3be-p101">当 **LockType** 属性设置为 **adLockBatchOptimistic** ，并且提供程序支持批更新时，批模式有效。根据游标位置，某些锁定类型设置不可用。例如，当 **CursorLocation** 设置为 **adUseClient** 时，保守式锁定类型不可用。反过来，当游标位置位于服务器时，提供程序可能不支持批开放式锁定。仅应将批更新用于键集游标或静态游标。</span><span class="sxs-lookup"><span data-stu-id="1e3be-p101">Batch mode is in effect when the **LockType** property is set to **adLockBatchOptimistic** and batch updating is supported by the provider. Certain lock type settings are not available depending on cursor location. For instance, a pessimistic lock type is not available when the **CursorLocation** is set to **adUseClient**. Conversely, a provider may not support a batch optimistic lock when the cursor location is on the server. You should use batch updating with either a keyset or static cursor only.</span></span>

<span data-ttu-id="1e3be-p102">**UpdateBatch** 方法用于将复制缓冲区中保存的 **Recordset** 更改发送到服务器以更新数据源。在以下部分中，我们将以批模式打开一个 **Recordset** ，对复制缓冲区进行更改，然后调用 **UpdateBatch** 将更改发送到数据源。</span><span class="sxs-lookup"><span data-stu-id="1e3be-p102">The **UpdateBatch** method is used to send **Recordset** changes held in the copy buffer to the server to update the data source. In the following section, we will open a **Recordset** in batch mode, make changes to the copy buffer, and then send our changes to the data source using a call to **UpdateBatch**.</span></span>

<span data-ttu-id="1e3be-111">本节包括下列主题：</span><span class="sxs-lookup"><span data-stu-id="1e3be-111">This section includes the following topics:</span></span>

- [<span data-ttu-id="1e3be-112">发送更新：UpdateBatch</span><span class="sxs-lookup"><span data-stu-id="1e3be-112">Sending the updates: UpdateBatch</span></span>](sending-the-updates-updatebatch.md)
- [<span data-ttu-id="1e3be-113">筛选出更新后的记录</span><span class="sxs-lookup"><span data-stu-id="1e3be-113">Filtering for updated records</span></span>](filtering-for-updated-records.md)
- [<span data-ttu-id="1e3be-114">处理失败的更新</span><span class="sxs-lookup"><span data-stu-id="1e3be-114">Dealing with failed updates</span></span>](dealing-with-failed-updates.md)
- [<span data-ttu-id="1e3be-115">检测和解决冲突</span><span class="sxs-lookup"><span data-stu-id="1e3be-115">Detecting and resolving conflicts</span></span>](detecting-and-resolving-conflicts.md)
- [<span data-ttu-id="1e3be-116">断开并重新连接记录集</span><span class="sxs-lookup"><span data-stu-id="1e3be-116">Disconnecting and reconnecting the Recordset</span></span>](disconnecting-and-reconnecting-the-recordset.md)
- [<span data-ttu-id="1e3be-117">更新加入结果： Unique Table</span><span class="sxs-lookup"><span data-stu-id="1e3be-117">Updating JOINed results: Unique Table</span></span>](updating-joined-results-unique-table.md)

