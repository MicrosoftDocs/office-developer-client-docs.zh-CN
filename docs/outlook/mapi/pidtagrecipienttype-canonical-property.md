---
title: PidTagRecipientType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientType
api_type:
- COM
ms.assetid: 67e31027-6bc2-4a40-9b00-d61baef4ab0f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0218ff558e9dfca2f73bbad2dc42cdb7bd7121fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778186"
---
# <a name="pidtagrecipienttype-canonical-property"></a><span data-ttu-id="ed427-103">PidTagRecipientType 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-103">PidTagRecipientType Canonical Property</span></span>

  
  
<span data-ttu-id="ed427-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ed427-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ed427-105">包含邮件收件人的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="ed427-105">Contains the recipient type for a message recipient.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ed427-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ed427-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ed427-107">PR_RECIPIENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="ed427-107">PR_RECIPIENT_TYPE</span></span>  <br/> |
|<span data-ttu-id="ed427-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ed427-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ed427-109">0x0C15</span><span class="sxs-lookup"><span data-stu-id="ed427-109">0x0C15</span></span>  <br/> |
|<span data-ttu-id="ed427-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ed427-110">Data type:</span></span>  <br/> |<span data-ttu-id="ed427-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ed427-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ed427-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ed427-112">Area:</span></span>  <br/> |<span data-ttu-id="ed427-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="ed427-113">MAPI recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ed427-114">备注</span><span class="sxs-lookup"><span data-stu-id="ed427-114">Remarks</span></span>

<span data-ttu-id="ed427-115">此属性中包含的收件人类型包括一个必选的值和一个可选标志。</span><span class="sxs-lookup"><span data-stu-id="ed427-115">The recipient type contained in this property consists of one required value and one optional flag.</span></span>
  
<span data-ttu-id="ed427-116">此属性必须包含完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ed427-116">This property must contain exactly one of the following values:</span></span>
  
<span data-ttu-id="ed427-117">MAPI_TO</span><span class="sxs-lookup"><span data-stu-id="ed427-117">MAPI_TO</span></span> 
  
> <span data-ttu-id="ed427-118">收件人是主 （给） 收件人。</span><span class="sxs-lookup"><span data-stu-id="ed427-118">The recipient is a primary (To) recipient.</span></span> <span data-ttu-id="ed427-119">客户端需要处理主收件人。</span><span class="sxs-lookup"><span data-stu-id="ed427-119">Clients are required to handle primary recipients.</span></span> <span data-ttu-id="ed427-120">所有其他类型是可选的。</span><span class="sxs-lookup"><span data-stu-id="ed427-120">All other types are optional.</span></span>
    
<span data-ttu-id="ed427-121">MAPI_CC</span><span class="sxs-lookup"><span data-stu-id="ed427-121">MAPI_CC</span></span> 
  
> <span data-ttu-id="ed427-122">收件人抄送 (CC) 收件人收到除了主收件人的邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="ed427-122">The recipient is a carbon copy (CC) recipient, a recipient that receives a message in addition to the primary recipients.</span></span>
    
<span data-ttu-id="ed427-123">MAPI_BCC</span><span class="sxs-lookup"><span data-stu-id="ed427-123">MAPI_BCC</span></span> 
  
> <span data-ttu-id="ed427-124">收件人是密件抄送 (BCC) 收件人。</span><span class="sxs-lookup"><span data-stu-id="ed427-124">The recipient is a blind carbon copy (BCC) recipient.</span></span> <span data-ttu-id="ed427-125">主和抄送副本收件人不知道密件抄送收件人的存在。</span><span class="sxs-lookup"><span data-stu-id="ed427-125">Primary and carbon copy recipients are unaware of the existence of BCC recipients.</span></span> 
    
<span data-ttu-id="ed427-126">MAPI_P1</span><span class="sxs-lookup"><span data-stu-id="ed427-126">MAPI_P1</span></span> 
  
> <span data-ttu-id="ed427-127">收件人未成功接收邮件在上一次尝试。</span><span class="sxs-lookup"><span data-stu-id="ed427-127">The recipient did not successfully receive the message on the previous attempt.</span></span> <span data-ttu-id="ed427-128">这是早期传输重新。</span><span class="sxs-lookup"><span data-stu-id="ed427-128">This is a resend of an earlier transmission.</span></span>
    
