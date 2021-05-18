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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278790"
---
# <a name="pidtagstatus-canonical-property"></a><span data-ttu-id="4cb9f-103">PidTagStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="4cb9f-103">PidTagStatus Canonical Property</span></span>

  
  
<span data-ttu-id="4cb9f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4cb9f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4cb9f-105">包含定义文件夹状态的 32 位位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-105">Contains a 32-bit bitmask of flags that define folder status.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4cb9f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4cb9f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4cb9f-107">PR_STATUS</span><span class="sxs-lookup"><span data-stu-id="4cb9f-107">PR_STATUS</span></span>  <br/> |
|<span data-ttu-id="4cb9f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4cb9f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4cb9f-109">0x360B</span><span class="sxs-lookup"><span data-stu-id="4cb9f-109">0x360B</span></span>  <br/> |
|<span data-ttu-id="4cb9f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4cb9f-110">Data type:</span></span>  <br/> |<span data-ttu-id="4cb9f-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4cb9f-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4cb9f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4cb9f-112">Area:</span></span>  <br/> |<span data-ttu-id="4cb9f-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="4cb9f-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4cb9f-114">备注</span><span class="sxs-lookup"><span data-stu-id="4cb9f-114">Remarks</span></span>

<span data-ttu-id="4cb9f-115">文件夹的此属性类似于邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-115">This property for folders is analogous to the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property for messages.</span></span> <span data-ttu-id="4cb9f-116">其标志仅为客户端应用程序提供，不会影响邮件存储。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-116">Its flags are provided for the client application only and do not affect the message store.</span></span> <span data-ttu-id="4cb9f-117">客户端可以使用或忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-117">Clients can use or ignore these settings.</span></span> <span data-ttu-id="4cb9f-118">客户端还可以为此属性的客户端可定义位定义自己的值。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-118">The client can also define its own values for the client-definable bits of this property.</span></span>
  
<span data-ttu-id="4cb9f-119">可以为位掩码设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="4cb9f-119">One or more of the following flags can be set for the bitmask:</span></span>
  
<span data-ttu-id="4cb9f-120">FLDSTATUS_DELMARKED</span><span class="sxs-lookup"><span data-stu-id="4cb9f-120">FLDSTATUS_DELMARKED</span></span> 
  
> <span data-ttu-id="4cb9f-121">文件夹标记为删除。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-121">The folder is marked for deletion.</span></span> <span data-ttu-id="4cb9f-122">客户端应用程序设置此标志。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-122">The client application sets this flag.</span></span>
    
<span data-ttu-id="4cb9f-123">FLDSTATUS_HIDDEN</span><span class="sxs-lookup"><span data-stu-id="4cb9f-123">FLDSTATUS_HIDDEN</span></span> 
  
> <span data-ttu-id="4cb9f-124">文件夹处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-124">The folder is hidden.</span></span>
    
<span data-ttu-id="4cb9f-125">FLDSTATUS_HIGHLIGHTED</span><span class="sxs-lookup"><span data-stu-id="4cb9f-125">FLDSTATUS_HIGHLIGHTED</span></span> 
  
> <span data-ttu-id="4cb9f-126">例如，该文件夹会突出显示，如反向视频中所示。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-126">The folder is highlighted, for example, shown in reverse video.</span></span>
    
<span data-ttu-id="4cb9f-127">FLDSTATUS_TAGGED</span><span class="sxs-lookup"><span data-stu-id="4cb9f-127">FLDSTATUS_TAGGED</span></span> 
  
> <span data-ttu-id="4cb9f-128">文件夹已标记。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-128">The folder is tagged.</span></span>
    
<span data-ttu-id="4cb9f-129">邮件存储提供程序将文件夹上的此属性设置为一个或多个这些值，客户端会根据其应用程序的情况解释状态。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-129">Message store providers set this property on a folder to one or more of these values and clients interpret the status as appropriate for their applications.</span></span> <span data-ttu-id="4cb9f-130">例如，客户端可以使用文件夹状态直观地区分层次结构表中的文件夹，以相同的方式显示状态相同的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-130">For example, a client can use the folder status to visually differentiate between folders in a hierarchy table, displaying folders with the same status in the same way.</span></span> <span data-ttu-id="4cb9f-131">突出显示的文件夹可以显示在反向视频中，标记的文件夹和标记为删除的文件夹可以使用有意义的图标显示，并且隐藏文件夹可以隐藏。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-131">Highlighted folders can be shown in reverse video, tagged folders and folders marked for deletion can be shown with a meaningful icon, and hidden folders can be concealed.</span></span>
  
<span data-ttu-id="4cb9f-132">第 16 位到第 31 位 ("0x10000"到0x80000000") "，可供 IPM 客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-132">Bits 16 through 31 ("0x10000" through "0x80000000") of this property are available for use by the IPM client application.</span></span> <span data-ttu-id="4cb9f-133">保留所有其他位以供 MAPI 使用;上述列表中未定义的项应最初设置为零，且不应更改。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-133">All other bits are reserved for use by MAPI; those not defined in the preceding list should be initially set to zero and not altered.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4cb9f-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="4cb9f-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4cb9f-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="4cb9f-135">Protocol specifications</span></span>

<span data-ttu-id="4cb9f-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cb9f-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cb9f-137">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4cb9f-138">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cb9f-138">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4cb9f-139">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-139">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4cb9f-140">头文件</span><span class="sxs-lookup"><span data-stu-id="4cb9f-140">Header files</span></span>

<span data-ttu-id="4cb9f-141">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4cb9f-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="4cb9f-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="4cb9f-143">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4cb9f-143">Mapitags.h</span></span>
  
> <span data-ttu-id="4cb9f-144">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4cb9f-144">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4cb9f-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb9f-145">See also</span></span>



[<span data-ttu-id="4cb9f-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4cb9f-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4cb9f-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4cb9f-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4cb9f-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4cb9f-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4cb9f-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4cb9f-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

