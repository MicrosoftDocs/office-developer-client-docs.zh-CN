---
title: Upload表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2a9b3f214c76b8ec965c84c4731e0dc57e83352
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405819"
---
# <a name="upload-table-state"></a><span data-ttu-id="53153-103">Upload表状态</span><span class="sxs-lookup"><span data-stu-id="53153-103">Upload Table State</span></span>

  
  
<span data-ttu-id="53153-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53153-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="53153-105">本主题介绍复制状态机的上载表状态期间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="53153-105">This topic describes what happens during the upload table state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="53153-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="53153-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="53153-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="53153-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="53153-108">**LR_SYNC_UPLOAD_TABLE**</span><span class="sxs-lookup"><span data-stu-id="53153-108">**LR_SYNC_UPLOAD_TABLE**</span></span> <br/> |
|<span data-ttu-id="53153-109">相关数据结构：</span><span class="sxs-lookup"><span data-stu-id="53153-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="53153-110">**[UPTBL](uptbl.md)**</span><span class="sxs-lookup"><span data-stu-id="53153-110">**[UPTBL](uptbl.md)**</span></span> <br/> |
|<span data-ttu-id="53153-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="53153-111">From this state:</span></span>  <br/> |[<span data-ttu-id="53153-112">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="53153-112">Synchronize contents state</span></span>](synchronize-contents-state.md) <br/> |
|<span data-ttu-id="53153-113">至此状态：</span><span class="sxs-lookup"><span data-stu-id="53153-113">To this state:</span></span>  <br/> |<span data-ttu-id="53153-114">[Upload邮件状态、](upload-message-state.md)[上传删除状态、](upload-delete-status-state.md)[上传读取状态或](upload-read-status-state.md)同步内容状态</span><span class="sxs-lookup"><span data-stu-id="53153-114">[Upload message state](upload-message-state.md), [upload delete status state](upload-delete-status-state.md), [upload read status state](upload-read-status-state.md), or synchronize contents state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="53153-115">复制状态机是一个确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="53153-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="53153-116">从一个状态到另一个状态的客户端最终必须从后者返回到前者。</span><span class="sxs-lookup"><span data-stu-id="53153-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="53153-117">说明</span><span class="sxs-lookup"><span data-stu-id="53153-117">Description</span></span>

<span data-ttu-id="53153-118">此状态将启动上载之前同步内容状态中指定的文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="53153-118">This state initiates uploading the contents of a folder that has been specified in a preceding synchronize contents state.</span></span> <span data-ttu-id="53153-119">该文件夹可以是邮件、日历、联系人、任务、便笺或日记文件夹。</span><span class="sxs-lookup"><span data-stu-id="53153-119">The folder can be a mail, calendar, contacts, tasks, notes, or journal folder.</span></span> <span data-ttu-id="53153-120">在此状态中，Outlook创建已添加、修改、移动、删除或标记为已读的项目列表，并为相应的上传邮件状态、上传删除状态或上传读取状态状态准备相应的内部信息。</span><span class="sxs-lookup"><span data-stu-id="53153-120">During this state, Outlook creates a list of items that have been added, modified, moved, deleted, or marked as read, and prepares the appropriate internal information for the corresponding upload message state, upload delete status state, or upload read status state.</span></span>
  
<span data-ttu-id="53153-121">当此状态结束时，Outlook将文件夹标记为已同步其内容，以便内容不会再次上载，直到进行其他修改。</span><span class="sxs-lookup"><span data-stu-id="53153-121">When this state ends, Outlook marks the folder as having its contents synchronized, so that the contents will not be uploaded again until another modification is made.</span></span> <span data-ttu-id="53153-122">本地存储将返回同步内容状态。</span><span class="sxs-lookup"><span data-stu-id="53153-122">The local store returns to the synchronize contents state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53153-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53153-123">See also</span></span>



[<span data-ttu-id="53153-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="53153-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="53153-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="53153-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="53153-126">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="53153-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="53153-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="53153-127">SYNCSTATE</span></span>](syncstate.md)

