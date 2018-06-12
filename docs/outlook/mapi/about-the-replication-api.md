---
title: 有关复制 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5133045a-b1e2-7728-5cd5-6d85eb940cf9
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 50b36ee60d00e06a1f5baa8726b5f27c4a3e6ce7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774466"
---
# <a name="about-the-replication-api"></a><span data-ttu-id="31118-103">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="31118-103">About the Replication API</span></span>

  
  
<span data-ttu-id="31118-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31118-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31118-105">复制 API 提供了 MAPI 消息存储提供程序同步 Microsoft Outlook 2013 或 Microsoft Outlook 2010 之间的服务器和专用基于.pst 本地存储该提供程序创建的项目的功能。</span><span class="sxs-lookup"><span data-stu-id="31118-105">The Replication API provides the functionality for a MAPI message store provider to synchronize Microsoft Outlook 2013 or Microsoft Outlook 2010 items between a server and a private .pst-based local store that is created for that provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="31118-106">MAPI 消息存储提供程序必须实现中[有关复制状态机](about-the-replication-state-machine.md)根据说明复制 API。</span><span class="sxs-lookup"><span data-stu-id="31118-106">A MAPI message store provider must implement the Replication API according to the instructions in [About the Replication State Machine](about-the-replication-state-machine.md).</span></span> <span data-ttu-id="31118-107">提供程序必须在个人存储为本身，创建仅使用 API 和不在为其他提供程序创建的个人存储，因为个人存储为创建其他提供程序可能已经安装了各自的服务器与自己复制机制。</span><span class="sxs-lookup"><span data-stu-id="31118-107">The provider must use the API only on a personal store created for itself, and not on personal stores created for other providers, because personal stores created for other providers may have already set up their own replication mechanisms with the respective server.</span></span> <span data-ttu-id="31118-108">例如，脱机文件夹文件 (.ost) 维护与 Microsoft Exchange server 自己复制关系。</span><span class="sxs-lookup"><span data-stu-id="31118-108">For example, an offline folder file (.ost) maintains its own replication relationship with a Microsoft Exchange server.</span></span> 
  
