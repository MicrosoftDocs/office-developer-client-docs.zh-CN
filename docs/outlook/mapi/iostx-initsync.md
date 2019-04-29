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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b9086383b45d40d5839284ac785d72438be60e00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413351"
---
# <a name="iostxinitsync"></a><span data-ttu-id="b6232-103">IOSTX::InitSync</span><span class="sxs-lookup"><span data-stu-id="b6232-103">IOSTX::InitSync</span></span>

  
  
<span data-ttu-id="b6232-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6232-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6232-105">通知本地邮件存储区同步即将启动。</span><span class="sxs-lookup"><span data-stu-id="b6232-105">Informs the local message store that synchronization is about to start.</span></span>
  
```cpp
HRESULT InitSync( 
    ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="b6232-106">参数</span><span class="sxs-lookup"><span data-stu-id="b6232-106">Parameters</span></span>

 <span data-ttu-id="b6232-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b6232-107">_ulFlags_</span></span>
  
> <span data-ttu-id="b6232-108">实时用于确定同步过程中的适当行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b6232-108">[in] Flags to determine appropriate behavior during synchronization.</span></span> <span data-ttu-id="b6232-109">Outlook 在复制状态机的每个状态中使用这些标志来确定它应为客户端提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b6232-109">Outlook uses these flags in each state of the replication state machine to determine the information that it should provide for the client.</span></span> <span data-ttu-id="b6232-110">例如, 如果客户端传递**SYNC_ONLY_ASSOCIATED**, 则 Outlook 将仅返回与关联 (或隐藏) 项目相关的信息。</span><span class="sxs-lookup"><span data-stu-id="b6232-110">For example, if the client passes **SYNC_ONLY_ASSOCIATED**, Outlook will only return information related to associated (or hidden) items.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="b6232-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6232-111">See also</span></span>



[<span data-ttu-id="b6232-112">IOSTX::GetLastError</span><span class="sxs-lookup"><span data-stu-id="b6232-112">IOSTX::GetLastError</span></span>](iostx-getlasterror.md)
  
[<span data-ttu-id="b6232-113">IOSTX::SetSyncResult</span><span class="sxs-lookup"><span data-stu-id="b6232-113">IOSTX::SetSyncResult</span></span>](iostx-setsyncresult.md)
  
[<span data-ttu-id="b6232-114">IOSTX::SyncBeg</span><span class="sxs-lookup"><span data-stu-id="b6232-114">IOSTX::SyncBeg</span></span>](iostx-syncbeg.md)
  
[<span data-ttu-id="b6232-115">IOSTX::SyncEnd</span><span class="sxs-lookup"><span data-stu-id="b6232-115">IOSTX::SyncEnd</span></span>](iostx-syncend.md)
  
[<span data-ttu-id="b6232-116">IOSTX::SyncHdrBeg</span><span class="sxs-lookup"><span data-stu-id="b6232-116">IOSTX::SyncHdrBeg</span></span>](iostx-synchdrbeg.md)
  
[<span data-ttu-id="b6232-117">IOSTX::SyncHdrEnd</span><span class="sxs-lookup"><span data-stu-id="b6232-117">IOSTX::SyncHdrEnd</span></span>](iostx-synchdrend.md)
  
[<span data-ttu-id="b6232-118">IOSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6232-118">IOSTX : IUnknown</span></span>](iostxiunknown.md)


[<span data-ttu-id="b6232-119">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b6232-119">MAPI Constants</span></span>](mapi-constants.md)

