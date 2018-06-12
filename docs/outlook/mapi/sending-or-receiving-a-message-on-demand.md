---
title: 发送或接收按需型消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 479404c5-4926-402a-aa12-75dd23276d75
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ece5340497f83862b711f076c8c6346e14ec9355
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778744"
---
# <a name="sending-or-receiving-a-message-on-demand"></a><span data-ttu-id="269da-103">发送或接收按需型消息</span><span class="sxs-lookup"><span data-stu-id="269da-103">Sending or receiving a message on demand</span></span>
  
<span data-ttu-id="269da-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="269da-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="269da-105">客户端通常依靠 MAPI 子系统 — MAPI 后台处理程序和服务提供程序 — 处理的邮件传输和接收的时间。</span><span class="sxs-lookup"><span data-stu-id="269da-105">Clients typically rely on the MAPI subsystem — the MAPI spooler and the service providers — to handle the timing of message transmission and reception.</span></span> <span data-ttu-id="269da-106">但是，您可以通过使用 MAPI 后台处理程序或传输提供程序的状态对象修改此计时。</span><span class="sxs-lookup"><span data-stu-id="269da-106">However, you can alter this timing by using the status object of either the MAPI spooler or a transport provider.</span></span>
  
<span data-ttu-id="269da-107">[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法从一个或多个传输提供程序的传入或传出队列中删除所有邮件。</span><span class="sxs-lookup"><span data-stu-id="269da-107">The [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method removes all messages from one or more transport provider's incoming or outgoing queues.</span></span> <span data-ttu-id="269da-108">下面的过程介绍两种技术可以发送或接收的消息的需求。</span><span class="sxs-lookup"><span data-stu-id="269da-108">The following procedures describe two techniques for sending or receiving messages on demand.</span></span> <span data-ttu-id="269da-109">第一个过程使用 MAPI 后台处理程序的状态对象来刷新的配置文件; 中每个传输提供程序的队列第二个过程刷新单个传输提供程序的队列。</span><span class="sxs-lookup"><span data-stu-id="269da-109">The first procedure uses the MAPI spooler's status object to flush the queues of every transport provider in the profile; the second procedure flushes the queue of a single transport provider.</span></span> 
  
### <a name="to-flush-all-incoming-or-outgoing-queues-in-a-single-operation"></a><span data-ttu-id="269da-110">刷新在单一操作中的所有传入或传出队列</span><span class="sxs-lookup"><span data-stu-id="269da-110">To flush all incoming or outgoing queues in a single operation</span></span>
  
1. <span data-ttu-id="269da-111">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。</span><span class="sxs-lookup"><span data-stu-id="269da-111">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="269da-112">调用状态表[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 的列。</span><span class="sxs-lookup"><span data-stu-id="269da-112">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) and **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)).</span></span>
    
3. <span data-ttu-id="269da-113">构建使用[SPropertyRestriction](spropertyrestriction.md)结构匹配**PR_RESOURCE_TYPE**与 MAPI_SPOOLER 属性限制。</span><span class="sxs-lookup"><span data-stu-id="269da-113">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_RESOURCE_TYPE** with MAPI_SPOOLER.</span></span> 
    
4. <span data-ttu-id="269da-114">呼叫[HrQueryAllRows](hrqueryallrows.md)，传递**SPropertyRestriction**结构中，若要检索的行代表 MAPI 后台处理程序的状态。</span><span class="sxs-lookup"><span data-stu-id="269da-114">Call [HrQueryAllRows](hrqueryallrows.md), passing in the **SPropertyRestriction** structure, to retrieve the row that represents the status of the MAPI spooler.</span></span> 
    
5. <span data-ttu-id="269da-115">传递给[IMAPISession::OpenEntry](imapisession-openentry.md)打开 MAPI 后台处理程序的状态对象**PR_ENTRYID**列。</span><span class="sxs-lookup"><span data-stu-id="269da-115">Pass the **PR_ENTRYID** column to [IMAPISession::OpenEntry](imapisession-openentry.md) to open the MAPI spooler's status object.</span></span> 
    
6. <span data-ttu-id="269da-116">调用 MAPI 后台处理程序的[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)方法，传递 FLUSH_NO_UI 标志禁止在用户界面和 FLUSH_DOWNLOAD 或 FLUSH_UPLOAD 刷新传出或传入队列的标志。</span><span class="sxs-lookup"><span data-stu-id="269da-116">Call the MAPI spooler's [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md) method, passing the FLUSH_NO_UI flag to suppress the user interface and either the FLUSH_DOWNLOAD or FLUSH_UPLOAD flag to flush the outgoing or incoming queues.</span></span> 
    
