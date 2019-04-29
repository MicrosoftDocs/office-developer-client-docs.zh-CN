---
title: UPMSG
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5fe3956b-819a-3edf-0e49-7a44bcfbabcd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1e0e2f9b794c4cee25488a754290922e58b7658d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427267"
---
# <a name="upmsg"></a><span data-ttu-id="5764e-103">UPMSG</span><span class="sxs-lookup"><span data-stu-id="5764e-103">UPMSG</span></span>

<span data-ttu-id="5764e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5764e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5764e-105">[上载邮件状态](upload-message-state.md)期间上载 Outlook 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="5764e-105">Information for uploading an Outlook item during the [upload message state](upload-message-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5764e-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="5764e-106">Quick info</span></span>

```cpp
struct UPMSG 
{ 
    ULONG ulFlags; 
    LPMESSAGE pmsg; 
    MEID meid; 
    SBinary binReserved1; 
    SBinary binReserved2; 
    FEID feid; 
    SBinary binChg; 
    SBinary binPcl; 
    SKEY skeySrc; 
};
```

## <a name="members"></a><span data-ttu-id="5764e-107">成员</span><span class="sxs-lookup"><span data-stu-id="5764e-107">Members</span></span>

 <span data-ttu-id="5764e-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="5764e-108">_ulFlags_</span></span>
  
> <span data-ttu-id="5764e-109">[输出]/[in] 标志以确定上载过程中的相应行为。</span><span class="sxs-lookup"><span data-stu-id="5764e-109">[out]/[in] Flags to determine appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="5764e-110">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="5764e-110">UPM_ASSOC</span></span>
    
    - <span data-ttu-id="5764e-111">排除项目相关联。</span><span class="sxs-lookup"><span data-stu-id="5764e-111">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="5764e-112">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="5764e-112">UPM_NEW</span></span>
    
    - <span data-ttu-id="5764e-113">排除新项目。</span><span class="sxs-lookup"><span data-stu-id="5764e-113">[out] New item.</span></span> 
    
  - <span data-ttu-id="5764e-114">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="5764e-114">UPM_MOV</span></span>
    
    - <span data-ttu-id="5764e-115">排除项目已移至此处。</span><span class="sxs-lookup"><span data-stu-id="5764e-115">[out] Item was moved here.</span></span>
    
  - <span data-ttu-id="5764e-116">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="5764e-116">UPM_MOD_PROPS</span></span>
    
    - <span data-ttu-id="5764e-117">排除修改了项目属性。</span><span class="sxs-lookup"><span data-stu-id="5764e-117">[out] Item properties were modified.</span></span>
    
  - <span data-ttu-id="5764e-118">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="5764e-118">UPM_HEADER</span></span>
    
    - <span data-ttu-id="5764e-119">排除Item 为邮件头。</span><span class="sxs-lookup"><span data-stu-id="5764e-119">[out] Item is a message header.</span></span>
    
  - <span data-ttu-id="5764e-120">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="5764e-120">UPM_OK</span></span>
    
    - <span data-ttu-id="5764e-121">实时上载成功。</span><span class="sxs-lookup"><span data-stu-id="5764e-121">[in] Upload was successful.</span></span> <span data-ttu-id="5764e-122">客户端将信息上载到服务器后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="5764e-122">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="5764e-123">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="5764e-123">UPM_MOVED</span></span>
    
    - <span data-ttu-id="5764e-124">实时已成功移动项目。</span><span class="sxs-lookup"><span data-stu-id="5764e-124">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="5764e-125">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="5764e-125">UPM_COMMIT</span></span>
    
    - <span data-ttu-id="5764e-126">实时立即提交上载状态。</span><span class="sxs-lookup"><span data-stu-id="5764e-126">[in] Commit upload state now.</span></span>
    
  - <span data-ttu-id="5764e-127">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="5764e-127">UPM_DELETE</span></span>
    
    - <span data-ttu-id="5764e-128">实时立即删除项目。</span><span class="sxs-lookup"><span data-stu-id="5764e-128">[in] Delete item now.</span></span>
    
  - <span data-ttu-id="5764e-129">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="5764e-129">UPM_SAVE</span></span>
    
    - <span data-ttu-id="5764e-130">实时保存对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5764e-130">[in] Save changes to the item.</span></span>
    
<span data-ttu-id="5764e-131">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="5764e-131">_pmsg_</span></span>
  
> <span data-ttu-id="5764e-132">排除打开项目对象。</span><span class="sxs-lookup"><span data-stu-id="5764e-132">[out] Open item object.</span></span> <span data-ttu-id="5764e-133">有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="5764e-133">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
<span data-ttu-id="5764e-134">_meid_</span><span class="sxs-lookup"><span data-stu-id="5764e-134">_meid_</span></span>
  
> <span data-ttu-id="5764e-135">排除项目的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="5764e-135">[out] Entry ID of item.</span></span>
    
<span data-ttu-id="5764e-136">_binReserved1_</span><span class="sxs-lookup"><span data-stu-id="5764e-136">_binReserved1_</span></span>
  
> <span data-ttu-id="5764e-137">实时此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="5764e-137">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="5764e-138">_binReserved2_</span><span class="sxs-lookup"><span data-stu-id="5764e-138">_binReserved2_</span></span>
  
> <span data-ttu-id="5764e-139">实时此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="5764e-139">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="5764e-140">_feid_</span><span class="sxs-lookup"><span data-stu-id="5764e-140">_feid_</span></span>
  
> <span data-ttu-id="5764e-141">排除源文件夹的条目 ID (如果已移动项目)。</span><span class="sxs-lookup"><span data-stu-id="5764e-141">[out] Entry ID of the source folder, if item was moved.</span></span>
    
<span data-ttu-id="5764e-142">_binChg_</span><span class="sxs-lookup"><span data-stu-id="5764e-142">_binChg_</span></span>
  
> <span data-ttu-id="5764e-143">排除如果已移动项, 则更改目标项的键。</span><span class="sxs-lookup"><span data-stu-id="5764e-143">[out] Change key of the destination item, if item was moved.</span></span> <span data-ttu-id="5764e-144">有关**SBinary**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="5764e-144">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="5764e-145">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="5764e-145">_binPcl_</span></span>
  
> <span data-ttu-id="5764e-146">排除如果项目已移动, 则更改目标项的列表。</span><span class="sxs-lookup"><span data-stu-id="5764e-146">[out] Change list of the destination item, if item was moved.</span></span> <span data-ttu-id="5764e-147">有关**SBinary**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="5764e-147">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="5764e-148">_skeySrc_</span><span class="sxs-lookup"><span data-stu-id="5764e-148">_skeySrc_</span></span>
  
> <span data-ttu-id="5764e-149">排除源项的源项 (如果已移动项)。</span><span class="sxs-lookup"><span data-stu-id="5764e-149">[out] Source key of the source item, if item was moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5764e-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5764e-150">See also</span></span>

- [<span data-ttu-id="5764e-151">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="5764e-151">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="5764e-152">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="5764e-152">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="5764e-153">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="5764e-153">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="5764e-154">FEID</span><span class="sxs-lookup"><span data-stu-id="5764e-154">FEID</span></span>](feid.md)
- [<span data-ttu-id="5764e-155">MEID</span><span class="sxs-lookup"><span data-stu-id="5764e-155">MEID</span></span>](meid.md)
- [<span data-ttu-id="5764e-156">SKEY</span><span class="sxs-lookup"><span data-stu-id="5764e-156">SKEY</span></span>](skey.md)

