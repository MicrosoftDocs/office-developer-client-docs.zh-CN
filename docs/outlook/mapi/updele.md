---
title: UPDELE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c38aa8be-ae77-0c40-9843-42e07b80db6b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2361d225c07d60fab40465b27ad393ca10f6d8eb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566584"
---
# <a name="updele"></a><span data-ttu-id="2bc36-103">UPDELE</span><span class="sxs-lookup"><span data-stu-id="2bc36-103">UPDELE</span></span>

<span data-ttu-id="2bc36-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2bc36-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2bc36-105">扩展的本地存储区中已被删除的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="2bc36-105">Extended information for items that have been deleted in a local store.</span></span> <span data-ttu-id="2bc36-106">[上载删除状态状态](upload-delete-status-state.md)期间使用此信息。</span><span class="sxs-lookup"><span data-stu-id="2bc36-106">This information is used during the [upload delete status state](upload-delete-status-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2bc36-107">快速信息</span><span class="sxs-lookup"><span data-stu-id="2bc36-107">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="2bc36-108">Members</span><span class="sxs-lookup"><span data-stu-id="2bc36-108">Members</span></span>

<span data-ttu-id="2bc36-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2bc36-109">_ulFlags_</span></span>
  
> <span data-ttu-id="2bc36-110">[out] / [输入] 要上载期间确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="2bc36-110">[out]/[in] Flags to determine appropriate behavior during uploading.</span></span>
    
  - <span data-ttu-id="2bc36-111">UPD_ASSOC</span><span class="sxs-lookup"><span data-stu-id="2bc36-111">UPD_ASSOC</span></span>
    
    - <span data-ttu-id="2bc36-112">[输出]项目相关联。</span><span class="sxs-lookup"><span data-stu-id="2bc36-112">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="2bc36-113">UPD_MOV</span><span class="sxs-lookup"><span data-stu-id="2bc36-113">UPD_MOV</span></span>
    
    - <span data-ttu-id="2bc36-114">[输出]项目被移。</span><span class="sxs-lookup"><span data-stu-id="2bc36-114">[out] Item was moved out.</span></span>
    
  - <span data-ttu-id="2bc36-115">UPD_OK</span><span class="sxs-lookup"><span data-stu-id="2bc36-115">UPD_OK</span></span> 
    
    - <span data-ttu-id="2bc36-116">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="2bc36-116">[in] Upload was successful.</span></span> <span data-ttu-id="2bc36-117">客户端设置后将上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="2bc36-117">The client sets this after uploading information to server.</span></span>
    
  - <span data-ttu-id="2bc36-118">UPD_MOVED</span><span class="sxs-lookup"><span data-stu-id="2bc36-118">UPD_MOVED</span></span>
    
    - <span data-ttu-id="2bc36-119">[in]项目已成功移动。</span><span class="sxs-lookup"><span data-stu-id="2bc36-119">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="2bc36-120">UPD_UPDATE</span><span class="sxs-lookup"><span data-stu-id="2bc36-120">UPD_UPDATE</span></span>
    
    - <span data-ttu-id="2bc36-121">[in]标记源项的修改。</span><span class="sxs-lookup"><span data-stu-id="2bc36-121">[in] Mark source item as modified.</span></span>
    
  - <span data-ttu-id="2bc36-122">UPD_COMMIT</span><span class="sxs-lookup"><span data-stu-id="2bc36-122">UPD_COMMIT</span></span>
    
    - <span data-ttu-id="2bc36-123">[in]提交现在上载状态 （输入 0）。</span><span class="sxs-lookup"><span data-stu-id="2bc36-123">[in] Commit upload state now (entry 0).</span></span>
    
<span data-ttu-id="2bc36-124">_skey_</span><span class="sxs-lookup"><span data-stu-id="2bc36-124">_skey_</span></span>
  
> <span data-ttu-id="2bc36-125">[输出]项目的源键。</span><span class="sxs-lookup"><span data-stu-id="2bc36-125">[out] Source key of item.</span></span>
    
<span data-ttu-id="2bc36-126">_dwReserved_</span><span class="sxs-lookup"><span data-stu-id="2bc36-126">_dwReserved_</span></span>
  
> <span data-ttu-id="2bc36-127">[输出]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="2bc36-127">[out] This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
<span data-ttu-id="2bc36-128">_binChg_</span><span class="sxs-lookup"><span data-stu-id="2bc36-128">_binChg_</span></span>
  
> <span data-ttu-id="2bc36-129">[输出]如果项目已移动，请更改目标项键。</span><span class="sxs-lookup"><span data-stu-id="2bc36-129">[out] Change key of destination item if item has been moved.</span></span>
    
<span data-ttu-id="2bc36-130">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="2bc36-130">_binPcl_</span></span>
  
> <span data-ttu-id="2bc36-131">[输出]如果已移动项目，更改目标项的列表。</span><span class="sxs-lookup"><span data-stu-id="2bc36-131">[out] Change list of destination item if item has been moved.</span></span>
    
<span data-ttu-id="2bc36-132">_skeyDst_</span><span class="sxs-lookup"><span data-stu-id="2bc36-132">_skeyDst_</span></span>
  
> <span data-ttu-id="2bc36-133">[输出]如果项目的目标项源键已移动。</span><span class="sxs-lookup"><span data-stu-id="2bc36-133">[out] Source key of destination item if item has been moved.</span></span>
    
<span data-ttu-id="2bc36-134">_pupmov_</span><span class="sxs-lookup"><span data-stu-id="2bc36-134">_pupmov_</span></span>
  
> <span data-ttu-id="2bc36-135">[输出]目标文件夹信息如果项目已被移动。</span><span class="sxs-lookup"><span data-stu-id="2bc36-135">[out] Destination folder information if item has been moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2bc36-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bc36-136">See also</span></span>

- [<span data-ttu-id="2bc36-137">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="2bc36-137">About the Replication API</span></span>](about-the-replication-api.md) 
- [<span data-ttu-id="2bc36-138">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="2bc36-138">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="2bc36-139">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2bc36-139">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="2bc36-140">SKEY</span><span class="sxs-lookup"><span data-stu-id="2bc36-140">SKEY</span></span>](skey.md)
- [<span data-ttu-id="2bc36-141">UPDEL</span><span class="sxs-lookup"><span data-stu-id="2bc36-141">UPDEL</span></span>](updel.md)
- [<span data-ttu-id="2bc36-142">UPMOV</span><span class="sxs-lookup"><span data-stu-id="2bc36-142">UPMOV</span></span>](upmov.md)

