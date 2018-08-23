---
title: 上传“删除状态”状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: dee566ad-b46d-1015-4b0b-6c3313060142
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a45cfafec5126c72f365858e41963bc95fa707a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574543"
---
# <a name="upload-delete-status-state"></a><span data-ttu-id="7681f-103">上传“删除状态”状态</span><span class="sxs-lookup"><span data-stu-id="7681f-103">Upload Delete Status State</span></span>

  
  
<span data-ttu-id="7681f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7681f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="7681f-105">本主题介绍的复制状态机上载删除状态状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="7681f-105">This topic describes what happens during the upload delete status state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="7681f-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7681f-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7681f-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="7681f-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="7681f-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span><span class="sxs-lookup"><span data-stu-id="7681f-108">**LR_SYNC_UPLOAD_MESSAGE_DEL**</span></span> <br/> |
|<span data-ttu-id="7681f-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="7681f-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="7681f-110">**[UPDEL](updel.md)**</span><span class="sxs-lookup"><span data-stu-id="7681f-110">**[UPDEL](updel.md)**</span></span> <br/> |
|<span data-ttu-id="7681f-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="7681f-111">From this state:</span></span>  <br/> |[<span data-ttu-id="7681f-112">上载表状态</span><span class="sxs-lookup"><span data-stu-id="7681f-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="7681f-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="7681f-113">To this state:</span></span>  <br/> |<span data-ttu-id="7681f-114">上载表状态</span><span class="sxs-lookup"><span data-stu-id="7681f-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="7681f-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="7681f-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="7681f-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="7681f-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="7681f-117">说明</span><span class="sxs-lookup"><span data-stu-id="7681f-117">Description</span></span>

<span data-ttu-id="7681f-118">此状态启动服务器上更新已在前面的上载表状态中指定的本地存储区上的文件夹中删除这些 Outlook 项目 （邮件、 日历、 联系人、 任务、 注释或日志）。</span><span class="sxs-lookup"><span data-stu-id="7681f-118">This state initiates updating on a server those Outlook items (mail, calendar, contact, task, note, or journal) that have been deleted in a folder on a local store specified in a preceding upload table state.</span></span> <span data-ttu-id="7681f-119">在此状态下，Outlook 初始化信息的项目的已删除或从文件夹移关联**UPDEL**数据结构中的成员。</span><span class="sxs-lookup"><span data-stu-id="7681f-119">During this state, Outlook initializes members in the associated **UPDEL** data structure with information for the items that have been deleted or moved from the folder.</span></span> 
  
<span data-ttu-id="7681f-120">然后，客户端删除的服务器上的文件夹中的指定的项。</span><span class="sxs-lookup"><span data-stu-id="7681f-120">The client then deletes the specified items in the folder on the server.</span></span> <span data-ttu-id="7681f-121">为了区分已移动而不是具有已删除的项，客户端必须检查**UPDEL**结构中标识的*pupmov*成员。</span><span class="sxs-lookup"><span data-stu-id="7681f-121">To distinguish items that have been moved as opposed to having been deleted, the client must check the  *pupmov*  members identified in the **UPDEL** structure.</span></span> 
  
<span data-ttu-id="7681f-122">此状态结束时，Outlook 将清除指示已删除项目; 内部信息因此，Outlook 将不再能够项的记录。</span><span class="sxs-lookup"><span data-stu-id="7681f-122">When this state ends, Outlook clears the internal information indicating that the item has been deleted; consequently, Outlook will no longer have a record of the item.</span></span> <span data-ttu-id="7681f-123">本地存储返回到上载表状态。</span><span class="sxs-lookup"><span data-stu-id="7681f-123">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7681f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7681f-124">See also</span></span>



[<span data-ttu-id="7681f-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="7681f-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="7681f-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="7681f-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="7681f-127">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="7681f-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="7681f-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="7681f-128">SYNCSTATE</span></span>](syncstate.md)

