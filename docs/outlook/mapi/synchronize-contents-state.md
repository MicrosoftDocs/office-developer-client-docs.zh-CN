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
# <a name="synchronize-contents-state"></a><span data-ttu-id="704c1-103">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="704c1-103">Synchronize Contents State</span></span>

  
  
<span data-ttu-id="704c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="704c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="704c1-105">本主题介绍同步复制状态机的内容状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="704c1-105">This topic describes what happens during the synchronize contents state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="704c1-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="704c1-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="704c1-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="704c1-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="704c1-108">**LR_SYNC_CONTENTS**</span><span class="sxs-lookup"><span data-stu-id="704c1-108">**LR_SYNC_CONTENTS**</span></span> <br/> |
|<span data-ttu-id="704c1-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="704c1-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="704c1-110">**[SYNCCONT](synccont.md)**</span><span class="sxs-lookup"><span data-stu-id="704c1-110">**[SYNCCONT](synccont.md)**</span></span> <br/> |
|<span data-ttu-id="704c1-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="704c1-111">From this state:</span></span>  <br/> |[<span data-ttu-id="704c1-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="704c1-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="704c1-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="704c1-113">To this state:</span></span>  <br/> |<span data-ttu-id="704c1-114">[下载表状态](download-table-state.md)[、上传表状态](upload-table-state.md)或同步状态</span><span class="sxs-lookup"><span data-stu-id="704c1-114">[Download table state](download-table-state.md), [upload table state](upload-table-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="704c1-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="704c1-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="704c1-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="704c1-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="704c1-117">说明</span><span class="sxs-lookup"><span data-stu-id="704c1-117">Description</span></span>

<span data-ttu-id="704c1-118">此状态启动两个复制过程之一：在本地存储上上载指定文件夹的内容或完全同步。</span><span class="sxs-lookup"><span data-stu-id="704c1-118">This state initiates one of the two replication processes: uploading the contents of specified folders on a local store, or a full synchronization.</span></span> <span data-ttu-id="704c1-119">在完全同步中，将首先上传并下载每个指定文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="704c1-119">In a full synchronization, for each of the specified folders, contents are uploaded first and then downloaded.</span></span> <span data-ttu-id="704c1-120">根据前面同步状态的相应 **[SYNC](sync.md)** 结构中设置的 *ulFlags，Outlook* **SYNCCONT** 结构中初始化 [out] 成员以提供内容相关信息。</span><span class="sxs-lookup"><span data-stu-id="704c1-120">Depending on the  *ulFlags*  set in the corresponding **[SYNC](sync.md)** structure in the preceding synchronize state, Outlook initializes [out] members in the **SYNCCONT** structure to provide information about the contents.</span></span> 
  
<span data-ttu-id="704c1-121">通过相同的 **SYNCCONT** 结构，客户端获取包含要上载或下载的内容的文件夹计数。</span><span class="sxs-lookup"><span data-stu-id="704c1-121">Through the same **SYNCCONT** structure, the client obtains the count of the folders that have content to be uploaded or downloaded.</span></span> <span data-ttu-id="704c1-122">客户端将循环访问其中每个文件夹，方法为将本地存储移动到上传表状态以上传文件夹，或将本地存储移动到下载表状态以下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="704c1-122">The client will loop through each of these folders by moving the local store to the upload table state to upload a folder, or moving the local store to the download table state to download the folder.</span></span> 
  
<span data-ttu-id="704c1-123">此外，客户端获取需要复制的文件夹的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="704c1-123">In addition, the client obtains entry IDs for the folders requiring replication.</span></span>
  
<span data-ttu-id="704c1-124">当此状态结束时，Outlook清理其内部信息。</span><span class="sxs-lookup"><span data-stu-id="704c1-124">When this state ends, Outlook cleans up its internal information.</span></span> <span data-ttu-id="704c1-125">本地存储将返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="704c1-125">The local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="704c1-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="704c1-126">See also</span></span>



[<span data-ttu-id="704c1-127">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="704c1-127">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="704c1-128">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="704c1-128">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="704c1-129">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="704c1-129">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="704c1-130">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="704c1-130">SYNCSTATE</span></span>](syncstate.md)

