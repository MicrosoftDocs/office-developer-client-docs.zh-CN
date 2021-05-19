---
title: 下载层次结构状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 8e0400ba-8530-e6ac-5de8-a62aeec5e10a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45535eef75c6fc091c02ec35b669675a51e4cf48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337007"
---
# <a name="download-hierarchy-state"></a><span data-ttu-id="3342a-103">下载层次结构状态</span><span class="sxs-lookup"><span data-stu-id="3342a-103">Download Hierarchy State</span></span>

  
  
<span data-ttu-id="3342a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3342a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="3342a-105">本主题介绍复制状态机的下载层次结构状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="3342a-105">This topic describes what happens during the download hierarchy state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="3342a-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="3342a-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3342a-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="3342a-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="3342a-108">**LR_SYNC_DOWNLOAD_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="3342a-108">**LR_SYNC_DOWNLOAD_HIERARCHY**</span></span> <br/> |
|<span data-ttu-id="3342a-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="3342a-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="3342a-110">**[DNHIER](dnhier.md)**</span><span class="sxs-lookup"><span data-stu-id="3342a-110">**[DNHIER](dnhier.md)**</span></span> <br/> |
|<span data-ttu-id="3342a-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="3342a-111">From this state:</span></span>  <br/> |[<span data-ttu-id="3342a-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="3342a-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="3342a-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="3342a-113">To this state:</span></span>  <br/> |<span data-ttu-id="3342a-114">同步状态</span><span class="sxs-lookup"><span data-stu-id="3342a-114">Synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="3342a-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="3342a-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="3342a-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="3342a-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="3342a-117">说明</span><span class="sxs-lookup"><span data-stu-id="3342a-117">Description</span></span>

<span data-ttu-id="3342a-118">此状态启动将文件夹的树层次结构从服务器下载到本地存储。</span><span class="sxs-lookup"><span data-stu-id="3342a-118">This state initiates downloading a tree hierarchy of folders from a server to the local store.</span></span> 
  
<span data-ttu-id="3342a-119">Outlook一个指向层次结构的指针初始化关联的 **DNHIER** 数据结构。</span><span class="sxs-lookup"><span data-stu-id="3342a-119">Outlook initializes the associated **DNHIER** data structure with a pointer to the hierarchy.</span></span> <span data-ttu-id="3342a-120">客户端下载层次结构，并将新文件夹或修改插入到本地存储中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3342a-120">The client downloads the hierarchy, and inserts new folders or modifications to folders in the local store.</span></span> <span data-ttu-id="3342a-121">下载过程采用 Microsoft Exchange 增量更改同步 (ICS) 。</span><span class="sxs-lookup"><span data-stu-id="3342a-121">The download process adopts Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="3342a-122">有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3342a-122">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
<span data-ttu-id="3342a-123">当此状态结束时，本地存储将返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="3342a-123">When this state ends, the local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3342a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3342a-124">See also</span></span>



[<span data-ttu-id="3342a-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="3342a-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="3342a-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="3342a-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="3342a-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="3342a-127">SYNCSTATE</span></span>](syncstate.md)