<span data-ttu-id="31118-109">若要使用复制 API，MAPI 消息存储提供程序必须首先打开并通过调用**[NSTServiceEntry](nstserviceentry.md)** 环绕基于.pst 的本地存储区。</span><span class="sxs-lookup"><span data-stu-id="31118-109">To use the Replication API, a MAPI message store provider must first open and wrap a .pst-based local store by calling **[NSTServiceEntry](nstserviceentry.md)**.</span></span> <span data-ttu-id="31118-110">提供程序然后可以使用 API、 **[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。</span><span class="sxs-lookup"><span data-stu-id="31118-110">The provider can then use the major interfaces of the API, **[IOSTX](iostxiunknown.md)** and **[IPSTX](ipstxiunknown.md)**, to carry out replication.</span></span> <span data-ttu-id="31118-111">由查询提供**IPSTX** [IMsgStore: IMAPIProp](imsgstoreimapiprop.md)，并由**[IPSTX::GetSyncObject](ipstx-getsyncobject.md)** 提供**IOSTX** 。</span><span class="sxs-lookup"><span data-stu-id="31118-111">**IPSTX** is provided by querying on [IMsgStore : IMAPIProp](imsgstoreimapiprop.md), and **IOSTX** is provided by **[IPSTX::GetSyncObject](ipstx-getsyncobject.md)**.</span></span> 
  
## <a name="the-iostx-interface"></a><span data-ttu-id="31118-112">IOSTX 接口</span><span class="sxs-lookup"><span data-stu-id="31118-112">The IOSTX Interface</span></span>

<span data-ttu-id="31118-113">**IOSTX**接口是执行同步复制 API 中的主要接口。</span><span class="sxs-lookup"><span data-stu-id="31118-113">The **IOSTX** interface is the primary interface that performs synchronization in the Replication API.</span></span> <span data-ttu-id="31118-114">**IOSTX**移动一系列状态，通过本地存储检索中每种状态信息的本地存储中的更改以及告知本地存储的服务器上的更改。</span><span class="sxs-lookup"><span data-stu-id="31118-114">**IOSTX** moves the local store through a series of states, retrieving information in each state about changes in the local store, as well as informing the local store of changes on the server.</span></span> <span data-ttu-id="31118-115">复制 API 还指定支持的同步的许多数据结构。</span><span class="sxs-lookup"><span data-stu-id="31118-115">The Replication API also specifies many data structures that support the synchronization.</span></span> 
  
<span data-ttu-id="31118-116">存储提供程序，为此 API 的客户端使用复制 API 包装本地存储，并将更改 （如对文件夹层次结构或添加新项的更改） 对本地存储推送到服务器，并还检索移动这些状态，有关更改服务器和的信息提供给**IOSTX**接口上的信息。</span><span class="sxs-lookup"><span data-stu-id="31118-116">A store provider, as a client to this API, uses the Replication API to wrap the local store and move through these states, pushing changes on the local store (such as changes to the folder hierarchy or the addition of new items) to the server, and also retrieving information about changes on the server and providing that information to the **IOSTX** interface.</span></span> <span data-ttu-id="31118-117">**IOSTX**接口采用增量更改同步 (ICS) 提供的 Microsoft Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="31118-117">The **IOSTX** interface adopts Incremental Change Synchronization (ICS) provided by Microsoft Exchange Server.</span></span> <span data-ttu-id="31118-118">有关 ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="31118-118">For more information about ICS, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span> <span data-ttu-id="31118-119">通过**IOSTX**，客户端使用 ICS 监视和同步到层次结构或本地存储区上的内容的增量更改。</span><span class="sxs-lookup"><span data-stu-id="31118-119">Through **IOSTX**, the client uses ICS to monitor and synchronize incremental changes to the hierarchy or content on a local store.</span></span> 
  
## <a name="the-ipstx-interface"></a><span data-ttu-id="31118-120">IPSTX 接口</span><span class="sxs-lookup"><span data-stu-id="31118-120">The IPSTX Interface</span></span>

 <span data-ttu-id="31118-121">**IPSTX**和其他第五 * * IPSTX *n* * * 继承**IPSTX**的接口提供了执行复制通过**IOSTX**界面时可以使用的帮助器功能。</span><span class="sxs-lookup"><span data-stu-id="31118-121">**IPSTX** and five other **IPSTX *n* ** interfaces that inherit from **IPSTX** provide helper functionality that can be used when performing replication through the **IOSTX** interface.</span></span> <span data-ttu-id="31118-122">例如， **[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)** 可以使本地存储模拟 Outlook 协议管理器后台打印到的服务器的传出邮件。</span><span class="sxs-lookup"><span data-stu-id="31118-122">For example, **[IPSTX::EmulateSpooler](ipstx-emulatespooler.md)** allows you to make the local store emulate the Outlook Protocol Manager to spool outgoing messages to a server.</span></span> 
  
<span data-ttu-id="31118-123">在复制过程状态切换的详细信息，请参阅[有关复制状态机](about-the-replication-state-machine.md)。</span><span class="sxs-lookup"><span data-stu-id="31118-123">For more information about state transitions during replication, see [About the Replication State Machine](about-the-replication-state-machine.md).</span></span>
  
## <a name="the-replication-api"></a><span data-ttu-id="31118-124">复制 API</span><span class="sxs-lookup"><span data-stu-id="31118-124">The Replication API</span></span>

<span data-ttu-id="31118-125">复制 API 提供了以下定义、 数据类型和接口。</span><span class="sxs-lookup"><span data-stu-id="31118-125">The Replication API provides the following defintions, data types, and interfaces.</span></span> <span data-ttu-id="31118-126">示例实现的存储提供程序换行个人文件夹文件 (PST)，请参阅[有关示例自动换行 PST 存储提供程序](about-the-sample-wrapped-pst-store-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="31118-126">For a sample implementation of a store provider for wrapped Personal Folders files (PST), see [About the Sample Wrapped PST Store Provider](about-the-sample-wrapped-pst-store-provider.md).</span></span>
  
<span data-ttu-id="31118-127">定义：</span><span class="sxs-lookup"><span data-stu-id="31118-127">Definitions:</span></span>
  
- [<span data-ttu-id="31118-128">复制 API 的常量</span><span class="sxs-lookup"><span data-stu-id="31118-128">Constants for the Replication API</span></span>](mapi-constants.md)
    
<span data-ttu-id="31118-129">函数：</span><span class="sxs-lookup"><span data-stu-id="31118-129">Functions:</span></span>
  
- <span data-ttu-id="31118-130">**[NSTServiceEntry](nstserviceentry.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-130">**[NSTServiceEntry](nstserviceentry.md)**</span></span>
    
<span data-ttu-id="31118-131">数据类型：</span><span class="sxs-lookup"><span data-stu-id="31118-131">Data types:</span></span>
  
- <span data-ttu-id="31118-132">**[DNHIER](dnhier.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-132">**[DNHIER](dnhier.md)**</span></span>
    
- <span data-ttu-id="31118-133">**[DNTBL](dntbl.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-133">**[DNTBL](dntbl.md)**</span></span>
    
- <span data-ttu-id="31118-134">**[DNTBLE](dntble.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-134">**[DNTBLE](dntble.md)**</span></span>
    
- <span data-ttu-id="31118-135">**[FEID](feid.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-135">**[FEID](feid.md)**</span></span>
    
- <span data-ttu-id="31118-136">**[HDRSYNC](hdrsync.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-136">**[HDRSYNC](hdrsync.md)**</span></span>
    
- <span data-ttu-id="31118-137">**[LTID](ltid.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-137">**[LTID](ltid.md)**</span></span>
    
- <span data-ttu-id="31118-138">**[MEID](meid.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-138">**[MEID](meid.md)**</span></span>
    
- <span data-ttu-id="31118-139">**[OLFI](olfi.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-139">**[OLFI](olfi.md)**</span></span>
    
- <span data-ttu-id="31118-140">**[SKEY](skey.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-140">**[SKEY](skey.md)**</span></span>
    
- <span data-ttu-id="31118-141">**[同步](sync.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-141">**[SYNC](sync.md)**</span></span>
    
- <span data-ttu-id="31118-142">**[SYNCCONT](synccont.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-142">**[SYNCCONT](synccont.md)**</span></span>
    
- <span data-ttu-id="31118-143">**[SYNCSTATE](syncstate.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-143">**[SYNCSTATE](syncstate.md)**</span></span>
    
- <span data-ttu-id="31118-144">**[UPDEL](updel.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-144">**[UPDEL](updel.md)**</span></span>
    
- <span data-ttu-id="31118-145">**[UPDELE](updele.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-145">**[UPDELE](updele.md)**</span></span>
    
- <span data-ttu-id="31118-146">**[UPFLD](upfld.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-146">**[UPFLD](upfld.md)**</span></span>
    
- <span data-ttu-id="31118-147">**[UPHIER](uphier.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-147">**[UPHIER](uphier.md)**</span></span>
    
- <span data-ttu-id="31118-148">**[UPMOV](upmov.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-148">**[UPMOV](upmov.md)**</span></span>
    
- <span data-ttu-id="31118-149">**[UPMSG](upmsg.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-149">**[UPMSG](upmsg.md)**</span></span>
    
- <span data-ttu-id="31118-150">**[UPREAD](upread.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-150">**[UPREAD](upread.md)**</span></span>
    
- <span data-ttu-id="31118-151">**[UPREADE](upreade.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-151">**[UPREADE](upreade.md)**</span></span>
    
- <span data-ttu-id="31118-152">**[UPTBL](uptbl.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-152">**[UPTBL](uptbl.md)**</span></span>
    
- <span data-ttu-id="31118-153">**[UPTBLE](uptble.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-153">**[UPTBLE](uptble.md)**</span></span>
    
<span data-ttu-id="31118-154">接口：</span><span class="sxs-lookup"><span data-stu-id="31118-154">Interfaces:</span></span>
  
- <span data-ttu-id="31118-155">**[IOSTX](iostxiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-155">**[IOSTX](iostxiunknown.md)**</span></span>
    
- <span data-ttu-id="31118-156">**[IPSTX](ipstxiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-156">**[IPSTX](ipstxiunknown.md)**</span></span>
    
- <span data-ttu-id="31118-157">**[IPSTX2](ipstx2ipstx.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-157">**[IPSTX2](ipstx2ipstx.md)**</span></span>
    
- <span data-ttu-id="31118-158">**[IPSTX3](ipstx3ipstx2.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-158">**[IPSTX3](ipstx3ipstx2.md)**</span></span>
    
- <span data-ttu-id="31118-159">**[IPSTX4](ipstx4ipstx3.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-159">**[IPSTX4](ipstx4ipstx3.md)**</span></span>
    
- <span data-ttu-id="31118-160">**[IPSTX5](ipstx5ipstx4.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-160">**[IPSTX5](ipstx5ipstx4.md)**</span></span>
    
- <span data-ttu-id="31118-161">**[IPSTX6](ipstx6ipstx5.md)**</span><span class="sxs-lookup"><span data-stu-id="31118-161">**[IPSTX6](ipstx6ipstx5.md)**</span></span>
    

