---
title: 下载层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0400ba-8530-e6ac-5de8-a62aeec5e10a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9c334bc86bdff4abb2762642a37e3f0933a0b29
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589026"
---
# <a name="download-hierarchy-state"></a><span data-ttu-id="c8f78-103">下载层次结构状态</span><span class="sxs-lookup"><span data-stu-id="c8f78-103">Download Hierarchy State</span></span>

  
  
<span data-ttu-id="c8f78-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8f78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="c8f78-105">本主题介绍的复制状态机下载层次结构状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="c8f78-105">This topic describes what happens during the download hierarchy state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="c8f78-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="c8f78-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c8f78-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="c8f78-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="c8f78-108">**LR_SYNC_DOWNLOAD_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="c8f78-108">**LR_SYNC_DOWNLOAD_HIERARCHY**</span></span> <br/> |
|<span data-ttu-id="c8f78-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="c8f78-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="c8f78-110">**[DNHIER](dnhier.md)**</span><span class="sxs-lookup"><span data-stu-id="c8f78-110">**[DNHIER](dnhier.md)**</span></span> <br/> |
|<span data-ttu-id="c8f78-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="c8f78-111">From this state:</span></span>  <br/> |[<span data-ttu-id="c8f78-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="c8f78-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="c8f78-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="c8f78-113">To this state:</span></span>  <br/> |<span data-ttu-id="c8f78-114">同步状态</span><span class="sxs-lookup"><span data-stu-id="c8f78-114">Synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c8f78-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="c8f78-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="c8f78-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="c8f78-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="c8f78-117">说明</span><span class="sxs-lookup"><span data-stu-id="c8f78-117">Description</span></span>

<span data-ttu-id="c8f78-118">此状态启动到本地存储从服务器下载文件夹树层次结构。</span><span class="sxs-lookup"><span data-stu-id="c8f78-118">This state initiates downloading a tree hierarchy of folders from a server to the local store.</span></span> 
  
<span data-ttu-id="c8f78-119">Outlook 初始化的层次结构的指针具有关联的**DNHIER**数据结构。</span><span class="sxs-lookup"><span data-stu-id="c8f78-119">Outlook initializes the associated **DNHIER** data structure with a pointer to the hierarchy.</span></span> <span data-ttu-id="c8f78-120">客户端下载层次结构，并将本地存储插入新的文件夹或文件夹的修改。</span><span class="sxs-lookup"><span data-stu-id="c8f78-120">The client downloads the hierarchy, and inserts new folders or modifications to folders in the local store.</span></span> <span data-ttu-id="c8f78-121">下载过程采用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="c8f78-121">The download process adopts Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="c8f78-122">ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c8f78-122">For more information on ICS, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
<span data-ttu-id="c8f78-123">此状态结束时，本地存储返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="c8f78-123">When this state ends, the local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8f78-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8f78-124">See also</span></span>



[<span data-ttu-id="c8f78-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="c8f78-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="c8f78-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="c8f78-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="c8f78-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="c8f78-127">SYNCSTATE</span></span>](syncstate.md)