<span data-ttu-id="ed427-129">此外，可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="ed427-129">In addition, the following flag can be set:</span></span>
  
<span data-ttu-id="ed427-130">MAPI_SUBMITTED</span><span class="sxs-lookup"><span data-stu-id="ed427-130">MAPI_SUBMITTED</span></span> 
  
> <span data-ttu-id="ed427-131">收件人已接收邮件，并不需要再次出现。</span><span class="sxs-lookup"><span data-stu-id="ed427-131">The recipient has already received the message and does not need to receive it again.</span></span> <span data-ttu-id="ed427-132">这是早期传输重新。</span><span class="sxs-lookup"><span data-stu-id="ed427-132">This is a resend of an earlier transmission.</span></span> <span data-ttu-id="ed427-133">此标志设置与**MAPI_TO**、 **MAPI_CC**和**MAPI_BCC**值结合使用。</span><span class="sxs-lookup"><span data-stu-id="ed427-133">This flag is set in conjunction with the **MAPI_TO**, **MAPI_CC**, and **MAPI_BCC** values.</span></span> 
    
<span data-ttu-id="ed427-134">正在一条消息，指出由于原件到一个或多个预期收件人时，将使用 MAPI_P1 值和**MAPI_SUBMITTED**标志。</span><span class="sxs-lookup"><span data-stu-id="ed427-134">The MAPI_P1 value and the **MAPI_SUBMITTED** flag are used when a message is being retransmitted due to nondelivery to one or more of the intended recipients.</span></span> <span data-ttu-id="ed427-135">为此重新传输，客户端上不需要该消息，但应显示的收件人列表中每个收件人设置**MAPI_SUBMITTED** 。</span><span class="sxs-lookup"><span data-stu-id="ed427-135">For this retransmission, the client sets **MAPI_SUBMITTED** on every recipient that does not need the message again but should be displayed in the recipient list.</span></span> <span data-ttu-id="ed427-136">用于每个未以前接收邮件的收件人，客户端不变，其**PR_RECIPIENT_TYPE**值保留原始收件人，但此外提交一份收件人提供 MAPI_P1 代替的原始值。</span><span class="sxs-lookup"><span data-stu-id="ed427-136">For every recipient that did not receive the message previously, the client retains the original recipient with its **PR_RECIPIENT_TYPE** value unchanged, but additionally submits a copy of the recipient with MAPI_P1 in place of the original value.</span></span> <span data-ttu-id="ed427-137">此副本，将被丢弃实际交付之前，强制进入 P1 信封的收件人，并向该收件人保证物理重新传输。</span><span class="sxs-lookup"><span data-stu-id="ed427-137">This copy, which is discarded before actual delivery, forces the recipient into the P1 envelope and guarantees physical retransmission to that recipient.</span></span> <span data-ttu-id="ed427-138">MAPI_P1 收件人**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ed427-138">The **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property is set to FALSE for MAPI_P1 recipients.</span></span>
  
<span data-ttu-id="ed427-139">当客户端显示重新发送窗体时，仅 MAPI_P1 收件人是可见的。</span><span class="sxs-lookup"><span data-stu-id="ed427-139">When a client displays a resend form, only the MAPI_P1 recipients are visible.</span></span> <span data-ttu-id="ed427-140">用户输入其他收件人的邮件传递时，除非收件人列表将显示首次发送邮件时完全相同。</span><span class="sxs-lookup"><span data-stu-id="ed427-140">Unless the user enters additional recipients, when the message is delivered, the recipient list appears exactly as it did when the message was sent for the first time.</span></span> 
  
<span data-ttu-id="ed427-141">**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 属性与收件人类型。</span><span class="sxs-lookup"><span data-stu-id="ed427-141">The **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)), **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) and **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) properties are related to recipient type.</span></span> <span data-ttu-id="ed427-142">当客户端呼叫消息的**IMAPIProp::SaveChanges**没有至少一个收件人的收件人列表中，消息存储提供程序，如下所示设置这些属性：</span><span class="sxs-lookup"><span data-stu-id="ed427-142">When a client calls a message's **IMAPIProp::SaveChanges** and there is at least one recipient in the recipient list, the message store provider sets these properties as follows:</span></span> 
  