7. <span data-ttu-id="269da-117">释放状态对象和状态表，以及分配表的[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="269da-117">Release the status object and the status table, as well as the [SRowSet](srowset.md) structure that is allocated for the table.</span></span> 
    
### <a name="to-flush-incoming-or-outgoing-queues-individually-by-transport-provider"></a><span data-ttu-id="269da-118">刷新分别由传输提供程序的传入或传出队列</span><span class="sxs-lookup"><span data-stu-id="269da-118">To flush incoming or outgoing queues individually by transport provider</span></span>
  
1. <span data-ttu-id="269da-119">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。</span><span class="sxs-lookup"><span data-stu-id="269da-119">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="269da-120">调用状态表[IMAPITable::SetColumns](imapitable-setcolumns.md)方法，以限制设置为**PR_ENTRYID**和**PR_RESOURCE_TYPE**的列。</span><span class="sxs-lookup"><span data-stu-id="269da-120">Call the status table's [IMAPITable::SetColumns](imapitable-setcolumns.md) method to limit the column set to **PR_ENTRYID** and **PR_RESOURCE_TYPE**.</span></span>
    
3. <span data-ttu-id="269da-121">构建使用[SPropertyRestriction](spropertyrestriction.md)结构匹配**PR_RESOURCE_TYPE**与 MAPI_TRANSPORT_PROVIDER 属性限制。</span><span class="sxs-lookup"><span data-stu-id="269da-121">Build a property restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_RESOURCE_TYPE** with MAPI_TRANSPORT_PROVIDER.</span></span> 
    
4. <span data-ttu-id="269da-122">调用[HrQueryAllRows](hrqueryallrows.md)，传递在**SPropertyRestriction**结构中，以检索由传输提供程序提供的行。</span><span class="sxs-lookup"><span data-stu-id="269da-122">Call [HrQueryAllRows](hrqueryallrows.md), passing in the **SPropertyRestriction** structure, to retrieve the rows that are supplied by transport providers.</span></span> 
    
5. <span data-ttu-id="269da-123">对于每个行从**HrQueryAllRows**返回：</span><span class="sxs-lookup"><span data-stu-id="269da-123">For each row returned from **HrQueryAllRows**:</span></span>
    
    1. <span data-ttu-id="269da-124">传递给[IMAPISession::OpenEntry](imapisession-openentry.md)打开传输提供程序的状态对象**PR_ENTRYID**列。</span><span class="sxs-lookup"><span data-stu-id="269da-124">Pass the **PR_ENTRYID** column to [IMAPISession::OpenEntry](imapisession-openentry.md) to open the transport provider's status object.</span></span> 
        
    2. <span data-ttu-id="269da-125">检查传输状态对象支持**FlushQueues**方法，通过检查其**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性具有 STATUS_FLUSH_QUEUES 标记设置。</span><span class="sxs-lookup"><span data-stu-id="269da-125">Check that the transport status object supports the **FlushQueues** method by checking that its **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property has the STATUS_FLUSH_QUEUES flag set.</span></span> 
        
    3. <span data-ttu-id="269da-126">如果受支持，调用[IMAPIStatus::FlushQueues](imapistatus-flushqueues.md)。</span><span class="sxs-lookup"><span data-stu-id="269da-126">If supported, call [IMAPIStatus::FlushQueues](imapistatus-flushqueues.md).</span></span> <span data-ttu-id="269da-127">如果不受支持，调用 MAPI 后台处理程序的**IMAPIStatus::FlushQueues**方法，传递_lpTargetTransport_参数中的传输类型的项标识符。</span><span class="sxs-lookup"><span data-stu-id="269da-127">If unsupported, call the MAPI spooler's **IMAPIStatus::FlushQueues** method, passing the entry identifier of the transport in the  _lpTargetTransport_ parameter.</span></span> <span data-ttu-id="269da-128">有关访问 MAPI 后台处理程序的状态的对象，请参阅前面过程的说明。</span><span class="sxs-lookup"><span data-stu-id="269da-128">See the preceding procedure for instructions on accessing the MAPI spooler's status object.</span></span> <span data-ttu-id="269da-129">FLUSH_DOWNLOAD 标志以刷新传出队列或 FLUSH_UPLOAD 标志以刷新传入的队列设置。</span><span class="sxs-lookup"><span data-stu-id="269da-129">Set the FLUSH_DOWNLOAD flag to flush the outgoing queues or the FLUSH_UPLOAD flag to flush the incoming queues.</span></span> 
        
    4. <span data-ttu-id="269da-130">释放状态对象和状态表，以及分配表的[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="269da-130">Release the status object and the status table, as well as the [SRowSet](srowset.md) structure that is allocated for the table.</span></span> 
    
<span data-ttu-id="269da-131">大多数 LAN 传输提供程序一样，MAPI 后台处理程序采用 FLUSH_NO_UI 标志。</span><span class="sxs-lookup"><span data-stu-id="269da-131">The MAPI spooler honors the FLUSH_NO_UI flag as do most LAN transport providers.</span></span> <span data-ttu-id="269da-132">但是，并非所有传输提供程序都排定此标志，尤其是那些明确使用调制解调器和远程访问服务 (RAS)。</span><span class="sxs-lookup"><span data-stu-id="269da-132">However, not all transport providers honor this flag, particularly those that use a modem explicitly and the Remote Access Service (RAS).</span></span> <span data-ttu-id="269da-133">RAS 不旨在使客户端可以隐藏用户界面。</span><span class="sxs-lookup"><span data-stu-id="269da-133">RAS was not designed to allow clients to suppress the user interface.</span></span> <span data-ttu-id="269da-134">很可能为进行配置，以便其可以连接而无需交互的用户，但它是变得比较困难，需要精通客户端的消息服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="269da-134">It is possible for a client to be configured so that it can connect without requiring the interaction of a user, but it is difficult and requires intimate knowledge of the client's message services.</span></span>
  

