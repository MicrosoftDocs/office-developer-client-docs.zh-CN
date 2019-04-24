---
title: PidLidSideEffects 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSideEffects
api_type:
- COM
ms.assetid: 90d601d9-5eeb-40b6-885d-ccd8a95ae322
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d57e6a195036ead9eb42666876e91a72f65eb8b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331295"
---
# <a name="pidlidsideeffects-canonical-property"></a><span data-ttu-id="5ec75-103">PidLidSideEffects 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ec75-103">PidLidSideEffects Canonical Property</span></span>

  
  
<span data-ttu-id="5ec75-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ec75-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ec75-105">控制客户端在最终用户输入时处理邮件对象的方式。</span><span class="sxs-lookup"><span data-stu-id="5ec75-105">Controls how a message object is handled by the client when acting on end-user input.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ec75-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5ec75-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5ec75-107">dispidSideEffects</span><span class="sxs-lookup"><span data-stu-id="5ec75-107">dispidSideEffects</span></span>  <br/> |
|<span data-ttu-id="5ec75-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="5ec75-108">Property set:</span></span>  <br/> |<span data-ttu-id="5ec75-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5ec75-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5ec75-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="5ec75-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="5ec75-111">0x00008510</span><span class="sxs-lookup"><span data-stu-id="5ec75-111">0x00008510</span></span>  <br/> |
|<span data-ttu-id="5ec75-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5ec75-112">Data type:</span></span>  <br/> |<span data-ttu-id="5ec75-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5ec75-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5ec75-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5ec75-114">Area:</span></span>  <br/> |<span data-ttu-id="5ec75-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="5ec75-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5ec75-116">注解</span><span class="sxs-lookup"><span data-stu-id="5ec75-116">Remarks</span></span>

<span data-ttu-id="5ec75-117">必须设置为按位或零个或更多的以下标志。</span><span class="sxs-lookup"><span data-stu-id="5ec75-117">Must be set to a bitwise or zero or more of the following flags.</span></span>
  
