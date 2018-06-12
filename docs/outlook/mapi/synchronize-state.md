---
title: 同步状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270ff414-514c-b1fc-db48-761bf6de8867
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 36bdeecfaaa94492b1e719dbd1cf455bfa40db47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778944"
---
# <a name="synchronize-state"></a><span data-ttu-id="9868f-103">同步状态</span><span class="sxs-lookup"><span data-stu-id="9868f-103">Synchronize State</span></span>

  
  
<span data-ttu-id="9868f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9868f-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="9868f-105">本主题介绍时会发生什么情况期间的复制状态机同步状态。</span><span class="sxs-lookup"><span data-stu-id="9868f-105">This topic describes what happens during the synchronize state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="9868f-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="9868f-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9868f-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="9868f-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="9868f-108">**LR_SYNC**</span><span class="sxs-lookup"><span data-stu-id="9868f-108">**LR_SYNC**</span></span> <br/> |
|<span data-ttu-id="9868f-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="9868f-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="9868f-110">**[同步](sync.md)**</span><span class="sxs-lookup"><span data-stu-id="9868f-110">**[SYNC](sync.md)**</span></span> <br/> |
|<span data-ttu-id="9868f-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="9868f-111">From this state:</span></span>  <br/> |[<span data-ttu-id="9868f-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="9868f-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="9868f-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="9868f-113">To this state:</span></span>  <br/> |<span data-ttu-id="9868f-114">[下载层次结构状态](download-hierarchy-state.md)、[同步内容状态](synchronize-contents-state.md)、[上载层次结构状态](upload-hierarchy-state.md)，或空闲状态</span><span class="sxs-lookup"><span data-stu-id="9868f-114">[Download hierarchy state](download-hierarchy-state.md), [synchronize contents state](synchronize-contents-state.md), [upload hierarchy state](upload-hierarchy-state.md), or idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9868f-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="9868f-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="9868f-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="9868f-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="9868f-117">说明</span><span class="sxs-lookup"><span data-stu-id="9868f-117">Description</span></span>

<span data-ttu-id="9868f-118">此状态启动同步。</span><span class="sxs-lookup"><span data-stu-id="9868f-118">This state initiates synchronization.</span></span> <span data-ttu-id="9868f-119">本地存储从此处可以转换为上载或下载状态。</span><span class="sxs-lookup"><span data-stu-id="9868f-119">A local store can transition to an upload or a download state from here.</span></span> <span data-ttu-id="9868f-120">例如，本地存储可以移到上载层次结构状态文件夹层次结构上载到服务器，或它可以执行完全同步的第一个上载层次结构，然后从服务器下载层次结构。</span><span class="sxs-lookup"><span data-stu-id="9868f-120">For example, a local store can move to the upload hierarchy state to upload a folder hierarchy to the server, or it can perform a full synchronization by first uploading the hierarchy and then downloading the hierarchy from the server.</span></span>
  
<span data-ttu-id="9868f-121">在此状态下，Outlook 初始化的本地存储的路径具有关联的**同步**数据结构，以便该 Outlook 其他状态期间看到修改。</span><span class="sxs-lookup"><span data-stu-id="9868f-121">During this state, Outlook initializes the associated **SYNC** data structure with the path to the local store, so that Outlook sees modifications during other states.</span></span> 
  
<span data-ttu-id="9868f-122">[输入] 设置客户端**同步**，其告知如何处理其他状态的 Outlook 的成员。</span><span class="sxs-lookup"><span data-stu-id="9868f-122">The client sets the [in] members of **SYNC**, which tells Outlook how to handle other states.</span></span> <span data-ttu-id="9868f-123">例如，客户端可以设置*ulFlags* **UPS_UPLOAD_ONLY**和**UPS_THESE_FOLDERS**和将上载*pel*以告知 Outlook 仅这些文件夹的文件夹的项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="9868f-123">For example, the client can set  *ulFlags*  to **UPS_UPLOAD_ONLY** and **UPS_THESE_FOLDERS** and  *pel*  to a list of entry identifiers of the folders to tell Outlook that only these folders will be uploaded.</span></span> <span data-ttu-id="9868f-124">此状态结束时，本地存储恢复到空闲状态。</span><span class="sxs-lookup"><span data-stu-id="9868f-124">When this state ends, the local store reverts to the idle state.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9868f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9868f-125">See also</span></span>



[<span data-ttu-id="9868f-126">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="9868f-126">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="9868f-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="9868f-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="9868f-128">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="9868f-128">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="9868f-129">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="9868f-129">SYNCSTATE</span></span>](syncstate.md)

