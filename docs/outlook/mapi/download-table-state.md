---
title: 下载表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5bcc8b0a-0ab7-6c3e-8334-9e83cf2882a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a29cc131b4fe352b067e343376b2b705e8e3244
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774842"
---
# <a name="download-table-state"></a><span data-ttu-id="19631-103">下载表状态</span><span class="sxs-lookup"><span data-stu-id="19631-103">Download Table State</span></span>

  
  
<span data-ttu-id="19631-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19631-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="19631-105">本主题介绍的复制状态机下载表状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="19631-105">This topic describes what happens during the download table state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="19631-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="19631-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="19631-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="19631-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="19631-108">**LR_SYNC_DOWNLOAD_TABLE**</span><span class="sxs-lookup"><span data-stu-id="19631-108">**LR_SYNC_DOWNLOAD_TABLE**</span></span> <br/> |
|<span data-ttu-id="19631-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="19631-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="19631-110">**[DNTBL](dntbl.md)**</span><span class="sxs-lookup"><span data-stu-id="19631-110">**[DNTBL](dntbl.md)**</span></span> <br/> |
|<span data-ttu-id="19631-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="19631-111">From this state:</span></span>  <br/> |[<span data-ttu-id="19631-112">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="19631-112">Synchronize contents state</span></span>](synchronize-contents-state.md) <br/> |
|<span data-ttu-id="19631-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="19631-113">To this state:</span></span>  <br/> |<span data-ttu-id="19631-114">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="19631-114">Synchronize contents state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="19631-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="19631-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="19631-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="19631-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="19631-117">说明</span><span class="sxs-lookup"><span data-stu-id="19631-117">Description</span></span>

<span data-ttu-id="19631-118">此状态启动下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="19631-118">This state initiates downloading a folder.</span></span> <span data-ttu-id="19631-119">在此状态下，Outlook 初始化有关该文件夹具有关联的**DNTBL**数据结构。</span><span class="sxs-lookup"><span data-stu-id="19631-119">During this state, Outlook initializes the associated **DNTBL** data structure with information about the folder.</span></span> <span data-ttu-id="19631-120">客户端下载文件夹内容，并使用新的内容、 相应的修改或从服务器删除更新上本地存储的文件夹。</span><span class="sxs-lookup"><span data-stu-id="19631-120">The client downloads the folder contents, and updates the folder on the local store with new contents, modifications, or deletions from the server.</span></span> <span data-ttu-id="19631-121">下载过程采用 Microsoft Exchange 增量更改同步 (ICS)。</span><span class="sxs-lookup"><span data-stu-id="19631-121">The download process adopts Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="19631-122">ICS 的详细信息，请参阅[ICS 评价标准](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="19631-122">For more information on ICS, see [ICS Evaluation Criteria](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
<span data-ttu-id="19631-123">此状态结束时，本地存储返回到同步内容状态。</span><span class="sxs-lookup"><span data-stu-id="19631-123">When this state ends, the local store returns to the synchronize contents state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19631-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19631-124">See also</span></span>



[<span data-ttu-id="19631-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="19631-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="19631-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="19631-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="19631-127">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="19631-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="19631-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="19631-128">SYNCSTATE</span></span>](syncstate.md)

