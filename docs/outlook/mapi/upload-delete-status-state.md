---
title: 上传删除状态状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dda9d23a572446a5fa79a9500eb69558b6e0debd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357706"
---
# <a name="upload-delete-status-state"></a><span data-ttu-id="17b72-103">上传删除状态状态</span><span class="sxs-lookup"><span data-stu-id="17b72-103">Upload Delete Status State</span></span>

  
  
<span data-ttu-id="17b72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17b72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="17b72-105">本主题介绍复制状态机的上载删除状态状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="17b72-105">This topic describes what happens during the upload delete status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="17b72-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="17b72-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="17b72-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="17b72-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="17b72-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span><span class="sxs-lookup"><span data-stu-id="17b72-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span></span> <br/> |
|<span data-ttu-id="17b72-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="17b72-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="17b72-110">**[UPDEL](updel.md)**</span><span class="sxs-lookup"><span data-stu-id="17b72-110">**[UPDEL](updel.md)**</span></span> <br/> |
|<span data-ttu-id="17b72-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="17b72-111">From this state:</span></span>  <br/> |[<span data-ttu-id="17b72-112">上传表状态</span><span class="sxs-lookup"><span data-stu-id="17b72-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="17b72-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="17b72-113">To this state:</span></span>  <br/> |<span data-ttu-id="17b72-114">上传表状态</span><span class="sxs-lookup"><span data-stu-id="17b72-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="17b72-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="17b72-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="17b72-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="17b72-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="17b72-117">说明</span><span class="sxs-lookup"><span data-stu-id="17b72-117">Description</span></span>

<span data-ttu-id="17b72-118">此状态会在服务器上启动更新, 这些 Outlook 项目 (邮件、日历、联系人、任务、便笺或日记) 已在以前的上载表状态中指定的本地存储上的文件夹中删除。</span><span class="sxs-lookup"><span data-stu-id="17b72-118">This state initiates updating on a server those Outlook items (mail, calendar, contact, task, note, or journal) that have been deleted in a folder on a local store specified in a preceding upload table state.</span></span> <span data-ttu-id="17b72-119">在此状态下, Outlook 使用已从文件夹中删除或移动的项目的信息初始化关联的**UPDEL**数据结构中的成员。</span><span class="sxs-lookup"><span data-stu-id="17b72-119">During this state, Outlook initializes members in the associated **UPDEL** data structure with information for the items that have been deleted or moved from the folder.</span></span> 
  
<span data-ttu-id="17b72-120">然后, 客户端会删除服务器上的文件夹中的指定项。</span><span class="sxs-lookup"><span data-stu-id="17b72-120">The client then deletes the specified items in the folder on the server.</span></span> <span data-ttu-id="17b72-121">若要区分已移动而不是已删除的项目, 客户端必须检查**UPDEL**结构中标识的*pupmov*成员。</span><span class="sxs-lookup"><span data-stu-id="17b72-121">To distinguish items that have been moved as opposed to having been deleted, the client must check the  *pupmov*  members identified in the **UPDEL** structure.</span></span> 
  
<span data-ttu-id="17b72-122">当此状态结束时, Outlook 将清除指示该项已被删除的内部信息;因此, Outlook 将不再具有该项目的记录。</span><span class="sxs-lookup"><span data-stu-id="17b72-122">When this state ends, Outlook clears the internal information indicating that the item has been deleted; consequently, Outlook will no longer have a record of the item.</span></span> <span data-ttu-id="17b72-123">本地存储将返回到上传表状态。</span><span class="sxs-lookup"><span data-stu-id="17b72-123">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17b72-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17b72-124">See also</span></span>



[<span data-ttu-id="17b72-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="17b72-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="17b72-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="17b72-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="17b72-127">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="17b72-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="17b72-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="17b72-128">SYNCSTATE</span></span>](syncstate.md)

