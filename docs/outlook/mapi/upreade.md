---
title: UPREADE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d146ee74-0c3a-5fdd-b1aa-af6498550801
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1df2c665f8e9d7a0bd6d47ec59b2adf706bead75
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434142"
---
# <a name="upreade"></a><span data-ttu-id="84b68-103">UPREADE</span><span class="sxs-lookup"><span data-stu-id="84b68-103">UPREADE</span></span>

<span data-ttu-id="84b68-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="84b68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="84b68-105">用于在[上载读取状态状态](upload-read-status-state.md)期间上载项目的读取状态的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="84b68-105">Extended information for uploading the read state of an item during the [upload read status state](upload-read-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="84b68-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="84b68-106">Quick info</span></span>

```cpp
struct UPREADE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
};
```

## <a name="members"></a><span data-ttu-id="84b68-107">成员</span><span class="sxs-lookup"><span data-stu-id="84b68-107">Members</span></span>

<span data-ttu-id="84b68-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="84b68-108">_ulFlags_</span></span>
  
>  <span data-ttu-id="84b68-109">[输出]/[in] 标志, 以确定在上载过程中的相应行为。</span><span class="sxs-lookup"><span data-stu-id="84b68-109">[out]/[in] Flags to determine the appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="84b68-110">UPR_ASSOC</span><span class="sxs-lookup"><span data-stu-id="84b68-110">UPR_ASSOC</span></span>
    
    - <span data-ttu-id="84b68-111">排除项目已隐藏。</span><span class="sxs-lookup"><span data-stu-id="84b68-111">[out] Item is hidden.</span></span>
    
  - <span data-ttu-id="84b68-112">UPR_READ</span><span class="sxs-lookup"><span data-stu-id="84b68-112">UPR_READ</span></span>
    
    - <span data-ttu-id="84b68-113">排除项目的读取状态已更改。</span><span class="sxs-lookup"><span data-stu-id="84b68-113">[out] The read status of the item has been changed.</span></span>
    
  - <span data-ttu-id="84b68-114">UPR_OK</span><span class="sxs-lookup"><span data-stu-id="84b68-114">UPR_OK</span></span>
    
    - <span data-ttu-id="84b68-115">实时上载成功。</span><span class="sxs-lookup"><span data-stu-id="84b68-115">[in] Upload was successful.</span></span> <span data-ttu-id="84b68-116">客户端将信息上载到服务器后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="84b68-116">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="84b68-117">UPR_COMMIT</span><span class="sxs-lookup"><span data-stu-id="84b68-117">UPR_COMMIT</span></span>
    
    - <span data-ttu-id="84b68-118">实时立即上载项目的读取状态, 而不是等待[上载表状态](upload-table-state.md)的末尾, 以批处理的多个项目。</span><span class="sxs-lookup"><span data-stu-id="84b68-118">[in] Upload the read status of the item now, instead of waiting to the end of the [upload table state](upload-table-state.md) to batch-process more than one item.</span></span> 
    
<span data-ttu-id="84b68-119">_skey_</span><span class="sxs-lookup"><span data-stu-id="84b68-119">_skey_</span></span>
  
> <span data-ttu-id="84b68-120">排除项的源键。</span><span class="sxs-lookup"><span data-stu-id="84b68-120">[out] Source key of the item.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="84b68-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84b68-121">See also</span></span>

- [<span data-ttu-id="84b68-122">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="84b68-122">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="84b68-123">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="84b68-123">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="84b68-124">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="84b68-124">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="84b68-125">UPREAD</span><span class="sxs-lookup"><span data-stu-id="84b68-125">UPREAD</span></span>](upread.md)

