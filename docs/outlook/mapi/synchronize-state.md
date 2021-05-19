---
title: 同步状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 270ff414-514c-b1fc-db48-761bf6de8867
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7abbf049a848d417f640528e5030e37a954413e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414625"
---
# <a name="synchronize-state"></a><span data-ttu-id="ccce2-103">同步状态</span><span class="sxs-lookup"><span data-stu-id="ccce2-103">Synchronize State</span></span>

  
  
<span data-ttu-id="ccce2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ccce2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="ccce2-105">本主题介绍复制状态机的同步状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="ccce2-105">This topic describes what happens during the synchronize state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="ccce2-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="ccce2-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ccce2-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="ccce2-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="ccce2-108">**LR_SYNC**</span><span class="sxs-lookup"><span data-stu-id="ccce2-108">**LR_SYNC**</span></span> <br/> |
|<span data-ttu-id="ccce2-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="ccce2-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="ccce2-110">**[SYNC](sync.md)**</span><span class="sxs-lookup"><span data-stu-id="ccce2-110">**[SYNC](sync.md)**</span></span> <br/> |
|<span data-ttu-id="ccce2-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="ccce2-111">From this state:</span></span>  <br/> |[<span data-ttu-id="ccce2-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="ccce2-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="ccce2-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="ccce2-113">To this state:</span></span>  <br/> |<span data-ttu-id="ccce2-114">[下载层次结构状态](download-hierarchy-state.md)[、同步内容状态](synchronize-contents-state.md)、[上载层次结构状态](upload-hierarchy-state.md)或空闲状态</span><span class="sxs-lookup"><span data-stu-id="ccce2-114">[Download hierarchy state](download-hierarchy-state.md), [synchronize contents state](synchronize-contents-state.md), [upload hierarchy state](upload-hierarchy-state.md), or idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="ccce2-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="ccce2-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="ccce2-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="ccce2-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="ccce2-117">说明</span><span class="sxs-lookup"><span data-stu-id="ccce2-117">Description</span></span>

<span data-ttu-id="ccce2-118">此状态将启动同步。</span><span class="sxs-lookup"><span data-stu-id="ccce2-118">This state initiates synchronization.</span></span> <span data-ttu-id="ccce2-119">本地应用商店可以从此处转换为上传或下载状态。</span><span class="sxs-lookup"><span data-stu-id="ccce2-119">A local store can transition to an upload or a download state from here.</span></span> <span data-ttu-id="ccce2-120">例如，本地存储可以移动到上载层次结构状态以将文件夹层次结构上载到服务器，或者可以通过先上载层次结构然后从服务器下载层次结构来执行完全同步。</span><span class="sxs-lookup"><span data-stu-id="ccce2-120">For example, a local store can move to the upload hierarchy state to upload a folder hierarchy to the server, or it can perform a full synchronization by first uploading the hierarchy and then downloading the hierarchy from the server.</span></span>
  
<span data-ttu-id="ccce2-121">在此状态中，Outlook使用本地存储的路径初始化关联的 **SYNC** 数据结构，以便Outlook状态期间看到修改。</span><span class="sxs-lookup"><span data-stu-id="ccce2-121">During this state, Outlook initializes the associated **SYNC** data structure with the path to the local store, so that Outlook sees modifications during other states.</span></span> 
  
<span data-ttu-id="ccce2-122">客户端设置 **SYNC** 的 [in] 成员，Outlook如何处理其他状态。</span><span class="sxs-lookup"><span data-stu-id="ccce2-122">The client sets the [in] members of **SYNC**, which tells Outlook how to handle other states.</span></span> <span data-ttu-id="ccce2-123">例如，客户端可以将 *ulFlags* 设置为 **UPS_UPLOAD_ONLY** 和 **UPS_THESE_FOLDERS** 并拼写到文件夹的条目标识符列表，以告知 Outlook将仅上载这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="ccce2-123">For example, the client can set  *ulFlags*  to **UPS_UPLOAD_ONLY** and **UPS_THESE_FOLDERS** and  *pel*  to a list of entry identifiers of the folders to tell Outlook that only these folders will be uploaded.</span></span> <span data-ttu-id="ccce2-124">当此状态结束时，本地存储将恢复为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="ccce2-124">When this state ends, the local store reverts to the idle state.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ccce2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccce2-125">See also</span></span>



[<span data-ttu-id="ccce2-126">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="ccce2-126">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="ccce2-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ccce2-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="ccce2-128">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="ccce2-128">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="ccce2-129">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="ccce2-129">SYNCSTATE</span></span>](syncstate.md)

