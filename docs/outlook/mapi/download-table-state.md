---
title: 下载表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5bcc8b0a-0ab7-6c3e-8334-9e83cf2882a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7451d159ef97ef9d8160b386ec5bf88fb388706e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338337"
---
# <a name="download-table-state"></a><span data-ttu-id="22ae5-103">下载表状态</span><span class="sxs-lookup"><span data-stu-id="22ae5-103">Download Table State</span></span>

  
  
<span data-ttu-id="22ae5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22ae5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="22ae5-105">本主题介绍复制状态机的下载表状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="22ae5-105">This topic describes what happens during the download table state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="22ae5-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="22ae5-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="22ae5-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="22ae5-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="22ae5-108">**LR_SYNC_DOWNLOAD_TABLE**</span><span class="sxs-lookup"><span data-stu-id="22ae5-108">**LR_SYNC_DOWNLOAD_TABLE**</span></span> <br/> |
|<span data-ttu-id="22ae5-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="22ae5-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="22ae5-110">**[DNTBL](dntbl.md)**</span><span class="sxs-lookup"><span data-stu-id="22ae5-110">**[DNTBL](dntbl.md)**</span></span> <br/> |
|<span data-ttu-id="22ae5-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="22ae5-111">From this state:</span></span>  <br/> |[<span data-ttu-id="22ae5-112">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="22ae5-112">Synchronize contents state</span></span>](synchronize-contents-state.md) <br/> |
|<span data-ttu-id="22ae5-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="22ae5-113">To this state:</span></span>  <br/> |<span data-ttu-id="22ae5-114">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="22ae5-114">Synchronize contents state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="22ae5-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="22ae5-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="22ae5-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="22ae5-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="22ae5-117">说明</span><span class="sxs-lookup"><span data-stu-id="22ae5-117">Description</span></span>

<span data-ttu-id="22ae5-118">此状态将启动下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="22ae5-118">This state initiates downloading a folder.</span></span> <span data-ttu-id="22ae5-119">在此状态中，Outlook文件夹相关信息初始化关联的 **DNTBL** 数据结构。</span><span class="sxs-lookup"><span data-stu-id="22ae5-119">During this state, Outlook initializes the associated **DNTBL** data structure with information about the folder.</span></span> <span data-ttu-id="22ae5-120">客户端下载文件夹内容，然后使用服务器中的新内容、修改或删除更新本地存储上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22ae5-120">The client downloads the folder contents, and updates the folder on the local store with new contents, modifications, or deletions from the server.</span></span> <span data-ttu-id="22ae5-121">下载过程采用 Microsoft Exchange 增量更改同步 (ICS) 。</span><span class="sxs-lookup"><span data-stu-id="22ae5-121">The download process adopts Microsoft Exchange Incremental Change Synchronization (ICS).</span></span> <span data-ttu-id="22ae5-122">有关 ICS 的详细信息，请参阅 [ICS 评估条件](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="22ae5-122">For more information on ICS, see [ICS Evaluation Criteria](https://msdn.microsoft.com/library/aa579252%28EXCHG.80%29.aspx).</span></span>
  
<span data-ttu-id="22ae5-123">当此状态结束时，本地存储将返回同步内容状态。</span><span class="sxs-lookup"><span data-stu-id="22ae5-123">When this state ends, the local store returns to the synchronize contents state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22ae5-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22ae5-124">See also</span></span>



[<span data-ttu-id="22ae5-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="22ae5-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="22ae5-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="22ae5-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="22ae5-127">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="22ae5-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="22ae5-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="22ae5-128">SYNCSTATE</span></span>](syncstate.md)

