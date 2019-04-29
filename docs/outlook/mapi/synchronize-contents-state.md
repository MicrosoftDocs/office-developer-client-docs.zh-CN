---
title: 同步内容状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 52216bc3-8cbd-3856-ea46-78f7d0dd66ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ebe1f5f48f9becdf01ea184c2b76fa2c8fa21e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438468"
---
# <a name="synchronize-contents-state"></a><span data-ttu-id="30a24-103">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="30a24-103">Synchronize Contents State</span></span>

  
  
<span data-ttu-id="30a24-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30a24-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="30a24-105">本主题介绍在复制状态机的同步内容状态期间会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="30a24-105">This topic describes what happens during the synchronize contents state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="30a24-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="30a24-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="30a24-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="30a24-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="30a24-108">**LR_SYNC_CONTENTS**</span><span class="sxs-lookup"><span data-stu-id="30a24-108">**LR_SYNC_CONTENTS**</span></span> <br/> |
|<span data-ttu-id="30a24-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="30a24-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="30a24-110">**[SYNCCONT](synccont.md)**</span><span class="sxs-lookup"><span data-stu-id="30a24-110">**[SYNCCONT](synccont.md)**</span></span> <br/> |
|<span data-ttu-id="30a24-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="30a24-111">From this state:</span></span>  <br/> |[<span data-ttu-id="30a24-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="30a24-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="30a24-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="30a24-113">To this state:</span></span>  <br/> |<span data-ttu-id="30a24-114">[下载表状态](download-table-state.md)、[上传表状态](upload-table-state.md)或同步状态</span><span class="sxs-lookup"><span data-stu-id="30a24-114">[Download table state](download-table-state.md), [upload table state](upload-table-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="30a24-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="30a24-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="30a24-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="30a24-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="30a24-117">说明</span><span class="sxs-lookup"><span data-stu-id="30a24-117">Description</span></span>

<span data-ttu-id="30a24-118">此状态将启动两个复制过程之一: 上载本地存储上指定文件夹的内容或完全同步。</span><span class="sxs-lookup"><span data-stu-id="30a24-118">This state initiates one of the two replication processes: uploading the contents of specified folders on a local store, or a full synchronization.</span></span> <span data-ttu-id="30a24-119">在完全同步中, 对于每个指定的文件夹, 首先上载并下载内容。</span><span class="sxs-lookup"><span data-stu-id="30a24-119">In a full synchronization, for each of the specified folders, contents are uploaded first and then downloaded.</span></span> <span data-ttu-id="30a24-120">根据上一同步状态中对应**[同步](sync.md)** 结构中设置的*ulFlags* , Outlook 将初始化**SYNCCONT**结构中的 [out] 成员以提供有关内容的信息。</span><span class="sxs-lookup"><span data-stu-id="30a24-120">Depending on the  *ulFlags*  set in the corresponding **[SYNC](sync.md)** structure in the preceding synchronize state, Outlook initializes [out] members in the **SYNCCONT** structure to provide information about the contents.</span></span> 
  
<span data-ttu-id="30a24-121">通过相同的**SYNCCONT**结构, 客户端可以获取包含要上载或下载的内容的文件夹的计数。</span><span class="sxs-lookup"><span data-stu-id="30a24-121">Through the same **SYNCCONT** structure, the client obtains the count of the folders that have content to be uploaded or downloaded.</span></span> <span data-ttu-id="30a24-122">客户端将通过以下方式遍历这些文件夹中的每一个: 将本地存储移动到上载表状态以上载文件夹, 或将本地存储移动到下载表状态以下载该文件夹。</span><span class="sxs-lookup"><span data-stu-id="30a24-122">The client will loop through each of these folders by moving the local store to the upload table state to upload a folder, or moving the local store to the download table state to download the folder.</span></span> 
  
<span data-ttu-id="30a24-123">此外, 客户端还获取需要复制的文件夹的条目 id。</span><span class="sxs-lookup"><span data-stu-id="30a24-123">In addition, the client obtains entry IDs for the folders requiring replication.</span></span>
  
<span data-ttu-id="30a24-124">当此状态结束时, Outlook 将清除其内部信息。</span><span class="sxs-lookup"><span data-stu-id="30a24-124">When this state ends, Outlook cleans up its internal information.</span></span> <span data-ttu-id="30a24-125">本地存储将返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="30a24-125">The local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30a24-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30a24-126">See also</span></span>



[<span data-ttu-id="30a24-127">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="30a24-127">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="30a24-128">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="30a24-128">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="30a24-129">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="30a24-129">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="30a24-130">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="30a24-130">SYNCSTATE</span></span>](syncstate.md)

