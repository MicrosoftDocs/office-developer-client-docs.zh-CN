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
ms.openlocfilehash: fd593b68ef7ca25b1f8ceec613786cdbdd03fd76
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579072"
---
# <a name="upreade"></a><span data-ttu-id="3bf85-103">UPREADE</span><span class="sxs-lookup"><span data-stu-id="3bf85-103">UPREADE</span></span>

<span data-ttu-id="3bf85-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3bf85-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3bf85-105">用于[上载读取状态状态](upload-read-status-state.md)期间上载读取项的状态的扩展的信息。</span><span class="sxs-lookup"><span data-stu-id="3bf85-105">Extended information for uploading the read state of an item during the [upload read status state](upload-read-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="3bf85-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="3bf85-106">Quick info</span></span>

```cpp
struct UPREADE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
};
```

## <a name="members"></a><span data-ttu-id="3bf85-107">Members</span><span class="sxs-lookup"><span data-stu-id="3bf85-107">Members</span></span>

<span data-ttu-id="3bf85-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3bf85-108">_ulFlags_</span></span>
  
>  <span data-ttu-id="3bf85-109">[out] / [输入] 要在上载过程中确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="3bf85-109">[out]/[in] Flags to determine the appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="3bf85-110">UPR_ASSOC</span><span class="sxs-lookup"><span data-stu-id="3bf85-110">UPR_ASSOC</span></span>
    
    - <span data-ttu-id="3bf85-111">[输出]项目处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="3bf85-111">[out] Item is hidden.</span></span>
    
  - <span data-ttu-id="3bf85-112">UPR_READ</span><span class="sxs-lookup"><span data-stu-id="3bf85-112">UPR_READ</span></span>
    
    - <span data-ttu-id="3bf85-113">[输出]已更改项目的读取的状态。</span><span class="sxs-lookup"><span data-stu-id="3bf85-113">[out] The read status of the item has been changed.</span></span>
    
  - <span data-ttu-id="3bf85-114">UPR_OK</span><span class="sxs-lookup"><span data-stu-id="3bf85-114">UPR_OK</span></span>
    
    - <span data-ttu-id="3bf85-115">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="3bf85-115">[in] Upload was successful.</span></span> <span data-ttu-id="3bf85-116">客户端设置此后上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="3bf85-116">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="3bf85-117">UPR_COMMIT</span><span class="sxs-lookup"><span data-stu-id="3bf85-117">UPR_COMMIT</span></span>
    
    - <span data-ttu-id="3bf85-118">[in]上载读取的项目的状态现在，而不是等待到末尾的[上载表状态](upload-table-state.md)批处理过程的多个项目。</span><span class="sxs-lookup"><span data-stu-id="3bf85-118">[in] Upload the read status of the item now, instead of waiting to the end of the [upload table state](upload-table-state.md) to batch-process more than one item.</span></span> 
    
<span data-ttu-id="3bf85-119">_skey_</span><span class="sxs-lookup"><span data-stu-id="3bf85-119">_skey_</span></span>
  
> <span data-ttu-id="3bf85-120">[输出]项目的源键。</span><span class="sxs-lookup"><span data-stu-id="3bf85-120">[out] Source key of the item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3bf85-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bf85-121">See also</span></span>

- [<span data-ttu-id="3bf85-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="3bf85-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="3bf85-123">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="3bf85-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="3bf85-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3bf85-124">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="3bf85-125">UPREAD</span><span class="sxs-lookup"><span data-stu-id="3bf85-125">UPREAD</span></span>](upread.md)

