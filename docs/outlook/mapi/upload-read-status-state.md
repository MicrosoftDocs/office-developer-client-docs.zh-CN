---
title: 上载读取状态状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d45574e-df87-8c44-4aa7-d41b38406f0a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8ad2acf019df3f07060c8e8c71a62afd3fca03c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431538"
---
# <a name="upload-read-status-state"></a><span data-ttu-id="f7573-103">上载读取状态状态</span><span class="sxs-lookup"><span data-stu-id="f7573-103">Upload Read Status State</span></span>

  
  
<span data-ttu-id="f7573-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7573-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="f7573-105">本主题介绍复制状态机的上载读取状态状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="f7573-105">This topic describes what happens during the upload read status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="f7573-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="f7573-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f7573-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="f7573-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="f7573-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span><span class="sxs-lookup"><span data-stu-id="f7573-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span></span> <br/> |
|<span data-ttu-id="f7573-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="f7573-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="f7573-110">**[UPREAD](upread.md)**</span><span class="sxs-lookup"><span data-stu-id="f7573-110">**[UPREAD](upread.md)**</span></span> <br/> |
|<span data-ttu-id="f7573-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="f7573-111">From this state:</span></span>  <br/> |[<span data-ttu-id="f7573-112">上传表状态</span><span class="sxs-lookup"><span data-stu-id="f7573-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="f7573-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="f7573-113">To this state:</span></span>  <br/> |<span data-ttu-id="f7573-114">上传表状态</span><span class="sxs-lookup"><span data-stu-id="f7573-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="f7573-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="f7573-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="f7573-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="f7573-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="f7573-117">说明</span><span class="sxs-lookup"><span data-stu-id="f7573-117">Description</span></span>

<span data-ttu-id="f7573-118">此状态将启动上传表状态中指定的文件夹中项目的读取状态的上载。</span><span class="sxs-lookup"><span data-stu-id="f7573-118">This state initiates uploading the read status of items in a folder specified in a preceding upload table state.</span></span> <span data-ttu-id="f7573-119">在此状态下, Outlook 将关联的**UPREAD**数据结构与已更改其读取状态的文件夹中的项目的信息进行初始化。</span><span class="sxs-lookup"><span data-stu-id="f7573-119">During this state, Outlook initializes the associated **UPREAD** data structure with information for those items in the folder whose read status has changed.</span></span> <span data-ttu-id="f7573-120">然后, 客户端将服务器上这些项目的读取状态更新为 "已读" 或 "未读"。</span><span class="sxs-lookup"><span data-stu-id="f7573-120">The client then updates the read status of these items on the server as being read or unread.</span></span> 
  
<span data-ttu-id="f7573-121">当此状态结束时, Outlook 将清除有关项目读取状态的内部信息, 以防止再次上载项目的读取状态。</span><span class="sxs-lookup"><span data-stu-id="f7573-121">When this state ends, Outlook clears the internal information about the item's read status, preventing the item's read status from being uploaded again.</span></span> <span data-ttu-id="f7573-122">本地存储将返回到上传表状态。</span><span class="sxs-lookup"><span data-stu-id="f7573-122">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f7573-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7573-123">See also</span></span>



[<span data-ttu-id="f7573-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="f7573-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="f7573-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f7573-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="f7573-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="f7573-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="f7573-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="f7573-127">SYNCSTATE</span></span>](syncstate.md)

