---
title: Upload删除状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dda9d23a572446a5fa79a9500eb69558b6e0debd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425839"
---
# <a name="upload-delete-status-state"></a><span data-ttu-id="2a568-103">Upload删除状态</span><span class="sxs-lookup"><span data-stu-id="2a568-103">Upload Delete Status State</span></span>

  
  
<span data-ttu-id="2a568-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2a568-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="2a568-105">本主题介绍复制状态机的上载删除状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="2a568-105">This topic describes what happens during the upload delete status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="2a568-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="2a568-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2a568-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="2a568-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="2a568-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span><span class="sxs-lookup"><span data-stu-id="2a568-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span></span> <br/> |
|<span data-ttu-id="2a568-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="2a568-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="2a568-110">**[UPDEL](updel.md)**</span><span class="sxs-lookup"><span data-stu-id="2a568-110">**[UPDEL](updel.md)**</span></span> <br/> |
|<span data-ttu-id="2a568-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="2a568-111">From this state:</span></span>  <br/> |[<span data-ttu-id="2a568-112">Upload表状态</span><span class="sxs-lookup"><span data-stu-id="2a568-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="2a568-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="2a568-113">To this state:</span></span>  <br/> |<span data-ttu-id="2a568-114">Upload表状态</span><span class="sxs-lookup"><span data-stu-id="2a568-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2a568-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="2a568-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="2a568-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="2a568-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="2a568-117">说明</span><span class="sxs-lookup"><span data-stu-id="2a568-117">Description</span></span>

<span data-ttu-id="2a568-118">此状态将在服务器上启动更新Outlook (邮件、日历、联系人、任务、笔记或日记) 项目，这些项目已在先前上传表状态指定的本地存储上的文件夹中删除。</span><span class="sxs-lookup"><span data-stu-id="2a568-118">This state initiates updating on a server those Outlook items (mail, calendar, contact, task, note, or journal) that have been deleted in a folder on a local store specified in a preceding upload table state.</span></span> <span data-ttu-id="2a568-119">在此状态中，Outlook关联的 **UPDEL** 数据结构中的成员，并获取已删除或从文件夹中移动的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="2a568-119">During this state, Outlook initializes members in the associated **UPDEL** data structure with information for the items that have been deleted or moved from the folder.</span></span> 
  
<span data-ttu-id="2a568-120">然后，客户端将删除服务器上文件夹中的指定项目。</span><span class="sxs-lookup"><span data-stu-id="2a568-120">The client then deletes the specified items in the folder on the server.</span></span> <span data-ttu-id="2a568-121">为了区分已移动而不是已删除的项目，客户端必须检查 **UPDEL** 结构中标识的 *pupmov* 成员。</span><span class="sxs-lookup"><span data-stu-id="2a568-121">To distinguish items that have been moved as opposed to having been deleted, the client must check the  *pupmov*  members identified in the **UPDEL** structure.</span></span> 
  
<span data-ttu-id="2a568-122">当此状态结束时，Outlook清除指示项目已删除的内部信息;因此，Outlook不再具有该项目的记录。</span><span class="sxs-lookup"><span data-stu-id="2a568-122">When this state ends, Outlook clears the internal information indicating that the item has been deleted; consequently, Outlook will no longer have a record of the item.</span></span> <span data-ttu-id="2a568-123">本地存储将返回到上载表状态。</span><span class="sxs-lookup"><span data-stu-id="2a568-123">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a568-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a568-124">See also</span></span>



[<span data-ttu-id="2a568-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="2a568-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="2a568-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2a568-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="2a568-127">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="2a568-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="2a568-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="2a568-128">SYNCSTATE</span></span>](syncstate.md)

