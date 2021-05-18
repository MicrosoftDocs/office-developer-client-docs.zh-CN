---
title: 关于复制 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5133045a-b1e2-7728-5cd5-6d85eb940cf9
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 532c01d6885e72753067b2d30bf2bd5f88207176
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329517"
---
# <a name="about-the-replication-api"></a><span data-ttu-id="175db-103">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="175db-103">About the Replication API</span></span>

  
  
<span data-ttu-id="175db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="175db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="175db-105">复制 API 为 MAPI 邮件存储提供程序提供了功能，以在服务器和为提供程序创建的基于 .pst 的专用本地存储之间同步 Microsoft Outlook 2013 或 Microsoft Outlook 2010 项。</span><span class="sxs-lookup"><span data-stu-id="175db-105">The Replication API provides the functionality for a MAPI message store provider to synchronize Microsoft Outlook 2013 or Microsoft Outlook 2010 items between a server and a private .pst-based local store that is created for that provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="175db-106">MAPI 邮件存储提供程序必须按照关于复制状态机 中的[说明实现复制 API。](about-the-replication-state-machine.md)</span><span class="sxs-lookup"><span data-stu-id="175db-106">A MAPI message store provider must implement the Replication API according to the instructions in [About the Replication State Machine](about-the-replication-state-machine.md).</span></span> <span data-ttu-id="175db-107">提供程序必须仅在为自身创建的个人存储（而非为其他提供程序创建的个人存储）上使用此 API，因为为其他提供程序创建的个人存储可能已经使用各自的服务器设置了自己的复制机制。</span><span class="sxs-lookup"><span data-stu-id="175db-107">The provider must use the API only on a personal store created for itself, and not on personal stores created for other providers, because personal stores created for other providers may have already set up their own replication mechanisms with the respective server.</span></span> <span data-ttu-id="175db-108">例如，脱机文件夹文件 (.ost) 与 Microsoft Exchange 服务器保持自己的复制关系。</span><span class="sxs-lookup"><span data-stu-id="175db-108">For example, an offline folder file (.ost) maintains its own replication relationship with a Microsoft Exchange server.</span></span> 
  
<span data-ttu-id="175db-109">若要使用复制 API，MAPI 邮件存储提供程序必须先通过调用 **[NSTServiceEntry](nstserviceentry.md)** 打开并包装基于 .pst 的本地存储。</span><span class="sxs-lookup"><span data-stu-id="175db-109">To use the Replication API, a MAPI message store provider must first open and wrap a .pst-based local store by calling **[NSTServiceEntry](nstserviceentry.md)**.</span></span> <span data-ttu-id="175db-110">然后，提供程序可以使用 **[API、IOSTX](iostxiunknown.md)** 和 **[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。</span><span class="sxs-lookup"><span data-stu-id="175db-110">The provider can then use the major interfaces of the API, **[IOSTX](iostxiunknown.md)** and **[IPSTX](ipstxiunknown.md)**, to carry out replication.</span></span> <span data-ttu-id="175db-111">**IPSTX** 通过查询 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md)提供 **，IOSTX** 由 **[IPSTX：：GetSyncObject 提供](ipstx-getsyncobject.md)**。</span><span class="sxs-lookup"><span data-stu-id="175db-111">**IPSTX** is provided by querying on [IMsgStore : IMAPIProp](imsgstoreimapiprop.md), and **IOSTX** is provided by **[IPSTX::GetSyncObject](ipstx-getsyncobject.md)**.</span></span> 
  
## <a name="the-iostx-interface"></a><span data-ttu-id="175db-112">IOSTX 接口</span><span class="sxs-lookup"><span data-stu-id="175db-112">The IOSTX Interface</span></span>

<span data-ttu-id="175db-113">**IOSTX** 接口是在复制 API 中执行同步的主接口。</span><span class="sxs-lookup"><span data-stu-id="175db-113">The **IOSTX** interface is the primary interface that performs synchronization in the Replication API.</span></span> <span data-ttu-id="175db-114">**IOSTX** 通过一系列状态移动本地存储，检索每个状态中有关本地存储更改的信息，并通知本地存储服务器上所做的更改。</span><span class="sxs-lookup"><span data-stu-id="175db-114">**IOSTX** moves the local store through a series of states, retrieving information in each state about changes in the local store, as well as informing the local store of changes on the server.</span></span> <span data-ttu-id="175db-115">复制 API 还指定许多支持同步的数据结构。</span><span class="sxs-lookup"><span data-stu-id="175db-115">The Replication API also specifies many data structures that support the synchronization.</span></span> 
  
