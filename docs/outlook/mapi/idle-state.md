---
title: 空闲状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 46976bea-c6bb-2e37-2e67-4cbccaa03aec
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3db4ead7e2485bbbae82f2a07659c934b394d6d5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419476"
---
# <a name="idle-state"></a><span data-ttu-id="4c3fc-103">空闲状态</span><span class="sxs-lookup"><span data-stu-id="4c3fc-103">Idle State</span></span>

  
  
<span data-ttu-id="4c3fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c3fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="4c3fc-105">本主题介绍在复制状态机的空闲状态期间会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="4c3fc-105">This topic describes what happens during the idle state of the replication state machine.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="4c3fc-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="4c3fc-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4c3fc-107">状态标识符:</span><span class="sxs-lookup"><span data-stu-id="4c3fc-107">State Identifier:</span></span>  <br/> |<span data-ttu-id="4c3fc-108">**LR_SYNC_IDLE**</span><span class="sxs-lookup"><span data-stu-id="4c3fc-108">**LR_SYNC_IDLE**</span></span> <br/> |
|<span data-ttu-id="4c3fc-109">相关数据结构:</span><span class="sxs-lookup"><span data-stu-id="4c3fc-109">Related Data Structure:</span></span>  <br/> | <span data-ttu-id="4c3fc-110">*None*</span><span class="sxs-lookup"><span data-stu-id="4c3fc-110">*None*</span></span>  <br/> |
|<span data-ttu-id="4c3fc-111">从此状态:</span><span class="sxs-lookup"><span data-stu-id="4c3fc-111">From this state:</span></span>  <br/> | <span data-ttu-id="4c3fc-112">*不适用*</span><span class="sxs-lookup"><span data-stu-id="4c3fc-112">*Not applicable*</span></span>  <br/> |
|<span data-ttu-id="4c3fc-113">到此状态:</span><span class="sxs-lookup"><span data-stu-id="4c3fc-113">To this state:</span></span>  <br/> |[<span data-ttu-id="4c3fc-114">同步状态</span><span class="sxs-lookup"><span data-stu-id="4c3fc-114">Synchronize state</span></span>](synchronize-state.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="4c3fc-115">复制状态计算机是确定的状态机。</span><span class="sxs-lookup"><span data-stu-id="4c3fc-115">The replication state machine is a deterministic state machine.</span></span> <span data-ttu-id="4c3fc-116">客户端从一个状态传出到另一个状态最终必须返回到前者的前一项。</span><span class="sxs-lookup"><span data-stu-id="4c3fc-116">A client departing from one state to another must eventually return to the former from the latter.</span></span> 
  
## <a name="description"></a><span data-ttu-id="4c3fc-117">说明</span><span class="sxs-lookup"><span data-stu-id="4c3fc-117">Description</span></span>

<span data-ttu-id="4c3fc-118">在此状态下什么都不会发生。</span><span class="sxs-lookup"><span data-stu-id="4c3fc-118">Nothing happens in this state.</span></span> <span data-ttu-id="4c3fc-119">在启动复制之前和复制完成之后, 本地存储处于此状态。</span><span class="sxs-lookup"><span data-stu-id="4c3fc-119">A local store is in this state before replication is initiated and after replication is complete.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c3fc-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c3fc-120">See also</span></span>



[<span data-ttu-id="4c3fc-121">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="4c3fc-121">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="4c3fc-122">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="4c3fc-122">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="4c3fc-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="4c3fc-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="4c3fc-124">SYNCSTATE</span><span class="sxs-lookup"><span data-stu-id="4c3fc-124">SYNCSTATE</span></span>](syncstate.md)

