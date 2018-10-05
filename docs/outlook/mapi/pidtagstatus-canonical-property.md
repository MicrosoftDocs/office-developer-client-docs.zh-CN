---
title: PidTagStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStatus
api_type:
- COM
ms.assetid: 8b947660-eafe-47e1-9595-bd3ab7d455bf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de2342ef4d3e9d06f198e06dc19c65b7b144624f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387907"
---
# <a name="pidtagstatus-canonical-property"></a><span data-ttu-id="c65db-103">PidTagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="c65db-103">PidTagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="c65db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c65db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c65db-105">包含定义文件夹的状态标志的 32 位位掩码。</span><span class="sxs-lookup"><span data-stu-id="c65db-105">Contains a 32-bit bitmask of flags that define folder status.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c65db-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c65db-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c65db-107">PR_STATUS</span><span class="sxs-lookup"><span data-stu-id="c65db-107">PR_STATUS</span></span>  <br/> |
|<span data-ttu-id="c65db-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c65db-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c65db-109">0x360B</span><span class="sxs-lookup"><span data-stu-id="c65db-109">0x360B</span></span>  <br/> |
|<span data-ttu-id="c65db-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c65db-110">Data type:</span></span>  <br/> |<span data-ttu-id="c65db-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c65db-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c65db-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c65db-112">Area:</span></span>  <br/> |<span data-ttu-id="c65db-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="c65db-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c65db-114">说明</span><span class="sxs-lookup"><span data-stu-id="c65db-114">Remarks</span></span>

<span data-ttu-id="c65db-115">文件夹此属性是类似于邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="c65db-115">This property for folders is analogous to the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property for messages.</span></span> <span data-ttu-id="c65db-116">它的标志为客户端应用程序仅提供并不影响消息存储库。</span><span class="sxs-lookup"><span data-stu-id="c65db-116">Its flags are provided for the client application only and do not affect the message store.</span></span> <span data-ttu-id="c65db-117">客户端可以使用或忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="c65db-117">Clients can use or ignore these settings.</span></span> <span data-ttu-id="c65db-118">客户端还可以定义自己的此属性的客户端贴合位的值。</span><span class="sxs-lookup"><span data-stu-id="c65db-118">The client can also define its own values for the client-definable bits of this property.</span></span>
  
<span data-ttu-id="c65db-119">可以为位掩码设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="c65db-119">One or more of the following flags can be set for the bitmask:</span></span>
  
<span data-ttu-id="c65db-120">FLDSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="c65db-120">FLDSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="c65db-121">文件夹标记为删除。</span><span class="sxs-lookup"><span data-stu-id="c65db-121">The folder is marked for deletion.</span></span> <span data-ttu-id="c65db-122">客户端应用程序设置此标志。</span><span class="sxs-lookup"><span data-stu-id="c65db-122">The client application sets this flag.</span></span>
    
<span data-ttu-id="c65db-123">FLDSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="c65db-123">FLDSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="c65db-124">文件夹处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="c65db-124">The folder is hidden.</span></span>
    
<span data-ttu-id="c65db-125">FLDSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="c65db-125">FLDSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="c65db-126">文件夹突出显示，例如，反向中显示视频。</span><span class="sxs-lookup"><span data-stu-id="c65db-126">The folder is highlighted, for example, shown in reverse video.</span></span>
    
<span data-ttu-id="c65db-127">FLDSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="c65db-127">FLDSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="c65db-128">文件夹被标记。</span><span class="sxs-lookup"><span data-stu-id="c65db-128">The folder is tagged.</span></span>
    
<span data-ttu-id="c65db-129">消息存储提供程序将此属性设置在到一个文件夹或多个这些值和客户端解释根据其应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="c65db-129">Message store providers set this property on a folder to one or more of these values and clients interpret the status as appropriate for their applications.</span></span> <span data-ttu-id="c65db-130">例如，客户端可以使用文件夹状态直观地区分在相同的方式显示相同状态的文件夹的层次结构表中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c65db-130">For example, a client can use the folder status to visually differentiate between folders in a hierarchy table, displaying folders with the same status in the same way.</span></span> <span data-ttu-id="c65db-131">突出显示的文件夹可以显示反向视频、 标记文件夹中标记为删除文件夹可以显示包含有意义的图标，并可以隐藏隐藏的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c65db-131">Highlighted folders can be shown in reverse video, tagged folders and folders marked for deletion can be shown with a meaningful icon, and hidden folders can be concealed.</span></span>
  
<span data-ttu-id="c65db-132">位 16 到 31 (通过"0x80000000"的"0x10000")，此属性是可供使用 IPM 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c65db-132">Bits 16 through 31 ("0x10000" through "0x80000000") of this property are available for use by the IPM client application.</span></span> <span data-ttu-id="c65db-133">所有其他位供使用通过 MAPI;未定义上述列表中的值应最初设置为零并不会改动。</span><span class="sxs-lookup"><span data-stu-id="c65db-133">All other bits are reserved for use by MAPI; those not defined in the preceding list should be initially set to zero and not altered.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c65db-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="c65db-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c65db-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="c65db-135">Protocol specifications</span></span>

<span data-ttu-id="c65db-136">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c65db-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c65db-137">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c65db-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c65db-138">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c65db-138">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c65db-139">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="c65db-139">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c65db-140">头文件</span><span class="sxs-lookup"><span data-stu-id="c65db-140">Header files</span></span>

<span data-ttu-id="c65db-141">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c65db-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="c65db-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c65db-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="c65db-143">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c65db-143">Mapitags.h</span></span>
  
> <span data-ttu-id="c65db-144">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c65db-144">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c65db-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c65db-145">See also</span></span>



[<span data-ttu-id="c65db-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c65db-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c65db-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c65db-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c65db-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c65db-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c65db-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c65db-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

