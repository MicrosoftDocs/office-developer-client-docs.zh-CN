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
ms.openlocfilehash: fa29a55a5fc2ce89e125909d13a2c14a347ef831
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594023"
---
# <a name="pidlidsideeffects-canonical-property"></a><span data-ttu-id="e1136-103">PidLidSideEffects 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1136-103">PidLidSideEffects Canonical Property</span></span>

  
  
<span data-ttu-id="e1136-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1136-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1136-105">控制 message 对象时如何处理由客户端执行最终用户输入。</span><span class="sxs-lookup"><span data-stu-id="e1136-105">Controls how a message object is handled by the client when acting on end-user input.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e1136-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e1136-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e1136-107">dispidSideEffects</span><span class="sxs-lookup"><span data-stu-id="e1136-107">dispidSideEffects</span></span>  <br/> |
|<span data-ttu-id="e1136-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e1136-108">Property set:</span></span>  <br/> |<span data-ttu-id="e1136-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="e1136-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="e1136-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e1136-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e1136-111">0x00008510</span><span class="sxs-lookup"><span data-stu-id="e1136-111">0x00008510</span></span>  <br/> |
|<span data-ttu-id="e1136-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e1136-112">Data type:</span></span>  <br/> |<span data-ttu-id="e1136-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e1136-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e1136-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e1136-114">Area:</span></span>  <br/> |<span data-ttu-id="e1136-115">运行时配置</span><span class="sxs-lookup"><span data-stu-id="e1136-115">Run-time configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e1136-116">注解</span><span class="sxs-lookup"><span data-stu-id="e1136-116">Remarks</span></span>

<span data-ttu-id="e1136-117">必须设置为按位或零个或多个以下标志。</span><span class="sxs-lookup"><span data-stu-id="e1136-117">Must be set to a bitwise or zero or more of the following flags.</span></span>
  
