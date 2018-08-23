---
title: 上传表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bd54c30e8701a13637235e28ddcfef4c21d10a2b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576979"
---
# <a name="upload-table-state"></a><span data-ttu-id="c5746-103">上传表状态</span><span class="sxs-lookup"><span data-stu-id="c5746-103">Upload Table State</span></span>

  
  
<span data-ttu-id="c5746-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c5746-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="c5746-105">本主题介绍的复制状态机上载表状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="c5746-105">This topic describes what happens during the upload table state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="c5746-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="c5746-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c5746-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="c5746-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="c5746-108">**LR_SYNC_UPLOAD_TABLE**</span><span class="sxs-lookup"><span data-stu-id="c5746-108">**LR_SYNC_UPLOAD_TABLE**</span></span> <br/> |
|<span data-ttu-id="c5746-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="c5746-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="c5746-110">**[UPTBL](uptbl.md)**</span><span class="sxs-lookup"><span data-stu-id="c5746-110">**[UPTBL](uptbl.md)**</span></span> <br/> |
|<span data-ttu-id="c5746-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="c5746-111">From this state:</span></span>  <br/> |[<span data-ttu-id="c5746-112">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="c5746-112">Synchronize contents state</span></span>](synchronize-contents-state.md) <br/> |
|<span data-ttu-id="c5746-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="c5746-113">To this state:</span></span>  <br/> |<span data-ttu-id="c5746-114">[上载邮件状态](upload-message-state.md)、[上载删除状态状态](upload-delete-status-state.md)、[上载读取状态状态](upload-read-status-state.md)，或同步内容状态</span><span class="sxs-lookup"><span data-stu-id="c5746-114">[Upload message state](upload-message-state.md), [upload delete status state](upload-delete-status-state.md), [upload read status state](upload-read-status-state.md), or synchronize contents state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c5746-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="c5746-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="c5746-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="c5746-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="c5746-117">说明</span><span class="sxs-lookup"><span data-stu-id="c5746-117">Description</span></span>

<span data-ttu-id="c5746-118">此状态启动上载已在前面的同步内容状态指定文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="c5746-118">This state initiates uploading the contents of a folder that has been specified in a preceding synchronize contents state.</span></span> <span data-ttu-id="c5746-119">文件夹可以是邮件、 日历、 联系人、 任务、 备注或日记文件夹。</span><span class="sxs-lookup"><span data-stu-id="c5746-119">The folder can be a mail, calendar, contacts, tasks, notes, or journal folder.</span></span> <span data-ttu-id="c5746-120">在此状态下，Outlook 创建列表项的已添加、 修改、 移动、 删除或标记为已读，并准备对应的上载邮件状态的适当内部信息、 上载删除状态状态或上载读取状态状态。</span><span class="sxs-lookup"><span data-stu-id="c5746-120">During this state, Outlook creates a list of items that have been added, modified, moved, deleted, or marked as read, and prepares the appropriate internal information for the corresponding upload message state, upload delete status state, or upload read status state.</span></span>
  
<span data-ttu-id="c5746-121">此状态结束时，Outlook 将标记为具有同步，其内容，以便进行另一种修改之前，内容将不重新上载的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c5746-121">When this state ends, Outlook marks the folder as having its contents synchronized, so that the contents will not be uploaded again until another modification is made.</span></span> <span data-ttu-id="c5746-122">本地存储返回到同步内容状态。</span><span class="sxs-lookup"><span data-stu-id="c5746-122">The local store returns to the synchronize contents state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c5746-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5746-123">See also</span></span>



[<span data-ttu-id="c5746-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="c5746-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="c5746-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="c5746-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="c5746-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="c5746-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="c5746-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="c5746-127">SYNCSTATE</span></span>](syncstate.md)