<span data-ttu-id="175db-116">存储提供程序作为此 API 的客户端，使用复制 API 包装本地存储并移动这些状态，将更改推送到本地存储 (例如更改文件夹层次结构或向服务器添加新项) ，以及检索有关服务器上更改的信息，以及向 **IOSTX** 接口提供该信息。</span><span class="sxs-lookup"><span data-stu-id="175db-116">A store provider, as a client to this API, uses the Replication API to wrap the local store and move through these states, pushing changes on the local store (such as changes to the folder hierarchy or the addition of new items) to the server, and also retrieving information about changes on the server and providing that information to the **IOSTX** interface.</span></span> <span data-ttu-id="175db-117">**IOSTX** 接口采用由) 提供的 ICS (增量更改Microsoft Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="175db-117">The **IOSTX** interface adopts Incremental Change Synchronization (ICS) provided by Microsoft Exchange Server.</span></span> <span data-ttu-id="175db-118">有关 ICS 详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="175db-118">For more information about ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span> <span data-ttu-id="175db-119">通过 **IOSTX，** 客户端使用 ICS 监视并同步对层次结构或本地存储内容的增量更改。</span><span class="sxs-lookup"><span data-stu-id="175db-119">Through **IOSTX**, the client uses ICS to monitor and synchronize incremental changes to the hierarchy or content on a local store.</span></span> 
  
## <a name="the-ipstx-interface"></a><span data-ttu-id="175db-120">IPSTX 接口</span><span class="sxs-lookup"><span data-stu-id="175db-120">The IPSTX Interface</span></span>

 <span data-ttu-id="175db-121">**从 IPSTX** 继承的 IPSTX 和另外五个 \*\*IPSTX *n* \*\* 接口提供通过 **IOSTX** 接口执行复制时可以使用的帮助程序功能。 </span><span class="sxs-lookup"><span data-stu-id="175db-121">**IPSTX** and five other \*\*IPSTX *n* \*\* interfaces that inherit from **IPSTX** provide helper functionality that can be used when performing replication through the **IOSTX** interface.</span></span> <span data-ttu-id="175db-122">例如 **[，IPSTX：：EmulateSpooler](ipstx-emulatespooler.md)** 允许您使本地存储模拟 Outlook 协议管理器以将传出邮件后台打印到服务器。</span><span class="sxs-lookup"><span data-stu-id="175db-122">For example, **[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)** allows you to make the local store emulate the Outlook Protocol Manager to spool outgoing messages to a server.</span></span> 
  
<span data-ttu-id="175db-123">有关复制期间状态转换的信息，请参阅关于 [复制状态机](about-the-replication-state-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="175db-123">For more information about state transitions during replication, see [About the Replication State Machine](about-the-replication-state-machine.md).</span></span>
  
## <a name="the-replication-api"></a><span data-ttu-id="175db-124">复制 API</span><span class="sxs-lookup"><span data-stu-id="175db-124">The Replication API</span></span>

<span data-ttu-id="175db-125">复制 API 提供以下定义、数据类型和接口。</span><span class="sxs-lookup"><span data-stu-id="175db-125">The Replication API provides the following defintions, data types, and interfaces.</span></span> <span data-ttu-id="175db-126">有关包装的个人文件夹文件的存储提供程序的示例实现 (PST) ，请参阅关于封装 PST 存储 [提供程序示例](about-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="175db-126">For a sample implementation of a store provider for wrapped Personal Folders files (PST), see [About the Sample Wrapped PST Store Provider](about-the-sample-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="175db-127">定义：</span><span class="sxs-lookup"><span data-stu-id="175db-127">Definitions:</span></span>
  
- [<span data-ttu-id="175db-128">复制 API 的常量</span><span class="sxs-lookup"><span data-stu-id="175db-128">Constants for the Replication API</span></span>](mapi-constants.md)
    
<span data-ttu-id="175db-129">函数：</span><span class="sxs-lookup"><span data-stu-id="175db-129">Functions:</span></span>
  
- <span data-ttu-id="175db-130">**[NSTServiceEntry](nstserviceentry.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-130">**[NSTServiceEntry](nstserviceentry.md)**</span></span>
    
<span data-ttu-id="175db-131">数据类型：</span><span class="sxs-lookup"><span data-stu-id="175db-131">Data types:</span></span>
  
- <span data-ttu-id="175db-132">**[DNHIER](dnhier.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-132">**[DNHIER](dnhier.md)**</span></span>
    
- <span data-ttu-id="175db-133">**[DNTBL](dntbl.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-133">**[DNTBL](dntbl.md)**</span></span>
    
- <span data-ttu-id="175db-134">**[DNTBLE](dntble.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-134">**[DNTBLE](dntble.md)**</span></span>
    
- <span data-ttu-id="175db-135">**[FEID](feid.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-135">**[FEID](feid.md)**</span></span>
    
- <span data-ttu-id="175db-136">**[HDRSYNC](hdrsync.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-136">**[HDRSYNC](hdrsync.md)**</span></span>
    
- <span data-ttu-id="175db-137">**[LTID](ltid.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-137">**[LTID](ltid.md)**</span></span>
    
- <span data-ttu-id="175db-138">**[MEID](meid.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-138">**[MEID](meid.md)**</span></span>
    
- <span data-ttu-id="175db-139">**[OLFI](olfi.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-139">**[OLFI](olfi.md)**</span></span>
    
- <span data-ttu-id="175db-140">**[SKEY](skey.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-140">**[SKEY](skey.md)**</span></span>
    
- <span data-ttu-id="175db-141">**[SYNC](sync.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-141">**[SYNC](sync.md)**</span></span>
    
- <span data-ttu-id="175db-142">**[SYNCCONT](synccont.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-142">**[SYNCCONT](synccont.md)**</span></span>
    
- <span data-ttu-id="175db-143">**[SYNCSTATE](syncstate.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-143">**[SYNCSTATE](syncstate.md)**</span></span>
    
- <span data-ttu-id="175db-144">**[UPDEL](updel.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-144">**[UPDEL](updel.md)**</span></span>
    
- <span data-ttu-id="175db-145">**[UPDELE](updele.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-145">**[UPDELE](updele.md)**</span></span>
    
- <span data-ttu-id="175db-146">**[UPFLD](upfld.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-146">**[UPFLD](upfld.md)**</span></span>
    
- <span data-ttu-id="175db-147">**[UPHIER](uphier.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-147">**[UPHIER](uphier.md)**</span></span>
    
- <span data-ttu-id="175db-148">**[UPMOV](upmov.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-148">**[UPMOV](upmov.md)**</span></span>
    
- <span data-ttu-id="175db-149">**[UPMSG](upmsg.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-149">**[UPMSG](upmsg.md)**</span></span>
    
- <span data-ttu-id="175db-150">**[UPREAD](upread.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-150">**[UPREAD](upread.md)**</span></span>
    
- <span data-ttu-id="175db-151">**[UPREADE](upreade.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-151">**[UPREADE](upreade.md)**</span></span>
    
- <span data-ttu-id="175db-152">**[UPTBL](uptbl.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-152">**[UPTBL](uptbl.md)**</span></span>
    
- <span data-ttu-id="175db-153">**[UPTBLE](uptble.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-153">**[UPTBLE](uptble.md)**</span></span>
    
<span data-ttu-id="175db-154">接口：</span><span class="sxs-lookup"><span data-stu-id="175db-154">Interfaces:</span></span>
  
- <span data-ttu-id="175db-155">**[IOSTX](iostxiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-155">**[IOSTX](iostxiunknown.md)**</span></span>
    
- <span data-ttu-id="175db-156">**[IPSTX](ipstxiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-156">**[IPSTX](ipstxiunknown.md)**</span></span>
    
- <span data-ttu-id="175db-157">**[IPSTX2](ipstx2ipstx.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-157">**[IPSTX2](ipstx2ipstx.md)**</span></span>
    
- <span data-ttu-id="175db-158">**[IPSTX3](ipstx3ipstx2.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-158">**[IPSTX3](ipstx3ipstx2.md)**</span></span>
    
- <span data-ttu-id="175db-159">**[IPSTX4](ipstx4ipstx3.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-159">**[IPSTX4](ipstx4ipstx3.md)**</span></span>
    
- <span data-ttu-id="175db-160">**[IPSTX5](ipstx5ipstx4.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-160">**[IPSTX5](ipstx5ipstx4.md)**</span></span>
    
- <span data-ttu-id="175db-161">**[IPSTX6](ipstx6ipstx5.md)**</span><span class="sxs-lookup"><span data-stu-id="175db-161">**[IPSTX6](ipstx6ipstx5.md)**</span></span>
    

