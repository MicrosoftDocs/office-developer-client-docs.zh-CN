---
title: 空闲状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 46976bea-c6bb-2e37-2e67-4cbccaa03aec
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b74ecb44d9a38fc73ceed4077d6f7a939f92f5f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591798"
---
# <a name="idle-state"></a><span data-ttu-id="1ad59-103">空闲状态</span><span class="sxs-lookup"><span data-stu-id="1ad59-103">Idle State</span></span>

  
  
<span data-ttu-id="1ad59-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ad59-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="1ad59-105">本主题介绍复制状态机空闲状态期间出现的情况。</span><span class="sxs-lookup"><span data-stu-id="1ad59-105">This topic describes what happens during the idle state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="1ad59-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="1ad59-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1ad59-107">状态标识符：</span><span class="sxs-lookup"><span data-stu-id="1ad59-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="1ad59-108">**LR_SYNC_IDLE**</span><span class="sxs-lookup"><span data-stu-id="1ad59-108">**LR_SYNC_IDLE**</span></span> <br/> |
|<span data-ttu-id="1ad59-109">相关的数据结构：</span><span class="sxs-lookup"><span data-stu-id="1ad59-109">Related Data Structure:</span></span>  <br/> | <span data-ttu-id="1ad59-110">*None*</span><span class="sxs-lookup"><span data-stu-id="1ad59-110">*None*</span></span>  <br/> |
|<span data-ttu-id="1ad59-111">从此状态：</span><span class="sxs-lookup"><span data-stu-id="1ad59-111">From this state:</span></span>  <br/> | <span data-ttu-id="1ad59-112">*不适用*</span><span class="sxs-lookup"><span data-stu-id="1ad59-112">*Not applicable*</span></span>  <br/> |
|<span data-ttu-id="1ad59-113">为此状态：</span><span class="sxs-lookup"><span data-stu-id="1ad59-113">To this state:</span></span>  <br/> |[<span data-ttu-id="1ad59-114">同步状态</span><span class="sxs-lookup"><span data-stu-id="1ad59-114">Synchronize state</span></span>](synchronize-state.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="1ad59-115">复制状态机是确定性状态机。</span><span class="sxs-lookup"><span data-stu-id="1ad59-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="1ad59-116">从一种状态传出到另一个客户端从后者必须最终返回到前者。</span><span class="sxs-lookup"><span data-stu-id="1ad59-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="1ad59-117">说明</span><span class="sxs-lookup"><span data-stu-id="1ad59-117">Description</span></span>

<span data-ttu-id="1ad59-118">没有处于此状态反应。</span><span class="sxs-lookup"><span data-stu-id="1ad59-118">Nothing happens in this state.</span></span> <span data-ttu-id="1ad59-119">启动复制之前和之后复制已完成的本地存储区处于此状态。</span><span class="sxs-lookup"><span data-stu-id="1ad59-119">A local store is in this state before replication is initiated and after replication is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ad59-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad59-120">See also</span></span>



[<span data-ttu-id="1ad59-121">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="1ad59-121">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="1ad59-122">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="1ad59-122">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="1ad59-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="1ad59-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="1ad59-124">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="1ad59-124">SYNCSTATE</span></span>](syncstate.md)