|<span data-ttu-id="ed427-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="ed427-143">**Property**</span></span>|<span data-ttu-id="ed427-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed427-144">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed427-145">仅包含显示名称</span><span class="sxs-lookup"><span data-stu-id="ed427-145">PR_DISPLAY_TO</span></span>  <br/> |<span data-ttu-id="ed427-146">如果一个或多个收件人**MAPI_TO**收件人，则设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ed427-146">Set to TRUE if one or more of the recipients are **MAPI_TO** recipients.</span></span>  <br/> |
|<span data-ttu-id="ed427-147">PR_DISPLAY_CC</span><span class="sxs-lookup"><span data-stu-id="ed427-147">PR_DISPLAY_CC</span></span>  <br/> |<span data-ttu-id="ed427-148">如果一个或多个收件人**MAPI_CC**收件人，则设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ed427-148">Set to TRUE if one or more of the recipients are **MAPI_CC** recipients.</span></span>  <br/> |
| <span data-ttu-id="ed427-149">PR_DISPLAY_BCC</span><span class="sxs-lookup"><span data-stu-id="ed427-149">PR_DISPLAY_BCC</span></span>  <br/> |<span data-ttu-id="ed427-150">如果一个或多个收件人**MAPI_BCC**收件人，则设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ed427-150">Set to TRUE if one or more of the recipients are **MAPI_BCC** recipients.</span></span>  <br/> |
   
<span data-ttu-id="ed427-151">在 X.400，P1 或传递信封是一条消息，包括收件人的地址属性和控制传递和回复任何选项标志提供所需的信息。</span><span class="sxs-lookup"><span data-stu-id="ed427-151">In X.400, the P1 or delivery envelope is the information needed to deliver a message, including the recipient's address properties and any option flags controlling delivery and replies.</span></span> <span data-ttu-id="ed427-152">P2 或显示信封是通常显示每个收件人的消息文本本身以外的信息。</span><span class="sxs-lookup"><span data-stu-id="ed427-152">The P2 or display envelope is the information usually displayed to each recipient other than the message text itself.</span></span> <span data-ttu-id="ed427-153">它通常包括主题、 重要性、 优先级、 敏感度，和提交时间，以及主要和复制收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="ed427-153">It typically includes the subject, importance, priority, sensitivity, and submission time, as well as the primary and copied recipient names.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ed427-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="ed427-154">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ed427-155">协议规范</span><span class="sxs-lookup"><span data-stu-id="ed427-155">Protocol specifications</span></span>

<span data-ttu-id="ed427-156">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed427-156">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ed427-157">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ed427-157">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ed427-158">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed427-158">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ed427-159">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="ed427-159">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ed427-160">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed427-160">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ed427-161">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="ed427-161">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="ed427-162">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed427-162">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ed427-163">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ed427-163">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ed427-164">头文件</span><span class="sxs-lookup"><span data-stu-id="ed427-164">Header files</span></span>

<span data-ttu-id="ed427-165">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ed427-165">Mapidefs.h</span></span>
  
> <span data-ttu-id="ed427-166">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ed427-166">Provides data type definitions.</span></span>
    
<span data-ttu-id="ed427-167">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ed427-167">Mapitags.h</span></span>
  
> <span data-ttu-id="ed427-168">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ed427-168">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ed427-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed427-169">See also</span></span>



[<span data-ttu-id="ed427-170">PidTagRecipientStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-170">PidTagRecipientStatus Canonical Property</span></span>](pidtagrecipientstatus-canonical-property.md)
  
[<span data-ttu-id="ed427-171">PidTagDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-171">PidTagDisplayTo Canonical Property</span></span>](pidtagdisplayto-canonical-property.md)
  
[<span data-ttu-id="ed427-172">PidTagDisplayBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-172">PidTagDisplayBcc Canonical Property</span></span>](pidtagdisplaybcc-canonical-property.md)
  
[<span data-ttu-id="ed427-173">PidTagDisplayCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-173">PidTagDisplayCc Canonical Property</span></span>](pidtagdisplaycc-canonical-property.md)


[<span data-ttu-id="ed427-174">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ed427-174">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ed427-175">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ed427-175">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ed427-176">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ed427-176">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ed427-177">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ed427-177">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

