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
# <a name="upmsg"></a><span data-ttu-id="b1942-103">UPMSG</span><span class="sxs-lookup"><span data-stu-id="b1942-103">UPMSG</span></span>

<span data-ttu-id="b1942-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1942-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1942-105">上传邮件状态Outlook[上传项目的信息](upload-message-state.md)。</span><span class="sxs-lookup"><span data-stu-id="b1942-105">Information for uploading an Outlook item during the [upload message state](upload-message-state.md).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="b1942-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="b1942-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="b1942-107">成员</span><span class="sxs-lookup"><span data-stu-id="b1942-107">Members</span></span>

 <span data-ttu-id="b1942-108">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b1942-108">_ulFlags_</span></span>
  
> <span data-ttu-id="b1942-109">[out]/[in] 用于确定上传期间适当行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b1942-109">[out]/[in] Flags to determine appropriate behavior during the upload.</span></span> 
    
  - <span data-ttu-id="b1942-110">UPM_ASSOC</span><span class="sxs-lookup"><span data-stu-id="b1942-110">UPM_ASSOC</span></span>
    
    - <span data-ttu-id="b1942-111">[out]项目已关联。</span><span class="sxs-lookup"><span data-stu-id="b1942-111">[out] Item is associated.</span></span>
    
  - <span data-ttu-id="b1942-112">UPM_NEW</span><span class="sxs-lookup"><span data-stu-id="b1942-112">UPM_NEW</span></span>
    
    - <span data-ttu-id="b1942-113">[out]新建项目。</span><span class="sxs-lookup"><span data-stu-id="b1942-113">[out] New item.</span></span> 
    
  - <span data-ttu-id="b1942-114">UPM_MOV</span><span class="sxs-lookup"><span data-stu-id="b1942-114">UPM_MOV</span></span>
    
    - <span data-ttu-id="b1942-115">[out]项目已移动到此处。</span><span class="sxs-lookup"><span data-stu-id="b1942-115">[out] Item was moved here.</span></span>
    
  - <span data-ttu-id="b1942-116">UPM_MOD_PROPS</span><span class="sxs-lookup"><span data-stu-id="b1942-116">UPM_MOD_PROPS</span></span>
    
    - <span data-ttu-id="b1942-117">[out]已修改项目属性。</span><span class="sxs-lookup"><span data-stu-id="b1942-117">[out] Item properties were modified.</span></span>
    
  - <span data-ttu-id="b1942-118">UPM_HEADER</span><span class="sxs-lookup"><span data-stu-id="b1942-118">UPM_HEADER</span></span>
    
    - <span data-ttu-id="b1942-119">[out]Item 是邮件头。</span><span class="sxs-lookup"><span data-stu-id="b1942-119">[out] Item is a message header.</span></span>
    
  - <span data-ttu-id="b1942-120">UPM_OK</span><span class="sxs-lookup"><span data-stu-id="b1942-120">UPM_OK</span></span>
    
    - <span data-ttu-id="b1942-121">[in]Upload已成功。</span><span class="sxs-lookup"><span data-stu-id="b1942-121">[in] Upload was successful.</span></span> <span data-ttu-id="b1942-122">客户端在将信息上载到服务器后进行设置。</span><span class="sxs-lookup"><span data-stu-id="b1942-122">The client sets this after uploading information to the server.</span></span>
    
  - <span data-ttu-id="b1942-123">UPM_MOVED</span><span class="sxs-lookup"><span data-stu-id="b1942-123">UPM_MOVED</span></span>
    
    - <span data-ttu-id="b1942-124">[in]项目已成功移动。</span><span class="sxs-lookup"><span data-stu-id="b1942-124">[in] Item was moved successfully.</span></span>
    
  - <span data-ttu-id="b1942-125">UPM_COMMIT</span><span class="sxs-lookup"><span data-stu-id="b1942-125">UPM_COMMIT</span></span>
    
    - <span data-ttu-id="b1942-126">[in]现在提交上传状态。</span><span class="sxs-lookup"><span data-stu-id="b1942-126">[in] Commit upload state now.</span></span>
    
  - <span data-ttu-id="b1942-127">UPM_DELETE</span><span class="sxs-lookup"><span data-stu-id="b1942-127">UPM_DELETE</span></span>
    
    - <span data-ttu-id="b1942-128">[in]立即删除项目。</span><span class="sxs-lookup"><span data-stu-id="b1942-128">[in] Delete item now.</span></span>
    
  - <span data-ttu-id="b1942-129">UPM_SAVE</span><span class="sxs-lookup"><span data-stu-id="b1942-129">UPM_SAVE</span></span>
    
    - <span data-ttu-id="b1942-130">[in]保存对项目的更改。</span><span class="sxs-lookup"><span data-stu-id="b1942-130">[in] Save changes to the item.</span></span>
    
