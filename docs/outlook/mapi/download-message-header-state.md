---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9d1745d25e7f7a5052d767350ade6723067d1b8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578841"
---
# <a name="download-message-header-state"></a><span data-ttu-id="b6a9b-103">下载邮件头状态</span><span class="sxs-lookup"><span data-stu-id="b6a9b-103">Download Message Header State</span></span>

  
  
<span data-ttu-id="b6a9b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6a9b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="b6a9b-105">本主题介绍在下载邮件头状态的复制状态机时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-105">This topic describes what happens during the download message header state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="b6a9b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b6a9b-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b6a9b-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="b6a9b-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="b6a9b-108">**LR_SYNC_DOWNLOAD_HEADER**</span><span class="sxs-lookup"><span data-stu-id="b6a9b-108">**LR_SYNC_DOWNLOAD_HEADER**</span></span> <br/> |
|<span data-ttu-id="b6a9b-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="b6a9b-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="b6a9b-110">**[HDRSYNC](hdrsync.md)**</span><span class="sxs-lookup"><span data-stu-id="b6a9b-110">**[HDRSYNC](hdrsync.md)**</span></span> <br/> |
|<span data-ttu-id="b6a9b-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="b6a9b-111">From this state:</span></span>  <br/> |[<span data-ttu-id="b6a9b-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="b6a9b-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="b6a9b-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="b6a9b-113">To this state:</span></span>  <br/> |<span data-ttu-id="b6a9b-114">空闲状态</span><span class="sxs-lookup"><span data-stu-id="b6a9b-114">Idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="b6a9b-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="b6a9b-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="b6a9b-117">说明</span><span class="sxs-lookup"><span data-stu-id="b6a9b-117">Description</span></span>

<span data-ttu-id="b6a9b-118">在此状态下，客户端更新本地存储区上的邮件的标头。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-118">During this state, the client updates the header of a message on a local store.</span></span> <span data-ttu-id="b6a9b-119">本地存储进入**[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** 时此状态，并在调用**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** 时退出。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-119">The local store enters this state upon **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** and exits when **[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** is called.</span></span> <span data-ttu-id="b6a9b-120">在此状态下，Outlook 初始化信息的邮件的标头关联**HDRSYNC**数据结构的成员。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-120">During this state, Outlook initializes members of the associated **HDRSYNC** data structure with information about the header of a message.</span></span> <span data-ttu-id="b6a9b-121">客户端首次从服务器下载完整邮件项目，然后更新本地的邮件项目的标题。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-121">The client first downloads the full message item from the server and then updates the header of the message item locally.</span></span> 
  
<span data-ttu-id="b6a9b-122">同步结束时，客户端设置下载结果。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-122">When syncrhonization ends, the client sets the download results.</span></span> <span data-ttu-id="b6a9b-123">本地存储返回到空闲状态。</span><span class="sxs-lookup"><span data-stu-id="b6a9b-123">The local store returns to the idle state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6a9b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6a9b-124">See also</span></span>



[<span data-ttu-id="b6a9b-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="b6a9b-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="b6a9b-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b6a9b-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="b6a9b-127">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="b6a9b-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="b6a9b-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="b6a9b-128">SYNCSTATE</span></span>](syncstate.md)

