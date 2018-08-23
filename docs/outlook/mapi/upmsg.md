---
title: UPMSG
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5fe3956b-819a-3edf-0e49-7a44bcfbabcd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa8b84e7baed74bda25ec1b20bd79fb121a838fd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587570"
---
# <a name="upmsg"></a><span data-ttu-id="0c7bf-103">UPMSG</span><span class="sxs-lookup"><span data-stu-id="0c7bf-103">UPMSG</span></span>

<span data-ttu-id="0c7bf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c7bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c7bf-105">用于[上载邮件状态](upload-message-state.md)期间上载 Outlook 项目的信息。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-105">Information for uploading an Outlook item during the [upload message state](upload-message-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="0c7bf-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="0c7bf-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="0c7bf-107">Members</span><span class="sxs-lookup"><span data-stu-id="0c7bf-107">Members</span></span>

 <span data-ttu-id="0c7bf-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-108">_ulFlags_</span></span>
  
> <span data-ttu-id="0c7bf-109">[out] / [输入] 要上载期间确定适当的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-109">[out]/[in] Flags to determine appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="0c7bf-110">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="0c7bf-110">UPM_ASSOC</span></span>
    
    - <span data-ttu-id="0c7bf-111">[输出]项目相关联。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-111">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="0c7bf-112">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="0c7bf-112">UPM_NEW</span></span>
    
    - <span data-ttu-id="0c7bf-113">[输出]新项目。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-113">[out] New item.</span></span> 
    
  - <span data-ttu-id="0c7bf-114">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="0c7bf-114">UPM_MOV</span></span>
    
    - <span data-ttu-id="0c7bf-115">[输出]项目已移至此处。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-115">[out] Item was moved here.</span></span>
    
  - <span data-ttu-id="0c7bf-116">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="0c7bf-116">UPM_MOD_PROPS</span></span>
    
    - <span data-ttu-id="0c7bf-117">[输出]修改项目属性。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-117">[out] Item properties were modified.</span></span>
    
  - <span data-ttu-id="0c7bf-118">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="0c7bf-118">UPM_HEADER</span></span>
    
    - <span data-ttu-id="0c7bf-119">[输出]Item 是邮件头。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-119">[out] Item is a message header.</span></span>
    
  - <span data-ttu-id="0c7bf-120">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="0c7bf-120">UPM_OK</span></span>
    
    - <span data-ttu-id="0c7bf-121">[in]上载成功。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-121">[in] Upload was successful.</span></span> <span data-ttu-id="0c7bf-122">客户端设置此后上载到服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-122">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="0c7bf-123">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="0c7bf-123">UPM_MOVED</span></span>
    
    - <span data-ttu-id="0c7bf-124">[in]项目已成功移动。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-124">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="0c7bf-125">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="0c7bf-125">UPM_COMMIT</span></span>
    
    - <span data-ttu-id="0c7bf-126">[in]现在提交上载状态。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-126">[in] Commit upload state now.</span></span>
    
  - <span data-ttu-id="0c7bf-127">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="0c7bf-127">UPM_DELETE</span></span>
    
    - <span data-ttu-id="0c7bf-128">[in]现在将删除项目。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-128">[in] Delete item now.</span></span>
    
  - <span data-ttu-id="0c7bf-129">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="0c7bf-129">UPM_SAVE</span></span>
    
    - <span data-ttu-id="0c7bf-130">[in]将更改保存到项目中。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-130">[in] Save changes to the item.</span></span>
    
<span data-ttu-id="0c7bf-131">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-131">_pmsg_</span></span>
  
> <span data-ttu-id="0c7bf-132">[输出]打开项目对象。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-132">[out] Open item object.</span></span> <span data-ttu-id="0c7bf-133">请参阅 mapidefs.h **LPMESSAGE**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-133">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
<span data-ttu-id="0c7bf-134">_meid_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-134">_meid_</span></span>
  
> <span data-ttu-id="0c7bf-135">[输出]项目的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-135">[out] Entry ID of item.</span></span>
    
<span data-ttu-id="0c7bf-136">_binReserved1_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-136">_binReserved1_</span></span>
  
> <span data-ttu-id="0c7bf-137">[in]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-137">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="0c7bf-138">_binReserved2_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-138">_binReserved2_</span></span>
  
> <span data-ttu-id="0c7bf-139">[in]此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-139">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="0c7bf-140">_feid_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-140">_feid_</span></span>
  
> <span data-ttu-id="0c7bf-141">[输出]源文件夹，如果项目被移条目 ID。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-141">[out] Entry ID of the source folder, if item was moved.</span></span>
    
<span data-ttu-id="0c7bf-142">_binChg_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-142">_binChg_</span></span>
  
> <span data-ttu-id="0c7bf-143">[输出]如果项目被移，更改的目标项，键。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-143">[out] Change key of the destination item, if item was moved.</span></span> <span data-ttu-id="0c7bf-144">请参阅 mapidefs.h **SBinary**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-144">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="0c7bf-145">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-145">_binPcl_</span></span>
  
> <span data-ttu-id="0c7bf-146">[输出]如果项目被移，更改目标项，的列表。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-146">[out] Change list of the destination item, if item was moved.</span></span> <span data-ttu-id="0c7bf-147">请参阅 mapidefs.h **SBinary**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-147">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="0c7bf-148">_skeySrc_</span><span class="sxs-lookup"><span data-stu-id="0c7bf-148">_skeySrc_</span></span>
  
> <span data-ttu-id="0c7bf-149">[输出]如果项目被移源该项的源键。</span><span class="sxs-lookup"><span data-stu-id="0c7bf-149">[out] Source key of the source item, if item was moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c7bf-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c7bf-150">See also</span></span>

- [<span data-ttu-id="0c7bf-151">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="0c7bf-151">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="0c7bf-152">关于复制状态计算机</span><span class="sxs-lookup"><span data-stu-id="0c7bf-152">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="0c7bf-153">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="0c7bf-153">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="0c7bf-154">FEID</span><span class="sxs-lookup"><span data-stu-id="0c7bf-154">FEID</span></span>](feid.md)
- [<span data-ttu-id="0c7bf-155">MEID</span><span class="sxs-lookup"><span data-stu-id="0c7bf-155">MEID</span></span>](meid.md)
- [<span data-ttu-id="0c7bf-156">SKEY</span><span class="sxs-lookup"><span data-stu-id="0c7bf-156">SKEY</span></span>](skey.md)

