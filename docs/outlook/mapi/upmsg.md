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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338869"
---
# <a name="upmsg"></a><span data-ttu-id="36d7c-103">UPMSG</span><span class="sxs-lookup"><span data-stu-id="36d7c-103">UPMSG</span></span>

<span data-ttu-id="36d7c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36d7c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36d7c-105">[上载邮件状态](upload-message-state.md)期间上载 Outlook 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="36d7c-105">Information for uploading an Outlook item during the [upload message state](upload-message-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="36d7c-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="36d7c-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="36d7c-107">成员</span><span class="sxs-lookup"><span data-stu-id="36d7c-107">Members</span></span>

 <span data-ttu-id="36d7c-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="36d7c-108">_ulFlags_</span></span>
  
> <span data-ttu-id="36d7c-109">[输出]/[in] 标志以确定上载过程中的相应行为。</span><span class="sxs-lookup"><span data-stu-id="36d7c-109">[out]/[in] Flags to determine appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="36d7c-110">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="36d7c-110">UPM_ASSOC</span></span>
    
    - <span data-ttu-id="36d7c-111">排除项目相关联。</span><span class="sxs-lookup"><span data-stu-id="36d7c-111">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="36d7c-112">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="36d7c-112">UPM_NEW</span></span>
    
    - <span data-ttu-id="36d7c-113">排除新项目。</span><span class="sxs-lookup"><span data-stu-id="36d7c-113">[out] New item.</span></span> 
    
  - <span data-ttu-id="36d7c-114">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="36d7c-114">UPM_MOV</span></span>
    
    - <span data-ttu-id="36d7c-115">排除项目已移至此处。</span><span class="sxs-lookup"><span data-stu-id="36d7c-115">[out] Item was moved here.</span></span>
    
  - <span data-ttu-id="36d7c-116">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="36d7c-116">UPM_MOD_PROPS</span></span>
    
    - <span data-ttu-id="36d7c-117">排除修改了项目属性。</span><span class="sxs-lookup"><span data-stu-id="36d7c-117">[out] Item properties were modified.</span></span>
    
  - <span data-ttu-id="36d7c-118">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="36d7c-118">UPM_HEADER</span></span>
    
    - <span data-ttu-id="36d7c-119">排除Item 为邮件头。</span><span class="sxs-lookup"><span data-stu-id="36d7c-119">[out] Item is a message header.</span></span>
    
  - <span data-ttu-id="36d7c-120">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="36d7c-120">UPM_OK</span></span>
    
    - <span data-ttu-id="36d7c-121">实时上载成功。</span><span class="sxs-lookup"><span data-stu-id="36d7c-121">[in] Upload was successful.</span></span> <span data-ttu-id="36d7c-122">客户端将信息上载到服务器后对此进行设置。</span><span class="sxs-lookup"><span data-stu-id="36d7c-122">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="36d7c-123">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="36d7c-123">UPM_MOVED</span></span>
    
    - <span data-ttu-id="36d7c-124">实时已成功移动项目。</span><span class="sxs-lookup"><span data-stu-id="36d7c-124">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="36d7c-125">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="36d7c-125">UPM_COMMIT</span></span>
    
    - <span data-ttu-id="36d7c-126">实时立即提交上载状态。</span><span class="sxs-lookup"><span data-stu-id="36d7c-126">[in] Commit upload state now.</span></span>
    
  - <span data-ttu-id="36d7c-127">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="36d7c-127">UPM_DELETE</span></span>
    
    - <span data-ttu-id="36d7c-128">实时立即删除项目。</span><span class="sxs-lookup"><span data-stu-id="36d7c-128">[in] Delete item now.</span></span>
    
  - <span data-ttu-id="36d7c-129">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="36d7c-129">UPM_SAVE</span></span>
    
    - <span data-ttu-id="36d7c-130">实时保存对项目所做的更改。</span><span class="sxs-lookup"><span data-stu-id="36d7c-130">[in] Save changes to the item.</span></span>
    
<span data-ttu-id="36d7c-131">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="36d7c-131">_pmsg_</span></span>
  
> <span data-ttu-id="36d7c-132">排除打开项目对象。</span><span class="sxs-lookup"><span data-stu-id="36d7c-132">[out] Open item object.</span></span> <span data-ttu-id="36d7c-133">有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="36d7c-133">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
<span data-ttu-id="36d7c-134">_meid_</span><span class="sxs-lookup"><span data-stu-id="36d7c-134">_meid_</span></span>
  
> <span data-ttu-id="36d7c-135">排除项目的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="36d7c-135">[out] Entry ID of item.</span></span>
    
<span data-ttu-id="36d7c-136">_binReserved1_</span><span class="sxs-lookup"><span data-stu-id="36d7c-136">_binReserved1_</span></span>
  
> <span data-ttu-id="36d7c-137">实时此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="36d7c-137">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="36d7c-138">_binReserved2_</span><span class="sxs-lookup"><span data-stu-id="36d7c-138">_binReserved2_</span></span>
  
> <span data-ttu-id="36d7c-139">实时此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="36d7c-139">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="36d7c-140">_feid_</span><span class="sxs-lookup"><span data-stu-id="36d7c-140">_feid_</span></span>
  
> <span data-ttu-id="36d7c-141">排除源文件夹的条目 ID (如果已移动项目)。</span><span class="sxs-lookup"><span data-stu-id="36d7c-141">[out] Entry ID of the source folder, if item was moved.</span></span>
    
<span data-ttu-id="36d7c-142">_binChg_</span><span class="sxs-lookup"><span data-stu-id="36d7c-142">_binChg_</span></span>
  
> <span data-ttu-id="36d7c-143">排除如果已移动项, 则更改目标项的键。</span><span class="sxs-lookup"><span data-stu-id="36d7c-143">[out] Change key of the destination item, if item was moved.</span></span> <span data-ttu-id="36d7c-144">有关**SBinary**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="36d7c-144">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="36d7c-145">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="36d7c-145">_binPcl_</span></span>
  
> <span data-ttu-id="36d7c-146">排除如果项目已移动, 则更改目标项的列表。</span><span class="sxs-lookup"><span data-stu-id="36d7c-146">[out] Change list of the destination item, if item was moved.</span></span> <span data-ttu-id="36d7c-147">有关**SBinary**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="36d7c-147">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="36d7c-148">_skeySrc_</span><span class="sxs-lookup"><span data-stu-id="36d7c-148">_skeySrc_</span></span>
  
> <span data-ttu-id="36d7c-149">排除源项的源项 (如果已移动项)。</span><span class="sxs-lookup"><span data-stu-id="36d7c-149">[out] Source key of the source item, if item was moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="36d7c-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36d7c-150">See also</span></span>

- [<span data-ttu-id="36d7c-151">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="36d7c-151">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="36d7c-152">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="36d7c-152">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="36d7c-153">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="36d7c-153">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="36d7c-154">FEID</span><span class="sxs-lookup"><span data-stu-id="36d7c-154">FEID</span></span>](feid.md)
- [<span data-ttu-id="36d7c-155">MEID</span><span class="sxs-lookup"><span data-stu-id="36d7c-155">MEID</span></span>](meid.md)
- [<span data-ttu-id="36d7c-156">SKEY</span><span class="sxs-lookup"><span data-stu-id="36d7c-156">SKEY</span></span>](skey.md)

