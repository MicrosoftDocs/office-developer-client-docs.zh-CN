---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c8e83119d724f583d40583a6a5227bc467dc94da
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338834"
---
# <a name="download-message-header-state"></a><span data-ttu-id="d5a2c-103">下载邮件头状态</span><span class="sxs-lookup"><span data-stu-id="d5a2c-103">Download Message Header State</span></span>

  
  
<span data-ttu-id="d5a2c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5a2c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d5a2c-105">本主题介绍复制状态机的下载邮件头状态过程中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-105">This topic describes what happens during the download message header state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="d5a2c-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d5a2c-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d5a2c-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="d5a2c-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="d5a2c-108">**LR_SYNC_DOWNLOAD_HEADER**</span><span class="sxs-lookup"><span data-stu-id="d5a2c-108">**LR_SYNC_DOWNLOAD_HEADER**</span></span> <br/> |
|<span data-ttu-id="d5a2c-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="d5a2c-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="d5a2c-110">**[HDRSYNC](hdrsync.md)**</span><span class="sxs-lookup"><span data-stu-id="d5a2c-110">**[HDRSYNC](hdrsync.md)**</span></span> <br/> |
|<span data-ttu-id="d5a2c-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="d5a2c-111">From this state:</span></span>  <br/> |[<span data-ttu-id="d5a2c-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="d5a2c-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="d5a2c-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="d5a2c-113">To this state:</span></span>  <br/> |<span data-ttu-id="d5a2c-114">空闲状态</span><span class="sxs-lookup"><span data-stu-id="d5a2c-114">Idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d5a2c-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="d5a2c-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="d5a2c-117">说明</span><span class="sxs-lookup"><span data-stu-id="d5a2c-117">Description</span></span>

<span data-ttu-id="d5a2c-118">在此状态下, 客户端更新本地存储区上的邮件的邮件头。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-118">During this state, the client updates the header of a message on a local store.</span></span> <span data-ttu-id="d5a2c-119">本地存储在**[IOSTX:: SyncHdrBeg](iostx-synchdrbeg.md)** 时进入此状态, 并在调用**[IOSTX:: SyncHdrEnd](iostx-synchdrend.md)** 时退出。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-119">The local store enters this state upon **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** and exits when **[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** is called.</span></span> <span data-ttu-id="d5a2c-120">在此状态下, Outlook 使用有关邮件标头的信息初始化关联的**HDRSYNC**数据结构的成员。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-120">During this state, Outlook initializes members of the associated **HDRSYNC** data structure with information about the header of a message.</span></span> <span data-ttu-id="d5a2c-121">客户端先从服务器下载完整的邮件项, 然后在本地更新邮件项的邮件头。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-121">The client first downloads the full message item from the server and then updates the header of the message item locally.</span></span> 
  
<span data-ttu-id="d5a2c-122">当同步结束时, 客户端会设置下载结果。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-122">When syncrhonization ends, the client sets the download results.</span></span> <span data-ttu-id="d5a2c-123">本地存储将返回到空闲状态。</span><span class="sxs-lookup"><span data-stu-id="d5a2c-123">The local store returns to the idle state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d5a2c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5a2c-124">See also</span></span>



[<span data-ttu-id="d5a2c-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="d5a2c-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="d5a2c-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d5a2c-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="d5a2c-127">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="d5a2c-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="d5a2c-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="d5a2c-128">SYNCSTATE</span></span>](syncstate.md)

