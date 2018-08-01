---
title: 上传表状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: fe167c90-c817-b627-0728-5c6393477c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 454df4dde2062d20855e4d9bceaf4400669693ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779054"
---
# <a name="upload-table-state"></a><span data-ttu-id="11db0-103">上传表状态</span><span class="sxs-lookup"><span data-stu-id="11db0-103">Upload Table State</span></span>

  
  
<span data-ttu-id="11db0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="11db0-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="11db0-105">本主题介绍的复制状态机上载表状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="11db0-105">This topic describes what happens during the upload table state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="11db0-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="11db0-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11db0-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="11db0-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="11db0-108">**LR_SYNC_UPLOAD_TABLE**</span><span class="sxs-lookup"><span data-stu-id="11db0-108">**LR_SYNC_UPLOAD_TABLE**</span></span> <br/> |
|<span data-ttu-id="11db0-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="11db0-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="11db0-110">**[UPTBL](uptbl.md)**</span><span class="sxs-lookup"><span data-stu-id="11db0-110">**[UPTBL](uptbl.md)**</span></span> <br/> |
|<span data-ttu-id="11db0-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="11db0-111">From this state:</span></span>  <br/> |[<span data-ttu-id="11db0-112">同步内容状态</span><span class="sxs-lookup"><span data-stu-id="11db0-112">Synchronize contents state</span></span>](synchronize-contents-state.md) <br/> |
|<span data-ttu-id="11db0-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="11db0-113">To this state:</span></span>  <br/> |<span data-ttu-id="11db0-114">[上载邮件状态](upload-message-state.md)、[上载删除状态状态](upload-delete-status-state.md)、[上载读取状态状态](upload-read-status-state.md)，或同步内容状态</span><span class="sxs-lookup"><span data-stu-id="11db0-114">[Upload message state](upload-message-state.md), [upload delete status state](upload-delete-status-state.md), [upload read status state](upload-read-status-state.md), or synchronize contents state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="11db0-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="11db0-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="11db0-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="11db0-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="11db0-117">说明</span><span class="sxs-lookup"><span data-stu-id="11db0-117">Description</span></span>

<span data-ttu-id="11db0-118">此状态启动上载已在前面的同步内容状态指定文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="11db0-118">This state initiates uploading the contents of a folder that has been specified in a preceding synchronize contents state.</span></span> <span data-ttu-id="11db0-119">文件夹可以是邮件、 日历、 联系人、 任务、 备注或日记文件夹。</span><span class="sxs-lookup"><span data-stu-id="11db0-119">The folder can be a mail, calendar, contacts, tasks, notes, or journal folder.</span></span> <span data-ttu-id="11db0-120">在此状态下，Outlook 创建列表项的已添加、 修改、 移动、 删除或标记为已读，并准备对应的上载邮件状态的适当内部信息、 上载删除状态状态或上载读取状态状态。</span><span class="sxs-lookup"><span data-stu-id="11db0-120">During this state, Outlook creates a list of items that have been added, modified, moved, deleted, or marked as read, and prepares the appropriate internal information for the corresponding upload message state, upload delete status state, or upload read status state.</span></span>
  
<span data-ttu-id="11db0-121">此状态结束时，Outlook 将标记为具有同步，其内容，以便进行另一种修改之前，内容将不重新上载的文件夹。</span><span class="sxs-lookup"><span data-stu-id="11db0-121">When this state ends, Outlook marks the folder as having its contents synchronized, so that the contents will not be uploaded again until another modification is made.</span></span> <span data-ttu-id="11db0-122">本地存储返回到同步内容状态。</span><span class="sxs-lookup"><span data-stu-id="11db0-122">The local store returns to the synchronize contents state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="11db0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11db0-123">See also</span></span>



[<span data-ttu-id="11db0-124">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="11db0-124">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="11db0-125">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="11db0-125">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="11db0-126">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="11db0-126">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="11db0-127">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="11db0-127">SYNCSTATE</span></span>](syncstate.md)

