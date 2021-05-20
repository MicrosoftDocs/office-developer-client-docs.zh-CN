---
title: Upload读取状态
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
# <a name="upload-read-status-state"></a><span data-ttu-id="efcd4-103">Upload读取状态</span><span class="sxs-lookup"><span data-stu-id="efcd4-103">Upload Read Status State</span></span>

  
  
<span data-ttu-id="efcd4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="efcd4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="efcd4-105">本主题介绍复制状态机的上载读取状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="efcd4-105">This topic describes what happens during the upload read status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="efcd4-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="efcd4-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="efcd4-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="efcd4-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="efcd4-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span><span class="sxs-lookup"><span data-stu-id="efcd4-108">**LR_SYNC_UPLOAD_MESSAGE_READ**</span></span> <br/> |
|<span data-ttu-id="efcd4-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="efcd4-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="efcd4-110">**[UPREAD](upread.md)**</span><span class="sxs-lookup"><span data-stu-id="efcd4-110">**[UPREAD](upread.md)**</span></span> <br/> |
|<span data-ttu-id="efcd4-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="efcd4-111">From this state:</span></span>  <br/> |[<span data-ttu-id="efcd4-112">Upload表状态</span><span class="sxs-lookup"><span data-stu-id="efcd4-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="efcd4-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="efcd4-113">To this state:</span></span>  <br/> |<span data-ttu-id="efcd4-114">Upload表状态</span><span class="sxs-lookup"><span data-stu-id="efcd4-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="efcd4-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="efcd4-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="efcd4-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="efcd4-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="efcd4-117">说明</span><span class="sxs-lookup"><span data-stu-id="efcd4-117">Description</span></span>

<span data-ttu-id="efcd4-118">此状态将启动在先前上传表状态中指定的文件夹中上传项目的读取状态。</span><span class="sxs-lookup"><span data-stu-id="efcd4-118">This state initiates uploading the read status of items in a folder specified in a preceding upload table state.</span></span> <span data-ttu-id="efcd4-119">在此状态中，Outlook读取状态已更改的文件夹中的项目的信息初始化关联的 **UPREAD** 数据结构。</span><span class="sxs-lookup"><span data-stu-id="efcd4-119">During this state, Outlook initializes the associated **UPREAD** data structure with information for those items in the folder whose read status has changed.</span></span> <span data-ttu-id="efcd4-120">然后，客户端会在服务器上将这些项目的读取状态更新为已读或未读。</span><span class="sxs-lookup"><span data-stu-id="efcd4-120">The client then updates the read status of these items on the server as being read or unread.</span></span> 
  
<span data-ttu-id="efcd4-121">此状态结束时，Outlook清除有关项目的读取状态的内部信息，以防止再次上载项目的读取状态。</span><span class="sxs-lookup"><span data-stu-id="efcd4-121">When this state ends, Outlook clears the internal information about the item's read status, preventing the item's read status from being uploaded again.</span></span> <span data-ttu-id="efcd4-122">本地存储将返回到上载表状态。</span><span class="sxs-lookup"><span data-stu-id="efcd4-122">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="efcd4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efcd4-123">See also</span></span>



[<span data-ttu-id="efcd4-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="efcd4-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="efcd4-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="efcd4-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="efcd4-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="efcd4-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="efcd4-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="efcd4-127">SYNCSTATE</span></span>](syncstate.md)

