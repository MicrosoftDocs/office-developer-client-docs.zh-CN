---
title: 按需发送或接收邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 479404c5-4926-402a-aa12-75dd23276d75
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15b9c8c5a56b6f37464d2469bd1d7b3e24596502
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356474"
---
# <a name="sending-or-receiving-a-message-on-demand"></a><span data-ttu-id="1b105-103">按需发送或接收邮件</span><span class="sxs-lookup"><span data-stu-id="1b105-103">Sending or receiving a message on demand</span></span>
  
<span data-ttu-id="1b105-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b105-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b105-105">客户端通常依赖 mapi 子系统 (mapi 后台处理程序和服务提供程序) 来处理邮件传输和接收的时间。</span><span class="sxs-lookup"><span data-stu-id="1b105-105">Clients typically rely on the MAPI subsystem — the MAPI spooler and the service providers — to handle the timing of message transmission and reception.</span></span> <span data-ttu-id="1b105-106">但是, 可以使用 MAPI 后台处理程序或传输提供程序的 status 对象来更改此计时。</span><span class="sxs-lookup"><span data-stu-id="1b105-106">However, you can alter this timing by using the status object of either the MAPI spooler or a transport provider.</span></span>
  
<span data-ttu-id="1b105-107">[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法从一个或多个传输提供程序的传入或传出队列中删除所有邮件。</span><span class="sxs-lookup"><span data-stu-id="1b105-107">The [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method removes all messages from one or more transport provider's incoming or outgoing queues.</span></span> <span data-ttu-id="1b105-108">以下过程介绍了两种用于按需发送或接收邮件的技术。</span><span class="sxs-lookup"><span data-stu-id="1b105-108">The following procedures describe two techniques for sending or receiving messages on demand.</span></span> <span data-ttu-id="1b105-109">第一个过程使用 MAPI 后台处理程序的状态对象刷新配置文件中的每个传输提供程序的队列;第二个过程刷新单个传输提供程序的队列。</span><span class="sxs-lookup"><span data-stu-id="1b105-109">The first procedure uses the MAPI spooler's status object to flush the queues of every transport provider in the profile; the second procedure flushes the queue of a single transport provider.</span></span> 
  
### <a name="to-flush-all-incoming-or-outgoing-queues-in-a-single-operation"></a><span data-ttu-id="1b105-110">在单个操作中刷新所有传入或传出队列</span><span class="sxs-lookup"><span data-stu-id="1b105-110">To flush all incoming or outgoing queues in a single operation</span></span>
  
1. <span data-ttu-id="1b105-111">调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="1b105-111">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="1b105-112">调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法来限制将列设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="1b105-112">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="1b105-113">使用[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 以将**PR_RESOURCE_TYPE**与 MAPI_SPOOLER 相匹配。</span><span class="sxs-lookup"><span data-stu-id="1b105-113">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_RESOURCE_TYPE** with MAPI_SPOOLER.</span></span> 
    
4. <span data-ttu-id="1b105-114">调用[HrQueryAllRows](hrqueryallrows.md), 在**SPropertyRestriction**结构中传递, 以检索代表 MAPI 后台处理程序状态的行。</span><span class="sxs-lookup"><span data-stu-id="1b105-114">Call [HrQueryAllRows](hrqueryallrows.md), passing in the **SPropertyRestriction** structure, to retrieve the row that represents the status of the MAPI spooler.</span></span> 
    
5. <span data-ttu-id="1b105-115">将**PR_ENTRYID**列传递给[IMAPISession:: OpenEntry](imapisession-openentry.md)以打开 MAPI 后台处理程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="1b105-115">Pass the **PR_ENTRYID** column to [IMAPISession::OpenEntry](imapisession-openentry.md) to open the MAPI spooler's status object.</span></span> 
    
6. <span data-ttu-id="1b105-116">调用 MAPI 后台处理程序的[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)方法, 传递 FLUSH_NO_UI 标志以禁止显示用户界面, 并选择 FLUSH_DOWNLOAD 或 FLUSH_UPLOAD 标志以刷新传出或传入队列。</span><span class="sxs-lookup"><span data-stu-id="1b105-116">Call the MAPI spooler's [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method, passing the FLUSH_NO_UI flag to suppress the user interface and either the FLUSH_DOWNLOAD or FLUSH_UPLOAD flag to flush the outgoing or incoming queues.</span></span> 
    
7. <span data-ttu-id="1b105-117">释放状态对象和状态表, 以及为该表分配的[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1b105-117">Release the status object and the status table, as well as the [SRowSet](srowset.md) structure that is allocated for the table.</span></span> 
    
### <a name="to-flush-incoming-or-outgoing-queues-individually-by-transport-provider"></a><span data-ttu-id="1b105-118">通过传输提供程序单独刷新传入或传出队列</span><span class="sxs-lookup"><span data-stu-id="1b105-118">To flush incoming or outgoing queues individually by transport provider</span></span>
  
1. <span data-ttu-id="1b105-119">调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="1b105-119">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="1b105-120">调用状态表的[IMAPITable:: SetColumns](imapitable-setcolumns.md)方法以将列设置限制为**PR_ENTRYID**和**PR_RESOURCE_TYPE**。</span><span class="sxs-lookup"><span data-stu-id="1b105-120">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** and **PR_RESOURCE_TYPE**.</span></span>
    
3. <span data-ttu-id="1b105-121">使用[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 以将**PR_RESOURCE_TYPE**与 MAPI_TRANSPORT_PROVIDER 相匹配。</span><span class="sxs-lookup"><span data-stu-id="1b105-121">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_RESOURCE_TYPE** with MAPI_TRANSPORT_PROVIDER.</span></span> 
    
4. <span data-ttu-id="1b105-122">调用[HrQueryAllRows](hrqueryallrows.md), 在**SPropertyRestriction**结构中传递, 以检索传输提供程序提供的行。</span><span class="sxs-lookup"><span data-stu-id="1b105-122">Call [HrQueryAllRows](hrqueryallrows.md), passing in the **SPropertyRestriction** structure, to retrieve the rows that are supplied by transport providers.</span></span> 
    
5. <span data-ttu-id="1b105-123">对于从**HrQueryAllRows**返回的每个行:</span><span class="sxs-lookup"><span data-stu-id="1b105-123">For each row returned from **HrQueryAllRows**:</span></span>
    
    1. <span data-ttu-id="1b105-124">将**PR_ENTRYID**列传递给[IMAPISession:: OpenEntry](imapisession-openentry.md)以打开传输提供程序的状态对象。</span><span class="sxs-lookup"><span data-stu-id="1b105-124">Pass the **PR_ENTRYID** column to [IMAPISession::OpenEntry](imapisession-openentry.md) to open the transport provider's status object.</span></span> 
        
    2. <span data-ttu-id="1b105-125">检查传输状态对象是否支持**FlushQueues**方法, 方法是检查其**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性是否设置了 STATUS_FLUSH_QUEUES 标志。</span><span class="sxs-lookup"><span data-stu-id="1b105-125">Check that the transport status object supports the **FlushQueues** method by checking that its **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property has the STATUS_FLUSH_QUEUES flag set.</span></span> 
        
    3. <span data-ttu-id="1b105-126">如果支持, 请调用[IMAPIStatus:: FlushQueues](imapistatus-flushqueues.md)。</span><span class="sxs-lookup"><span data-stu-id="1b105-126">If supported, call [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md).</span></span> <span data-ttu-id="1b105-127">如果不受支持, 请调用 MAPI 后台处理程序的**IMAPIStatus:: FlushQueues**方法, 并在_lpTargetTransport_参数中传递传输条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1b105-127">If unsupported, call the MAPI spooler's **IMAPIStatus::FlushQueues** method, passing the entry identifier of the transport in the  _lpTargetTransport_ parameter.</span></span> <span data-ttu-id="1b105-128">有关访问 MAPI 后台处理程序的状态对象的说明, 请参阅前面的过程。</span><span class="sxs-lookup"><span data-stu-id="1b105-128">See the preceding procedure for instructions on accessing the MAPI spooler's status object.</span></span> <span data-ttu-id="1b105-129">设置 FLUSH_DOWNLOAD 标志以刷新传出队列或 FLUSH_UPLOAD 标志以刷新传入队列。</span><span class="sxs-lookup"><span data-stu-id="1b105-129">Set the FLUSH_DOWNLOAD flag to flush the outgoing queues or the FLUSH_UPLOAD flag to flush the incoming queues.</span></span> 
        
    4. <span data-ttu-id="1b105-130">释放状态对象和状态表, 以及为该表分配的[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1b105-130">Release the status object and the status table, as well as the [SRowSet](srowset.md) structure that is allocated for the table.</span></span> 
    
<span data-ttu-id="1b105-131">MAPI 后台处理程序将 FLUSH_NO_UI 标志视为大多数 LAN 传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="1b105-131">The MAPI spooler honors the FLUSH_NO_UI flag as do most LAN transport providers.</span></span> <span data-ttu-id="1b105-132">但是, 并不是所有传输提供者都服从此标志, 尤其是那些显式使用调制解调器和远程访问服务 (RAS) 的。</span><span class="sxs-lookup"><span data-stu-id="1b105-132">However, not all transport providers honor this flag, particularly those that use a modem explicitly and the Remote Access Service (RAS).</span></span> <span data-ttu-id="1b105-133">RAS 不允许客户端禁止显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="1b105-133">RAS was not designed to allow clients to suppress the user interface.</span></span> <span data-ttu-id="1b105-134">客户端可以进行配置, 以便它可以在不需要用户交互的情况下进行连接, 但这很困难, 需要了解客户端的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="1b105-134">It is possible for a client to be configured so that it can connect without requiring the interaction of a user, but it is difficult and requires intimate knowledge of the client's message services.</span></span>
  

