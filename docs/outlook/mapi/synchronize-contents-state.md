---
title: 同步内容状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 52216bc3-8cbd-3856-ea46-78f7d0dd66ff
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2bdbeb39cce1e62569f364875c3828cdd530c63
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577245"
---
# <a name="synchronize-contents-state"></a><span data-ttu-id="db1b9-103">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="db1b9-103">Synchronize Contents State</span></span>

  
  
<span data-ttu-id="db1b9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="db1b9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="db1b9-105">本主题介绍的复制状态机同步内容状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="db1b9-105">This topic describes what happens during the synchronize contents state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="db1b9-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="db1b9-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="db1b9-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="db1b9-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="db1b9-108">**LR_SYNC_CONTENTS**</span><span class="sxs-lookup"><span data-stu-id="db1b9-108">**LR_SYNC_CONTENTS**</span></span> <br/> |
|<span data-ttu-id="db1b9-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="db1b9-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="db1b9-110">**[SYNCCONT](synccont.md)**</span><span class="sxs-lookup"><span data-stu-id="db1b9-110">**[SYNCCONT](synccont.md)**</span></span> <br/> |
|<span data-ttu-id="db1b9-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="db1b9-111">From this state:</span></span>  <br/> |[<span data-ttu-id="db1b9-112">同步状态</span><span class="sxs-lookup"><span data-stu-id="db1b9-112">Synchronize state</span></span>](synchronize-state.md) <br/> |
|<span data-ttu-id="db1b9-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="db1b9-113">To this state:</span></span>  <br/> |<span data-ttu-id="db1b9-114">[下载表状态](download-table-state.md)、[上载表状态](upload-table-state.md)，或同步状态</span><span class="sxs-lookup"><span data-stu-id="db1b9-114">[Download table state](download-table-state.md), [upload table state](upload-table-state.md), or synchronize state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="db1b9-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="db1b9-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="db1b9-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="db1b9-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="db1b9-117">说明</span><span class="sxs-lookup"><span data-stu-id="db1b9-117">Description</span></span>

<span data-ttu-id="db1b9-118">此状态启动两个复制过程之一： 上载的内容文件夹的本地存储区或指定完全同步。</span><span class="sxs-lookup"><span data-stu-id="db1b9-118">This state initiates one of the two replication processes: uploading the contents of specified folders on a local store, or a full synchronization.</span></span> <span data-ttu-id="db1b9-119">在完全同步，为每个指定文件夹中，内容是首先上载和下载。</span><span class="sxs-lookup"><span data-stu-id="db1b9-119">In a full synchronization, for each of the specified folders, contents are uploaded first and then downloaded.</span></span> <span data-ttu-id="db1b9-120">根据在上述的相应**[同步](sync.md)** 结构中设置*ulFlags*同步状态时，Outlook 初始化 [输出] **SYNCCONT**结构中的成员以提供有关内容的信息。</span><span class="sxs-lookup"><span data-stu-id="db1b9-120">Depending on the  *ulFlags*  set in the corresponding **[SYNC](sync.md)** structure in the preceding synchronize state, Outlook initializes [out] members in the **SYNCCONT** structure to provide information about the contents.</span></span> 
  
<span data-ttu-id="db1b9-121">通过相同的**SYNCCONT**结构，客户端获取具有内容上载或下载的文件夹的计数。</span><span class="sxs-lookup"><span data-stu-id="db1b9-121">Through the same **SYNCCONT** structure, the client obtains the count of the folders that have content to be uploaded or downloaded.</span></span> <span data-ttu-id="db1b9-122">将本地存储移动到上载表状态上载一个文件夹，或移动到下载表状态，若要下载该文件夹的本地存储的情况下，客户端将循环访问每个这些文件夹。</span><span class="sxs-lookup"><span data-stu-id="db1b9-122">The client will loop through each of these folders by moving the local store to the upload table state to upload a folder, or moving the local store to the download table state to download the folder.</span></span> 
  
<span data-ttu-id="db1b9-123">此外，客户端获取需要复制的文件夹的条目 Id。</span><span class="sxs-lookup"><span data-stu-id="db1b9-123">In addition, the client obtains entry IDs for the folders requiring replication.</span></span>
  
<span data-ttu-id="db1b9-124">此状态结束时，Outlook 将清理其内部的信息。</span><span class="sxs-lookup"><span data-stu-id="db1b9-124">When this state ends, Outlook cleans up its internal information.</span></span> <span data-ttu-id="db1b9-125">本地存储返回到同步状态。</span><span class="sxs-lookup"><span data-stu-id="db1b9-125">The local store returns to the synchronize state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db1b9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db1b9-126">See also</span></span>



[<span data-ttu-id="db1b9-127">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="db1b9-127">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="db1b9-128">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="db1b9-128">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="db1b9-129">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="db1b9-129">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="db1b9-130">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="db1b9-130">SYNCSTATE</span></span>](syncstate.md)

