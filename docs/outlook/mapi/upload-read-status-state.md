---
title: 上传“读取状态”状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d45574e-df87-8c44-4aa7-d41b38406f0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41815a88fe1215d2a85a38592e04b0d0bbd43cc6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573045"
---
# <a name="upload-read-status-state"></a><span data-ttu-id="d0e5b-103">上传“读取状态”状态</span><span class="sxs-lookup"><span data-stu-id="d0e5b-103">Upload Read Status State</span></span>

  
  
<span data-ttu-id="d0e5b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0e5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d0e5b-105">本主题介绍上载读取的复制状态机状态状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-105">This topic describes what happens during the upload read status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="d0e5b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d0e5b-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d0e5b-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="d0e5b-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span><span class="sxs-lookup"><span data-stu-id="d0e5b-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span></span> <br/> |
|<span data-ttu-id="d0e5b-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="d0e5b-110">**[UPREAD](upread.md)**</span><span class="sxs-lookup"><span data-stu-id="d0e5b-110">**[UPREAD](upread.md)**</span></span> <br/> |
|<span data-ttu-id="d0e5b-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-111">From this state:</span></span>  <br/> |[<span data-ttu-id="d0e5b-112">上载表状态</span><span class="sxs-lookup"><span data-stu-id="d0e5b-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="d0e5b-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-113">To this state:</span></span>  <br/> |<span data-ttu-id="d0e5b-114">上载表状态</span><span class="sxs-lookup"><span data-stu-id="d0e5b-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d0e5b-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="d0e5b-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="d0e5b-117">说明</span><span class="sxs-lookup"><span data-stu-id="d0e5b-117">Description</span></span>

<span data-ttu-id="d0e5b-118">此状态启动上载读取中前面的上载表状态指定文件夹中的项目的状态。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-118">This state initiates uploading the read status of items in a folder specified in a preceding upload table state.</span></span> <span data-ttu-id="d0e5b-119">在此状态下，Outlook 初始化为其读取的状态已更改的文件夹中的那些项目的信息的关联的**UPREAD**数据结构。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-119">During this state, Outlook initializes the associated **UPREAD** data structure with information for those items in the folder whose read status has changed.</span></span> <span data-ttu-id="d0e5b-120">然后，客户端更新读取为读或未读的服务器上对这些项目的状态。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-120">The client then updates the read status of these items on the server as being read or unread.</span></span> 
  
<span data-ttu-id="d0e5b-121">此状态结束时，Outlook 将清除的内部的项读取状态信息防止再次上载的项读取的状态。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-121">When this state ends, Outlook clears the internal information about the item's read status, preventing the item's read status from being uploaded again.</span></span> <span data-ttu-id="d0e5b-122">本地存储返回到上载表状态。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-122">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0e5b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0e5b-123">See also</span></span>



[<span data-ttu-id="d0e5b-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="d0e5b-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="d0e5b-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d0e5b-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="d0e5b-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="d0e5b-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="d0e5b-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="d0e5b-127">SYNCSTATE</span></span>](syncstate.md)

