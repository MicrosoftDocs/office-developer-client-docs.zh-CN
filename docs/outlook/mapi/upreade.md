---
title: UPREADE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d146ee74-0c3a-5fdd-b1aa-af6498550801
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 854e674002953c31c47d56096700dca582ce0a5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779065"
---
# <a name="upreade"></a><span data-ttu-id="d6777-103">UPREADE</span><span class="sxs-lookup"><span data-stu-id="d6777-103">UPREADE</span></span>

<span data-ttu-id="d6777-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d6777-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d6777-105">用于[上载读取状态状态](upload-read-status-state.md)期间上载读取项的状态的扩展的信息。</span><span class="sxs-lookup"><span data-stu-id="d6777-105">Extended information for uploading the read state of an item during the [upload read status state](upload-read-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d6777-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d6777-106">Quick info</span></span>

```cpp
struct UPREADE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
};
```

## <a name="members"></a><span data-ttu-id="d6777-107">Members</span><span class="sxs-lookup"><span data-stu-id="d6777-107">Members</span></span>

<span data-ttu-id="d6777-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="d6777-108">_ulFlags_</span></span>
  
>  <span data-ttu-id="d6777-109">[out] / [输入] 要在上载过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="d6777-109">[out]/[in] Flags to determine the appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="d6777-110">UPR_ASSOC</span><span class="sxs-lookup"><span data-stu-id="d6777-110">UPR_ASSOC</span></span>
    
    - <span data-ttu-id="d6777-111">[输出]项目处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="d6777-111">[out] Item is hidden.</span></span>
    
  - <span data-ttu-id="d6777-112">UPR_READ</span><span class="sxs-lookup"><span data-stu-id="d6777-112">UPR_READ</span></span>
    
    - <span data-ttu-id="d6777-113">[输出]已更改项目的读取的状态。</span><span class="sxs-lookup"><span data-stu-id="d6777-113">[out] The read status of the item has been changed.</span></span>
    
  - <span data-ttu-id="d6777-114">UPR_OK</span><span class="sxs-lookup"><span data-stu-id="d6777-114">UPR_OK</span></span>
    
    - <span data-ttu-id="d6777-115">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="d6777-115">[in] Upload was successful.</span></span> <span data-ttu-id="d6777-116">客户端设置此后上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="d6777-116">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="d6777-117">UPR_COMMIT</span><span class="sxs-lookup"><span data-stu-id="d6777-117">UPR_COMMIT</span></span>
    
    - <span data-ttu-id="d6777-118">[in]上载读取的项目的状态现在，而不是等待到末尾的[上载表状态](upload-table-state.md)批处理过程的多个项目。</span><span class="sxs-lookup"><span data-stu-id="d6777-118">[in] Upload the read status of the item now, instead of waiting to the end of the [upload table state](upload-table-state.md) to batch-process more than one item.</span></span> 
    
<span data-ttu-id="d6777-119">_skey_</span><span class="sxs-lookup"><span data-stu-id="d6777-119">_skey_</span></span>
  
> <span data-ttu-id="d6777-120">[输出]项目的源键。</span><span class="sxs-lookup"><span data-stu-id="d6777-120">[out] Source key of the item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d6777-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6777-121">See also</span></span>

- [<span data-ttu-id="d6777-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="d6777-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="d6777-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="d6777-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="d6777-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d6777-124">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="d6777-125">UPREAD</span><span class="sxs-lookup"><span data-stu-id="d6777-125">UPREAD</span></span>](upread.md)

