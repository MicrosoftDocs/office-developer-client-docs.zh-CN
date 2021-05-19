---
title: UPDELE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c38aa8be-ae77-0c40-9843-42e07b80db6b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9bd61739b14d0ec382a9d582689c1049fe89429b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424880"
---
# <a name="updele"></a><span data-ttu-id="8c6b6-103">UPDELE</span><span class="sxs-lookup"><span data-stu-id="8c6b6-103">UPDELE</span></span>

<span data-ttu-id="8c6b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c6b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c6b6-105">已在本地存储中删除的项目的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-105">Extended information for items that have been deleted in a local store.</span></span> <span data-ttu-id="8c6b6-106">此信息在上载删除 [状态期间使用](upload-delete-status-state.md)。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="8c6b6-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="8c6b6-107">Quick info</span></span>

```cpp
struct UPDELE 
{ 
    ULONG ulFlags; 
    SKEY skey; 
    DWORD   dwReserved; 
    SBinary binChg; 
    SBinary binPcl; 
    SKEY skeyDst; 
    PUPMOV pupmov; 
};
```

## <a name="members"></a><span data-ttu-id="8c6b6-108">成员</span><span class="sxs-lookup"><span data-stu-id="8c6b6-108">Members</span></span>

<span data-ttu-id="8c6b6-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-109">_ulFlags_</span></span>
  
> <span data-ttu-id="8c6b6-110">[out]/[in] 用于确定上传期间适当行为的标志。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-110">[out]/[in] Flags to determine appropriate behavior during uploading.</span></span>
    
  - <span data-ttu-id="8c6b6-111">UPD_ASSOC</span><span class="sxs-lookup"><span data-stu-id="8c6b6-111">UPD_ASSOC</span></span>
    
    - <span data-ttu-id="8c6b6-112">[out]项目已关联。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-112">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="8c6b6-113">UPD_MOV</span><span class="sxs-lookup"><span data-stu-id="8c6b6-113">UPD_MOV</span></span>
    
    - <span data-ttu-id="8c6b6-114">[out]项目已移出。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-114">[out] Item was moved out.</span></span>
    
  - <span data-ttu-id="8c6b6-115">UPD_OK</span><span class="sxs-lookup"><span data-stu-id="8c6b6-115">UPD_OK</span></span> 
    
    - <span data-ttu-id="8c6b6-116">[in]Upload已成功。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-116">[in] Upload was successful.</span></span> <span data-ttu-id="8c6b6-117">客户端在将信息上载到服务器后进行设置。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-117">The client sets this after uploading information to server.</span></span>
    
  - <span data-ttu-id="8c6b6-118">UPD_MOVED</span><span class="sxs-lookup"><span data-stu-id="8c6b6-118">UPD_MOVED</span></span>
    
    - <span data-ttu-id="8c6b6-119">[in]项目已成功移动。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-119">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="8c6b6-120">UPD_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8c6b6-120">UPD_UPDATE</span></span>
    
    - <span data-ttu-id="8c6b6-121">[in]将源项目标记为已修改。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-121">[in] Mark source item as modified.</span></span>
    
  - <span data-ttu-id="8c6b6-122">UPD_COMMIT</span><span class="sxs-lookup"><span data-stu-id="8c6b6-122">UPD_COMMIT</span></span>
    
    - <span data-ttu-id="8c6b6-123">[in]提交上传状态 (项 0) 。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-123">[in] Commit upload state now (entry 0).</span></span>
    
<span data-ttu-id="8c6b6-124">_skey_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-124">_skey_</span></span>
  
> <span data-ttu-id="8c6b6-125">[out]项的源键。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-125">[out] Source key of item.</span></span>
    
<span data-ttu-id="8c6b6-126">_dwReserved_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-126">_dwReserved_</span></span>
  
> <span data-ttu-id="8c6b6-127">[传出] 保留此成员以供 Outlook 内部使用，且不支持此成员。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-127">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
<span data-ttu-id="8c6b6-128">_binChg_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-128">_binChg_</span></span>
  
> <span data-ttu-id="8c6b6-129">[out]更改目标项的键（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-129">[out] Change key of destination item if item has been moved.</span></span>
    
<span data-ttu-id="8c6b6-130">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-130">_binPcl_</span></span>
  
> <span data-ttu-id="8c6b6-131">[out]更改目标项列表（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-131">[out] Change list of destination item if item has been moved.</span></span>
    
<span data-ttu-id="8c6b6-132">_skeyDst_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-132">_skeyDst_</span></span>
  
> <span data-ttu-id="8c6b6-133">[out]目标项的源键（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-133">[out] Source key of destination item if item has been moved.</span></span>
    
<span data-ttu-id="8c6b6-134">_pupmov_</span><span class="sxs-lookup"><span data-stu-id="8c6b6-134">_pupmov_</span></span>
  
> <span data-ttu-id="8c6b6-135">[out]目标文件夹信息（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="8c6b6-135">[out] Destination folder information if item has been moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8c6b6-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c6b6-136">See also</span></span>

- [<span data-ttu-id="8c6b6-137">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="8c6b6-137">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="8c6b6-138">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="8c6b6-138">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="8c6b6-139">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="8c6b6-139">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="8c6b6-140">SKEY</span><span class="sxs-lookup"><span data-stu-id="8c6b6-140">SKEY</span></span>](skey.md)
- [<span data-ttu-id="8c6b6-141">UPDEL</span><span class="sxs-lookup"><span data-stu-id="8c6b6-141">UPDEL</span></span>](updel.md)
- [<span data-ttu-id="8c6b6-142">UPMOV</span><span class="sxs-lookup"><span data-stu-id="8c6b6-142">UPMOV</span></span>](upmov.md)