|<span data-ttu-id="e1136-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="e1136-118">**Name**</span></span>|<span data-ttu-id="e1136-119">**值**</span><span class="sxs-lookup"><span data-stu-id="e1136-119">**Value**</span></span>|<span data-ttu-id="e1136-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1136-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1136-121">seOpenToDelete</span><span class="sxs-lookup"><span data-stu-id="e1136-121">seOpenToDelete</span></span>  <br/> |<span data-ttu-id="e1136-122">0x0001</span><span class="sxs-lookup"><span data-stu-id="e1136-122">0x0001</span></span>  <br/> |<span data-ttu-id="e1136-123">Message 对象时删除需要其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1136-123">Additional processing is required on the message object when deleting.</span></span>  <br/> |
|<span data-ttu-id="e1136-124">seNoFrame</span><span class="sxs-lookup"><span data-stu-id="e1136-124">seNoFrame</span></span>  <br/> |<span data-ttu-id="e1136-125">0x0008</span><span class="sxs-lookup"><span data-stu-id="e1136-125">0x0008</span></span>  <br/> |<span data-ttu-id="e1136-126">没有用户界面相关联的消息对象。</span><span class="sxs-lookup"><span data-stu-id="e1136-126">No UI is associated with the message object.</span></span>  <br/> |
|<span data-ttu-id="e1136-127">seCoerceToInbox</span><span class="sxs-lookup"><span data-stu-id="e1136-127">seCoerceToInbox</span></span>  <br/> |<span data-ttu-id="e1136-128">0x0010</span><span class="sxs-lookup"><span data-stu-id="e1136-128">0x0010</span></span>  <br/> |<span data-ttu-id="e1136-129">Message 对象时移动或复制到**PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) 属性值为"IPF 一个 folder 对象上需要其他处理。请注意"。</span><span class="sxs-lookup"><span data-stu-id="e1136-129">Additional processing is required on the message object when moving or copying to a folder object with a **PR_CONTAINER_CLASS** ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) property of "IPF.Note".</span></span>  <br/> |
|<span data-ttu-id="e1136-130">seOpenTocopy</span><span class="sxs-lookup"><span data-stu-id="e1136-130">seOpenTocopy</span></span>  <br/> |<span data-ttu-id="e1136-131">0x0020</span><span class="sxs-lookup"><span data-stu-id="e1136-131">0x0020</span></span>  <br/> |<span data-ttu-id="e1136-132">Message 对象复制到另一个文件夹时需要其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1136-132">Additional processing is required on the message object when copying to another folder.</span></span>  <br/> |
|<span data-ttu-id="e1136-133">seOpenToMove</span><span class="sxs-lookup"><span data-stu-id="e1136-133">seOpenToMove</span></span>  <br/> |<span data-ttu-id="e1136-134">0x0040</span><span class="sxs-lookup"><span data-stu-id="e1136-134">0x0040</span></span>  <br/> |<span data-ttu-id="e1136-135">将移动到另一个文件夹时，将 message 对象上需要其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1136-135">Additional processing is required on the message object when moving to another folder.</span></span>  <br/> |
|<span data-ttu-id="e1136-136">seOpenForCtxMenu</span><span class="sxs-lookup"><span data-stu-id="e1136-136">seOpenForCtxMenu</span></span>  <br/> |<span data-ttu-id="e1136-137">0x0100</span><span class="sxs-lookup"><span data-stu-id="e1136-137">0x0100</span></span>  <br/> |<span data-ttu-id="e1136-138">Message 对象时向最终用户显示动词需要其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1136-138">Additional processing is required on the message object when displaying verbs to the end-user.</span></span>  <br/> |
|<span data-ttu-id="e1136-139">seCannotUndoDelete</span><span class="sxs-lookup"><span data-stu-id="e1136-139">seCannotUndoDelete</span></span>  <br/> |<span data-ttu-id="e1136-140">0x0400</span><span class="sxs-lookup"><span data-stu-id="e1136-140">0x0400</span></span>  <br/> |<span data-ttu-id="e1136-141">无法撤消删除操作，必须设置，除非设置"seOpenToDelete"。</span><span class="sxs-lookup"><span data-stu-id="e1136-141">Cannot undo delete operation, must not be set unless "seOpenToDelete" is set.</span></span>  <br/> |
|<span data-ttu-id="e1136-142">seCannotUndoCopy</span><span class="sxs-lookup"><span data-stu-id="e1136-142">seCannotUndoCopy</span></span>  <br/> |<span data-ttu-id="e1136-143">0x0800</span><span class="sxs-lookup"><span data-stu-id="e1136-143">0x0800</span></span>  <br/> |<span data-ttu-id="e1136-144">无法撤消复制操作，必须设置，除非设置"seOpenTocopy"。</span><span class="sxs-lookup"><span data-stu-id="e1136-144">Cannot undo copy operation, must not be set unless "seOpenTocopy" is set.</span></span>  <br/> |
|<span data-ttu-id="e1136-145">seCannotUndoMove</span><span class="sxs-lookup"><span data-stu-id="e1136-145">seCannotUndoMove</span></span>  <br/> |<span data-ttu-id="e1136-146">0x1000</span><span class="sxs-lookup"><span data-stu-id="e1136-146">0x1000</span></span>  <br/> |<span data-ttu-id="e1136-147">无法撤消移动操作，必须设置，除非设置"seOpenToMove"。</span><span class="sxs-lookup"><span data-stu-id="e1136-147">Cannot undo move operation, must not be set unless "seOpenToMove" is set.</span></span>  <br/> |
|<span data-ttu-id="e1136-148">seHasScript</span><span class="sxs-lookup"><span data-stu-id="e1136-148">seHasScript</span></span>  <br/> |<span data-ttu-id="e1136-149">0x2000</span><span class="sxs-lookup"><span data-stu-id="e1136-149">0x2000</span></span>  <br/> |<span data-ttu-id="e1136-150">Message 对象包含最终用户脚本。</span><span class="sxs-lookup"><span data-stu-id="e1136-150">The message object contains end-user script.</span></span>  <br/> |
|<span data-ttu-id="e1136-151">seOpenToPermDelete</span><span class="sxs-lookup"><span data-stu-id="e1136-151">seOpenToPermDelete</span></span>  <br/> |<span data-ttu-id="e1136-152">0x4000</span><span class="sxs-lookup"><span data-stu-id="e1136-152">0x4000</span></span>  <br/> |<span data-ttu-id="e1136-153">永久删除 message 对象需要进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="e1136-153">Additional processing is required to permanently delete the message object.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e1136-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="e1136-154">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e1136-155">协议规范</span><span class="sxs-lookup"><span data-stu-id="e1136-155">Protocol specifications</span></span>

<span data-ttu-id="e1136-156">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1136-156">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1136-157">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e1136-157">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e1136-158">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1136-158">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1136-159">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="e1136-159">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="e1136-160">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1136-160">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e1136-161">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="e1136-161">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e1136-162">头文件</span><span class="sxs-lookup"><span data-stu-id="e1136-162">Header files</span></span>

<span data-ttu-id="e1136-163">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e1136-163">Mapidefs.h</span></span>
  
> <span data-ttu-id="e1136-164">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e1136-164">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e1136-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1136-165">See also</span></span>



[<span data-ttu-id="e1136-166">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e1136-166">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e1136-167">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e1136-167">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e1136-168">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e1136-168">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e1136-169">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e1136-169">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