<span data-ttu-id="b1942-131">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="b1942-131">_pmsg_</span></span>
  
> <span data-ttu-id="b1942-132">[out]打开项目对象。</span><span class="sxs-lookup"><span data-stu-id="b1942-132">[out] Open item object.</span></span> <span data-ttu-id="b1942-133">有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="b1942-133">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span> 
    
<span data-ttu-id="b1942-134">_meid_</span><span class="sxs-lookup"><span data-stu-id="b1942-134">_meid_</span></span>
  
> <span data-ttu-id="b1942-135">[out]项的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="b1942-135">[out] Entry ID of item.</span></span>
    
<span data-ttu-id="b1942-136">_binReserved1_</span><span class="sxs-lookup"><span data-stu-id="b1942-136">_binReserved1_</span></span>
  
> <span data-ttu-id="b1942-137">[in]此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="b1942-137">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="b1942-138">_binReserved2_</span><span class="sxs-lookup"><span data-stu-id="b1942-138">_binReserved2_</span></span>
  
> <span data-ttu-id="b1942-139">[in]此成员仅供内部使用，Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="b1942-139">[in] This member is reserved for the internal use of Outlook and is not supported.</span></span> 
    
<span data-ttu-id="b1942-140">_feid_</span><span class="sxs-lookup"><span data-stu-id="b1942-140">_feid_</span></span>
  
> <span data-ttu-id="b1942-141">[out]源文件夹的条目 ID（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="b1942-141">[out] Entry ID of the source folder, if item was moved.</span></span>
    
<span data-ttu-id="b1942-142">_binChg_</span><span class="sxs-lookup"><span data-stu-id="b1942-142">_binChg_</span></span>
  
> <span data-ttu-id="b1942-143">[out]更改目标项的键（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="b1942-143">[out] Change key of the destination item, if item was moved.</span></span> <span data-ttu-id="b1942-144">有关 **SBinary** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="b1942-144">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="b1942-145">_binPcl_</span><span class="sxs-lookup"><span data-stu-id="b1942-145">_binPcl_</span></span>
  
> <span data-ttu-id="b1942-146">[out]更改目标项的列表（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="b1942-146">[out] Change list of the destination item, if item was moved.</span></span> <span data-ttu-id="b1942-147">有关 **SBinary** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="b1942-147">See mapidefs.h for the type definition of **SBinary**.</span></span> 
    
<span data-ttu-id="b1942-148">_skeySrc_</span><span class="sxs-lookup"><span data-stu-id="b1942-148">_skeySrc_</span></span>
  
> <span data-ttu-id="b1942-149">[out]源项的源键（如果项目已移动）。</span><span class="sxs-lookup"><span data-stu-id="b1942-149">[out] Source key of the source item, if item was moved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b1942-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1942-150">See also</span></span>

- [<span data-ttu-id="b1942-151">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="b1942-151">About the Replication API</span></span>](about-the-replication-api.md)
- [<span data-ttu-id="b1942-152">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="b1942-152">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
- [<span data-ttu-id="b1942-153">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="b1942-153">MAPI Constants</span></span>](mapi-constants.md)
- [<span data-ttu-id="b1942-154">FEID</span><span class="sxs-lookup"><span data-stu-id="b1942-154">FEID</span></span>](feid.md)
- [<span data-ttu-id="b1942-155">MEID</span><span class="sxs-lookup"><span data-stu-id="b1942-155">MEID</span></span>](meid.md)
- [<span data-ttu-id="b1942-156">SKEY</span><span class="sxs-lookup"><span data-stu-id="b1942-156">SKEY</span></span>](skey.md)