|<span data-ttu-id="5ec75-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="5ec75-118">**Name**</span></span>|<span data-ttu-id="5ec75-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="5ec75-119">**Value**</span></span>|<span data-ttu-id="5ec75-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5ec75-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ec75-121">seOpenToDelete</span><span class="sxs-lookup"><span data-stu-id="5ec75-121">seOpenToDelete</span></span>  <br/> |<span data-ttu-id="5ec75-122">0x0001</span><span class="sxs-lookup"><span data-stu-id="5ec75-122">0x0001</span></span>  <br/> |<span data-ttu-id="5ec75-123">删除邮件对象时需要进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="5ec75-123">Additional processing is required on the message object when deleting.</span></span>  <br/> |
|<span data-ttu-id="5ec75-124">seNoFrame</span><span class="sxs-lookup"><span data-stu-id="5ec75-124">seNoFrame</span></span>  <br/> |<span data-ttu-id="5ec75-125">0x0008</span><span class="sxs-lookup"><span data-stu-id="5ec75-125">0x0008</span></span>  <br/> |<span data-ttu-id="5ec75-126">没有与 message 对象相关联的 UI。</span><span class="sxs-lookup"><span data-stu-id="5ec75-126">No UI is associated with the message object.</span></span>  <br/> |
|<span data-ttu-id="5ec75-127">seCoerceToInbox</span><span class="sxs-lookup"><span data-stu-id="5ec75-127">seCoerceToInbox</span></span>  <br/> |<span data-ttu-id="5ec75-128">0x0010</span><span class="sxs-lookup"><span data-stu-id="5ec75-128">0x0010</span></span>  <br/> |<span data-ttu-id="5ec75-129">移动或复制到具有 " **PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md))" 属性的 "IPF" 的 folder 对象时, 需要对 message 对象进行额外的处理。注释 "。</span><span class="sxs-lookup"><span data-stu-id="5ec75-129">Additional processing is required on the message object when moving or copying to a folder object with a **PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) property of "IPF.Note".</span></span>  <br/> |
|<span data-ttu-id="5ec75-130">seOpenTocopy</span><span class="sxs-lookup"><span data-stu-id="5ec75-130">seOpenTocopy</span></span>  <br/> |<span data-ttu-id="5ec75-131">0x0020</span><span class="sxs-lookup"><span data-stu-id="5ec75-131">0x0020</span></span>  <br/> |<span data-ttu-id="5ec75-132">将邮件对象复制到另一个文件夹时需要进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="5ec75-132">Additional processing is required on the message object when copying to another folder.</span></span>  <br/> |
|<span data-ttu-id="5ec75-133">seOpenToMove</span><span class="sxs-lookup"><span data-stu-id="5ec75-133">seOpenToMove</span></span>  <br/> |<span data-ttu-id="5ec75-134">0x0040</span><span class="sxs-lookup"><span data-stu-id="5ec75-134">0x0040</span></span>  <br/> |<span data-ttu-id="5ec75-135">在邮件对象移到另一个文件夹时需要进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="5ec75-135">Additional processing is required on the message object when moving to another folder.</span></span>  <br/> |
|<span data-ttu-id="5ec75-136">seOpenForCtxMenu</span><span class="sxs-lookup"><span data-stu-id="5ec75-136">seOpenForCtxMenu</span></span>  <br/> |<span data-ttu-id="5ec75-137">0x0100</span><span class="sxs-lookup"><span data-stu-id="5ec75-137">0x0100</span></span>  <br/> |<span data-ttu-id="5ec75-138">向最终用户显示动作时, 对 message 对象需要进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="5ec75-138">Additional processing is required on the message object when displaying verbs to the end-user.</span></span>  <br/> |
|<span data-ttu-id="5ec75-139">seCannotUndoDelete</span><span class="sxs-lookup"><span data-stu-id="5ec75-139">seCannotUndoDelete</span></span>  <br/> |<span data-ttu-id="5ec75-140">0x0400</span><span class="sxs-lookup"><span data-stu-id="5ec75-140">0x0400</span></span>  <br/> |<span data-ttu-id="5ec75-141">无法撤消删除操作, 除非设置了 "seOpenToDelete", 否则不得对其进行设置。</span><span class="sxs-lookup"><span data-stu-id="5ec75-141">Cannot undo delete operation, must not be set unless "seOpenToDelete" is set.</span></span>  <br/> |
|<span data-ttu-id="5ec75-142">seCannotUndoCopy</span><span class="sxs-lookup"><span data-stu-id="5ec75-142">seCannotUndoCopy</span></span>  <br/> |<span data-ttu-id="5ec75-143">0x0800</span><span class="sxs-lookup"><span data-stu-id="5ec75-143">0x0800</span></span>  <br/> |<span data-ttu-id="5ec75-144">无法撤消复制操作, 除非设置了 "seOpenTocopy", 否则不得对其进行设置。</span><span class="sxs-lookup"><span data-stu-id="5ec75-144">Cannot undo copy operation, must not be set unless "seOpenTocopy" is set.</span></span>  <br/> |
|<span data-ttu-id="5ec75-145">seCannotUndoMove</span><span class="sxs-lookup"><span data-stu-id="5ec75-145">seCannotUndoMove</span></span>  <br/> |<span data-ttu-id="5ec75-146">0x1000</span><span class="sxs-lookup"><span data-stu-id="5ec75-146">0x1000</span></span>  <br/> |<span data-ttu-id="5ec75-147">无法撤消移动操作, 除非设置了 "seOpenToMove", 否则不得进行设置。</span><span class="sxs-lookup"><span data-stu-id="5ec75-147">Cannot undo move operation, must not be set unless "seOpenToMove" is set.</span></span>  <br/> |
|<span data-ttu-id="5ec75-148">seHasScript</span><span class="sxs-lookup"><span data-stu-id="5ec75-148">seHasScript</span></span>  <br/> |<span data-ttu-id="5ec75-149">0x2000</span><span class="sxs-lookup"><span data-stu-id="5ec75-149">0x2000</span></span>  <br/> |<span data-ttu-id="5ec75-150">message 对象包含最终用户脚本。</span><span class="sxs-lookup"><span data-stu-id="5ec75-150">The message object contains end-user script.</span></span>  <br/> |
|<span data-ttu-id="5ec75-151">seOpenToPermDelete</span><span class="sxs-lookup"><span data-stu-id="5ec75-151">seOpenToPermDelete</span></span>  <br/> |<span data-ttu-id="5ec75-152">0x4000</span><span class="sxs-lookup"><span data-stu-id="5ec75-152">0x4000</span></span>  <br/> |<span data-ttu-id="5ec75-153">若要永久删除 message 对象, 需要进行额外的处理。</span><span class="sxs-lookup"><span data-stu-id="5ec75-153">Additional processing is required to permanently delete the message object.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="5ec75-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="5ec75-154">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5ec75-155">协议规范</span><span class="sxs-lookup"><span data-stu-id="5ec75-155">Protocol specifications</span></span>

<span data-ttu-id="5ec75-156">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ec75-156">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ec75-157">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5ec75-157">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5ec75-158">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ec75-158">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ec75-159">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="5ec75-159">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="5ec75-160">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ec75-160">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ec75-161">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5ec75-161">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5ec75-162">头文件</span><span class="sxs-lookup"><span data-stu-id="5ec75-162">Header files</span></span>

<span data-ttu-id="5ec75-163">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5ec75-163">Mapidefs.h</span></span>
  
> <span data-ttu-id="5ec75-164">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5ec75-164">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ec75-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ec75-165">See also</span></span>



[<span data-ttu-id="5ec75-166">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5ec75-166">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5ec75-167">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ec75-167">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5ec75-168">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5ec75-168">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5ec75-169">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5ec75-169">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

