---
title: PidTagRecipientFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientFlags
api_type:
- COM
ms.assetid: 9fbe537f-b5fe-48a2-803c-653c50c82efd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e84f1361e9ca3d95b4297c01801e649a9f86ced
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569230"
---
# <a name="pidtagrecipientflags-canonical-property"></a><span data-ttu-id="dba57-103">PidTagRecipientFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="dba57-103">PidTagRecipientFlags Canonical Property</span></span>

  
  
<span data-ttu-id="dba57-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dba57-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dba57-105">指定一个位字段，介绍了在收件人的状态。</span><span class="sxs-lookup"><span data-stu-id="dba57-105">Specifies a bit field that describes the recipient status.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dba57-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dba57-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dba57-107">PR_RECIPIENT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="dba57-107">PR_RECIPIENT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="dba57-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="dba57-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dba57-109">0x5FFD</span><span class="sxs-lookup"><span data-stu-id="dba57-109">0x5FFD</span></span>  <br/> |
|<span data-ttu-id="dba57-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dba57-110">Data type:</span></span>  <br/> |<span data-ttu-id="dba57-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="dba57-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="dba57-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dba57-112">Area:</span></span>  <br/> |<span data-ttu-id="dba57-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="dba57-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dba57-114">注解</span><span class="sxs-lookup"><span data-stu-id="dba57-114">Remarks</span></span>

<span data-ttu-id="dba57-115">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="dba57-115">This property is not required.</span></span> <span data-ttu-id="dba57-116">以下是可以设置的单个标记。</span><span class="sxs-lookup"><span data-stu-id="dba57-116">The following are the individual flags that can be set.</span></span>
  
|<span data-ttu-id="dba57-117">**值**</span><span class="sxs-lookup"><span data-stu-id="dba57-117">**Value**</span></span>|<span data-ttu-id="dba57-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="dba57-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dba57-119">S (recipSendable，0x00000001)</span><span class="sxs-lookup"><span data-stu-id="dba57-119">S (recipSendable, 0x00000001)</span></span>  <br/> |<span data-ttu-id="dba57-120">收件人是**Sendable**与会者。</span><span class="sxs-lookup"><span data-stu-id="dba57-120">The recipient is a **Sendable** Attendee.</span></span> <span data-ttu-id="dba57-121">**DispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) 属性中仅使用此标志。</span><span class="sxs-lookup"><span data-stu-id="dba57-121">This flag is only used in the **dispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) property.</span></span>  <br/> |
|<span data-ttu-id="dba57-122">O (recipOrganizer，0x0000002)</span><span class="sxs-lookup"><span data-stu-id="dba57-122">O (recipOrganizer, 0x0000002)</span></span>  <br/> |<span data-ttu-id="dba57-123">设置了此标志**RecipientRow**表示会议组织者。</span><span class="sxs-lookup"><span data-stu-id="dba57-123">The **RecipientRow** on which this flag is set represents the meeting Organizer.</span></span>  <br/> |
|<span data-ttu-id="dba57-124">紧急 (recipExceptionalResponse，0x00000010)</span><span class="sxs-lookup"><span data-stu-id="dba57-124">ER (recipExceptionalResponse, 0x00000010)</span></span>  <br/> |<span data-ttu-id="dba57-125">指示与会者此**RecipientRow**所在异常赋予响应。</span><span class="sxs-lookup"><span data-stu-id="dba57-125">Indicates that the attendee gave a response for the exception on which this **RecipientRow** resides.</span></span> <span data-ttu-id="dba57-126">组织者的会议对象的异常邮件嵌入对象**RecipientRow**中仅使用此标志。</span><span class="sxs-lookup"><span data-stu-id="dba57-126">This flag is only used in a **RecipientRow** of an exception embedded message object of the organizer's meeting object.</span></span>  <br/> |
|<span data-ttu-id="dba57-127">ED (recipExceptionalDeleted，0x00000020)</span><span class="sxs-lookup"><span data-stu-id="dba57-127">ED (recipExceptionalDeleted, 0x00000020)</span></span>  <br/> |<span data-ttu-id="dba57-128">指示，虽然**RecipientRow**存在，它应被视为未显示相应的收件人。</span><span class="sxs-lookup"><span data-stu-id="dba57-128">Indicates that although the **RecipientRow** exists, it should be treated as if the corresponding recipient does not.</span></span> <span data-ttu-id="dba57-129">组织者的会议对象的异常邮件嵌入对象**RecipientRow**中仅使用此标志。</span><span class="sxs-lookup"><span data-stu-id="dba57-129">This flag is only used in a **RecipientRow** of an exception embedded message object of the organizer's meeting object.</span></span>  <br/> |
|<span data-ttu-id="dba57-130">X (保留，0x00000040)</span><span class="sxs-lookup"><span data-stu-id="dba57-130">X (reserved, 0x00000040)</span></span>  <br/> |<span data-ttu-id="dba57-131">不能设置。</span><span class="sxs-lookup"><span data-stu-id="dba57-131">Must not be set.</span></span>  <br/> |
|<span data-ttu-id="dba57-132">X (保留，0x00000080)</span><span class="sxs-lookup"><span data-stu-id="dba57-132">X (reserved, 0x00000080)</span></span>  <br/> |<span data-ttu-id="dba57-133">不能设置。</span><span class="sxs-lookup"><span data-stu-id="dba57-133">Must not be set.</span></span>  <br/> |
|<span data-ttu-id="dba57-134">G (recipOriginal，0x00000100)</span><span class="sxs-lookup"><span data-stu-id="dba57-134">G (recipOriginal, 0x00000100)</span></span>  <br/> |<span data-ttu-id="dba57-135">指示收件人是原始与会者。</span><span class="sxs-lookup"><span data-stu-id="dba57-135">Indicates the recipient is an original attendee.</span></span> <span data-ttu-id="dba57-136">**DispidApptUnsendableRecips**属性中仅使用此标志。</span><span class="sxs-lookup"><span data-stu-id="dba57-136">This flag is only used in the **dispidApptUnsendableRecips** property.</span></span>  <br/> |
|<span data-ttu-id="dba57-137">X (保留，0x00000200)</span><span class="sxs-lookup"><span data-stu-id="dba57-137">X (reserved, 0x00000200)</span></span>  <br/> |<span data-ttu-id="dba57-138">保留。</span><span class="sxs-lookup"><span data-stu-id="dba57-138">Reserved.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="dba57-139">相关资源</span><span class="sxs-lookup"><span data-stu-id="dba57-139">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dba57-140">协议规范</span><span class="sxs-lookup"><span data-stu-id="dba57-140">Protocol specifications</span></span>

<span data-ttu-id="dba57-141">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dba57-141">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dba57-142">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="dba57-142">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dba57-143">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dba57-143">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dba57-144">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="dba57-144">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dba57-145">头文件</span><span class="sxs-lookup"><span data-stu-id="dba57-145">Header files</span></span>

<span data-ttu-id="dba57-146">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dba57-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="dba57-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dba57-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="dba57-148">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dba57-148">Mapitags.h</span></span>
  
> <span data-ttu-id="dba57-149">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dba57-149">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dba57-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dba57-150">See also</span></span>



[<span data-ttu-id="dba57-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dba57-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dba57-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dba57-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dba57-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dba57-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dba57-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dba57-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

