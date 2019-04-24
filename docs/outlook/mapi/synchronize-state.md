---
title: 同步状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270ff414-514c-b1fc-db48-761bf6de8867
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7abbf049a848d417f640528e5030e37a954413e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349509"
---
# <a name="synchronize-state"></a><span data-ttu-id="e24b7-103">同步状态</span><span class="sxs-lookup"><span data-stu-id="e24b7-103">Synchronize State</span></span>

  
  
<span data-ttu-id="e24b7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e24b7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="e24b7-105">本主题介绍复制状态机的同步状态过程中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="e24b7-105">This topic describes what happens during the synchronize state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="e24b7-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="e24b7-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e24b7-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="e24b7-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="e24b7-108">**LR_SYNC**</span><span class="sxs-lookup"><span data-stu-id="e24b7-108">**LR_SYNC**</span></span> <br/> |
|<span data-ttu-id="e24b7-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="e24b7-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="e24b7-110">**[同步](sync.md)**</span><span class="sxs-lookup"><span data-stu-id="e24b7-110">**[SYNC](sync.md)**</span></span> <br/> |
|<span data-ttu-id="e24b7-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="e24b7-111">From this state:</span></span>  <br/> |[<span data-ttu-id="e24b7-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="e24b7-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="e24b7-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="e24b7-113">To this state:</span></span>  <br/> |<span data-ttu-id="e24b7-114">[下载层次结构状态](download-hierarchy-state.md)、[同步内容状态](synchronize-contents-state.md)、[上传层次结构状态](upload-hierarchy-state.md)或空闲状态</span><span class="sxs-lookup"><span data-stu-id="e24b7-114">[Download hierarchy state](download-hierarchy-state.md), [synchronize contents state](synchronize-contents-state.md), [upload hierarchy state](upload-hierarchy-state.md), or idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e24b7-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="e24b7-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="e24b7-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="e24b7-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="e24b7-117">说明</span><span class="sxs-lookup"><span data-stu-id="e24b7-117">Description</span></span>

<span data-ttu-id="e24b7-118">此状态将启动同步。</span><span class="sxs-lookup"><span data-stu-id="e24b7-118">This state initiates synchronization.</span></span> <span data-ttu-id="e24b7-119">本地存储可以从此处转换到上传或下载状态。</span><span class="sxs-lookup"><span data-stu-id="e24b7-119">A local store can transition to an upload or a download state from here.</span></span> <span data-ttu-id="e24b7-120">例如, 本地存储可以转到上载层次结构状态以将文件夹层次结构上传到服务器, 也可以通过先上载层次结构, 然后从服务器下载层次结构来执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="e24b7-120">For example, a local store can move to the upload hierarchy state to upload a folder hierarchy to the server, or it can perform a full synchronization by first uploading the hierarchy and then downloading the hierarchy from the server.</span></span>
  
<span data-ttu-id="e24b7-121">在此状态下, outlook 使用本地存储的路径初始化关联的**同步**数据结构, 以便 outlook 看到在其他状态期间进行的修改。</span><span class="sxs-lookup"><span data-stu-id="e24b7-121">During this state, Outlook initializes the associated **SYNC** data structure with the path to the local store, so that Outlook sees modifications during other states.</span></span> 
  
<span data-ttu-id="e24b7-122">客户端设置**SYNC**的 [in] 成员, 这将告诉 Outlook 如何处理其他状态。</span><span class="sxs-lookup"><span data-stu-id="e24b7-122">The client sets the [in] members of **SYNC**, which tells Outlook how to handle other states.</span></span> <span data-ttu-id="e24b7-123">例如, 客户端可以将*ulFlags*设置为**UPS_UPLOAD_ONLY**和**UPS_THESE_FOLDERS** and *pel* , 以指示 Outlook 仅上载这些文件夹的文件夹的条目标识符列表。</span><span class="sxs-lookup"><span data-stu-id="e24b7-123">For example, the client can set  *ulFlags*  to **UPS_UPLOAD_ONLY** and **UPS_THESE_FOLDERS** and  *pel*  to a list of entry identifiers of the folders to tell Outlook that only these folders will be uploaded.</span></span> <span data-ttu-id="e24b7-124">当此状态结束时, 本地存储将恢复为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="e24b7-124">When this state ends, the local store reverts to the idle state.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e24b7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e24b7-125">See also</span></span>



[<span data-ttu-id="e24b7-126">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="e24b7-126">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e24b7-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e24b7-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="e24b7-128">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="e24b7-128">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="e24b7-129">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="e24b7-129">SYNCSTATE</span></span>](syncstate.md)

