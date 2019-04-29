---
title: 上传邮件状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7fdc1494-4f40-38bd-d363-144ca70e5906
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 61cda23557a501a2651385d192f1dc7432ef1cb5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433799"
---
# <a name="upload-message-state"></a><span data-ttu-id="9bd9b-103">上传邮件状态</span><span class="sxs-lookup"><span data-stu-id="9bd9b-103">Upload Message State</span></span>

  
  
<span data-ttu-id="9bd9b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9bd9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="9bd9b-105">本主题介绍复制状态机的上载邮件状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-105">This topic describes what happens during the upload message state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="9bd9b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="9bd9b-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9bd9b-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="9bd9b-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="9bd9b-108">**LR_SYNC_UPLOAD_MESSAGE**</span><span class="sxs-lookup"><span data-stu-id="9bd9b-108">**LR_SYNC_UPLOAD_MESSAGE**</span></span> <br/> |
|<span data-ttu-id="9bd9b-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="9bd9b-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="9bd9b-110">**[UPMSG](upmsg.md)**</span><span class="sxs-lookup"><span data-stu-id="9bd9b-110">**[UPMSG](upmsg.md)**</span></span> <br/> |
|<span data-ttu-id="9bd9b-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="9bd9b-111">From this state:</span></span>  <br/> |[<span data-ttu-id="9bd9b-112">上传表状态</span><span class="sxs-lookup"><span data-stu-id="9bd9b-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="9bd9b-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="9bd9b-113">To this state:</span></span>  <br/> |<span data-ttu-id="9bd9b-114">上传表状态</span><span class="sxs-lookup"><span data-stu-id="9bd9b-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9bd9b-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="9bd9b-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="9bd9b-117">说明</span><span class="sxs-lookup"><span data-stu-id="9bd9b-117">Description</span></span>

<span data-ttu-id="9bd9b-118">此状态会启动上载新的 Outlook 项目 (邮件、日历、联系人、任务、便笺或日记), 或者已被移动到当前文件夹或已修改的项目。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-118">This state initiates uploading an Outlook item (mail, calendar, contact, task, note, or journal) that is new or has been moved to the current folder, or that has been modified.</span></span> <span data-ttu-id="9bd9b-119">Outlook 使用项目的添加、移动或修改的相应信息初始化 correpsonding **UPMSG**数据结构。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-119">Outlook initializes the correpsonding **UPMSG** data structure with the appropriate information for the item as being added, moved, or modified.</span></span> 
  
<span data-ttu-id="9bd9b-120">如果已添加或移动该项目, 则客户端会适当地在服务器上添加或更新项目。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-120">If the item has been added or moved, the client then appropriately adds or updates the item on the server.</span></span> 
  
<span data-ttu-id="9bd9b-121">如果修改了项目, Outlook 会进一步在**UPMSG**数据结构中指定所做的修改是在邮件头中 (在这种情况下, 该项目是邮件头)、项目属性中还是在需要冲突的项本身中。办法.</span><span class="sxs-lookup"><span data-stu-id="9bd9b-121">If the item has been modified, Outlook further specifies in the **UPMSG** data structure whether the modifications are in a message header (in which case the item is the message header), in the item properties, or in the item itself that requires conflict resolution.</span></span> <span data-ttu-id="9bd9b-122">然后, 客户端更新服务器上的项目。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-122">The client then updates the item on the server.</span></span> 
  
<span data-ttu-id="9bd9b-123">项目上传结束时, Outlook 会注意到邮件已上载, 因此在后续上传时不会处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-123">When the item upload ends, Outlook notes that the message has been uploaded, so that it will not be processed in a subsequent upload.</span></span> <span data-ttu-id="9bd9b-124">本地存储将返回到上传表状态。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-124">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9bd9b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bd9b-125">See also</span></span>



[<span data-ttu-id="9bd9b-126">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="9bd9b-126">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="9bd9b-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="9bd9b-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="9bd9b-128">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="9bd9b-128">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="9bd9b-129">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="9bd9b-129">SYNCSTATE</span></span>](syncstate.md)

