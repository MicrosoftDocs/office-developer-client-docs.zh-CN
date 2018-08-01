---
title: IOSTXInitSync
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.InitSync
api_type:
- COM
ms.assetid: e22244a2-ac5f-910a-501f-4483ea0667c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 07305f712fd925b206ce18a32f8f5a24f199ccbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775953"
---
# <a name="iostxinitsync"></a><span data-ttu-id="189f2-103">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="189f2-103">IOSTX::InitSync</span></span>

  
  
<span data-ttu-id="189f2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="189f2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="189f2-105">通知的本地消息存储同步即将开始。</span><span class="sxs-lookup"><span data-stu-id="189f2-105">Informs the local message store that synchronization is about to start.</span></span>
  
```cpp
HRESULT InitSync( 
    ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="189f2-106">参数</span><span class="sxs-lookup"><span data-stu-id="189f2-106">Parameters</span></span>

 <span data-ttu-id="189f2-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="189f2-107">_ulFlags_</span></span>
  
> <span data-ttu-id="189f2-108">[in]同步过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="189f2-108">[in] Flags to determine appropriate behavior during synchronization.</span></span> <span data-ttu-id="189f2-109">Outlook 使用中的复制状态机每种状态这些标志来确定其应该为客户端提供的信息。</span><span class="sxs-lookup"><span data-stu-id="189f2-109">Outlook uses these flags in each state of the replication state machine to determine the information that it should provide for the client.</span></span> <span data-ttu-id="189f2-110">例如，如果客户端通过**SYNC_ONLY_ASSOCIATED**，Outlook 将仅返回与关联 （或隐藏） 的项相关的信息。</span><span class="sxs-lookup"><span data-stu-id="189f2-110">For example, if the client passes **SYNC_ONLY_ASSOCIATED**, Outlook will only return information related to associated (or hidden) items.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="189f2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="189f2-111">See also</span></span>



[<span data-ttu-id="189f2-112">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="189f2-112">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="189f2-113">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="189f2-113">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="189f2-114">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="189f2-114">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="189f2-115">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="189f2-115">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="189f2-116">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="189f2-116">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="189f2-117">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="189f2-117">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="189f2-118">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="189f2-118">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="189f2-119">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="189f2-119">MAPI Constants</span></span>](mapi-constants.md)

