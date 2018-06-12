---
title: 上载邮件状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7fdc1494-4f40-38bd-d363-144ca70e5906
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 752756cbcf6c1ce487188dd4b9ba55eee6506cd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779050"
---
# <a name="upload-message-state"></a><span data-ttu-id="282f2-103">上载邮件状态</span><span class="sxs-lookup"><span data-stu-id="282f2-103">Upload Message State</span></span>

  
  
<span data-ttu-id="282f2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="282f2-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="282f2-105">本主题介绍上载邮件状态的复制状态机期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="282f2-105">This topic describes what happens during the upload message state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="282f2-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="282f2-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="282f2-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="282f2-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="282f2-108">**LR_SYNC_UPLOAD_MESSAGE**</span><span class="sxs-lookup"><span data-stu-id="282f2-108">**LR_SYNC_UPLOAD_MESSAGE**</span></span> <br/> |
|<span data-ttu-id="282f2-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="282f2-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="282f2-110">**[UPMSG](upmsg.md)**</span><span class="sxs-lookup"><span data-stu-id="282f2-110">**[UPMSG](upmsg.md)**</span></span> <br/> |
|<span data-ttu-id="282f2-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="282f2-111">From this state:</span></span>  <br/> |[<span data-ttu-id="282f2-112">上载表状态</span><span class="sxs-lookup"><span data-stu-id="282f2-112">Upload table state</span></span>](upload-table-state.md) <br/> |
|<span data-ttu-id="282f2-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="282f2-113">To this state:</span></span>  <br/> |<span data-ttu-id="282f2-114">上载表状态</span><span class="sxs-lookup"><span data-stu-id="282f2-114">Upload table state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="282f2-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="282f2-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="282f2-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="282f2-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="282f2-117">说明</span><span class="sxs-lookup"><span data-stu-id="282f2-117">Description</span></span>

<span data-ttu-id="282f2-118">此状态启动上载 Outlook 项目 （邮件、 日历、 联系人、 任务、 注释或日记） 的新增或已移动到当前文件夹，或已修改的。</span><span class="sxs-lookup"><span data-stu-id="282f2-118">This state initiates uploading an Outlook item (mail, calendar, contact, task, note, or journal) that is new or has been moved to the current folder, or that has been modified.</span></span> <span data-ttu-id="282f2-119">Outlook 初始化 correpsonding **UPMSG**数据结构的项目的相应信息，如添加、 移动或修改。</span><span class="sxs-lookup"><span data-stu-id="282f2-119">Outlook initializes the correpsonding **UPMSG** data structure with the appropriate information for the item as being added, moved, or modified.</span></span> 
  
<span data-ttu-id="282f2-120">如果已添加或移动项目，客户端然后相应地添加或更新服务器上的项。</span><span class="sxs-lookup"><span data-stu-id="282f2-120">If the item has been added or moved, the client then appropriately adds or updates the item on the server.</span></span> 
  
<span data-ttu-id="282f2-121">如果已修改项目，Outlook 进一步指定**UPMSG**数据结构中修改的邮件头 （这种情况下该项目是邮件头）、 在项目属性，或本身需要冲突项目中解决方法。</span><span class="sxs-lookup"><span data-stu-id="282f2-121">If the item has been modified, Outlook further specifies in the **UPMSG** data structure whether the modifications are in a message header (in which case the item is the message header), in the item properties, or in the item itself that requires conflict resolution.</span></span> <span data-ttu-id="282f2-122">然后，客户端更新服务器上的项。</span><span class="sxs-lookup"><span data-stu-id="282f2-122">The client then updates the item on the server.</span></span> 
  
<span data-ttu-id="282f2-123">项目上载结束时，Outlook 备注，已上载邮件，以便将不会处理后续上载。</span><span class="sxs-lookup"><span data-stu-id="282f2-123">When the item upload ends, Outlook notes that the message has been uploaded, so that it will not be processed in a subsequent upload.</span></span> <span data-ttu-id="282f2-124">本地存储返回到上载表状态。</span><span class="sxs-lookup"><span data-stu-id="282f2-124">The local store returns to the upload table state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="282f2-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="282f2-125">See also</span></span>



[<span data-ttu-id="282f2-126">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="282f2-126">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="282f2-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="282f2-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="282f2-128">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="282f2-128">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="282f2-129">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="282f2-129">SYNCSTATE</span></span>](syncstate.md)

