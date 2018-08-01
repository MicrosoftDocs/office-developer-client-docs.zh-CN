---
title: 下载邮件头状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 03f69592-a5ea-e30b-9674-9cfa895163d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7407b6606634ecc0151f582e4481ecbff5e7dc57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774820"
---
# <a name="download-message-header-state"></a><span data-ttu-id="6d982-103">下载邮件头状态</span><span class="sxs-lookup"><span data-stu-id="6d982-103">Download Message Header State</span></span>

  
  
<span data-ttu-id="6d982-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6d982-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="6d982-105">本主题介绍在下载邮件头状态的复制状态机时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="6d982-105">This topic describes what happens during the download message header state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="6d982-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6d982-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6d982-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="6d982-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="6d982-108">**LR_SYNC_DOWNLOAD_HEADER**</span><span class="sxs-lookup"><span data-stu-id="6d982-108">**LR_SYNC_DOWNLOAD_HEADER**</span></span> <br/> |
|<span data-ttu-id="6d982-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="6d982-109">Related Data Structure:</span></span>  <br/> |<span data-ttu-id="6d982-110">**[HDRSYNC](hdrsync.md)**</span><span class="sxs-lookup"><span data-stu-id="6d982-110">**[HDRSYNC](hdrsync.md)**</span></span> <br/> |
|<span data-ttu-id="6d982-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="6d982-111">From this state:</span></span>  <br/> |[<span data-ttu-id="6d982-112">空闲状态</span><span class="sxs-lookup"><span data-stu-id="6d982-112">Idle state</span></span>](idle-state.md) <br/> |
|<span data-ttu-id="6d982-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="6d982-113">To this state:</span></span>  <br/> |<span data-ttu-id="6d982-114">空闲状态</span><span class="sxs-lookup"><span data-stu-id="6d982-114">Idle state</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6d982-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="6d982-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="6d982-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="6d982-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="6d982-117">说明</span><span class="sxs-lookup"><span data-stu-id="6d982-117">Description</span></span>

<span data-ttu-id="6d982-118">在此状态下，客户端更新本地存储区上的邮件的标头。</span><span class="sxs-lookup"><span data-stu-id="6d982-118">During this state, the client updates the header of a message on a local store.</span></span> <span data-ttu-id="6d982-119">本地存储进入**[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** 时此状态，并在调用**[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** 时退出。</span><span class="sxs-lookup"><span data-stu-id="6d982-119">The local store enters this state upon **[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)** and exits when **[IOSTX::SyncHdrEnd](iostx-synchdrend.md)** is called.</span></span> <span data-ttu-id="6d982-120">在此状态下，Outlook 初始化信息的邮件的标头关联**HDRSYNC**数据结构的成员。</span><span class="sxs-lookup"><span data-stu-id="6d982-120">During this state, Outlook initializes members of the associated **HDRSYNC** data structure with information about the header of a message.</span></span> <span data-ttu-id="6d982-121">客户端首次从服务器下载完整邮件项目，然后更新本地的邮件项目的标题。</span><span class="sxs-lookup"><span data-stu-id="6d982-121">The client first downloads the full message item from the server and then updates the header of the message item locally.</span></span> 
  
<span data-ttu-id="6d982-122">同步结束时，客户端设置下载结果。</span><span class="sxs-lookup"><span data-stu-id="6d982-122">When syncrhonization ends, the client sets the download results.</span></span> <span data-ttu-id="6d982-123">本地存储返回到空闲状态。</span><span class="sxs-lookup"><span data-stu-id="6d982-123">The local store returns to the idle state.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6d982-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d982-124">See also</span></span>



[<span data-ttu-id="6d982-125">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="6d982-125">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="6d982-126">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6d982-126">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="6d982-127">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="6d982-127">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="6d982-128">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="6d982-128">SYNCSTATE</span></span>](syncstate.md)

