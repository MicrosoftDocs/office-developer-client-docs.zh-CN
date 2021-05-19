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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d74fdb3acb6db94078d6090f0def050fb564cd9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355256"
---
# <a name="pidtagrecipienttype-canonical-property"></a><span data-ttu-id="ae602-103">PidTagRecipientType 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-103">PidTagRecipientType Canonical Property</span></span>

  
  
<span data-ttu-id="ae602-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae602-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae602-105">包含邮件收件人的收件人类型。</span><span class="sxs-lookup"><span data-stu-id="ae602-105">Contains the recipient type for a message recipient.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ae602-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ae602-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ae602-107">PR_RECIPIENT_TYPE</span><span class="sxs-lookup"><span data-stu-id="ae602-107">PR_RECIPIENT_TYPE</span></span>  <br/> |
|<span data-ttu-id="ae602-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ae602-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ae602-109">0x0C15</span><span class="sxs-lookup"><span data-stu-id="ae602-109">0x0C15</span></span>  <br/> |
|<span data-ttu-id="ae602-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ae602-110">Data type:</span></span>  <br/> |<span data-ttu-id="ae602-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ae602-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ae602-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ae602-112">Area:</span></span>  <br/> |<span data-ttu-id="ae602-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="ae602-113">MAPI recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ae602-114">备注</span><span class="sxs-lookup"><span data-stu-id="ae602-114">Remarks</span></span>

<span data-ttu-id="ae602-115">此属性中包含的收件人类型由一个必需值和一个可选标志组成。</span><span class="sxs-lookup"><span data-stu-id="ae602-115">The recipient type contained in this property consists of one required value and one optional flag.</span></span>
  
<span data-ttu-id="ae602-116">此属性必须仅包含下列值之一：</span><span class="sxs-lookup"><span data-stu-id="ae602-116">This property must contain exactly one of the following values:</span></span>
  
<span data-ttu-id="ae602-117">MAPI_TO</span><span class="sxs-lookup"><span data-stu-id="ae602-117">MAPI_TO</span></span> 
  
> <span data-ttu-id="ae602-118">收件人是收件人 () 收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-118">The recipient is a primary (To) recipient.</span></span> <span data-ttu-id="ae602-119">客户端需要处理主收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-119">Clients are required to handle primary recipients.</span></span> <span data-ttu-id="ae602-120">所有其他类型都是可选的。</span><span class="sxs-lookup"><span data-stu-id="ae602-120">All other types are optional.</span></span>
    
<span data-ttu-id="ae602-121">MAPI_CC</span><span class="sxs-lookup"><span data-stu-id="ae602-121">MAPI_CC</span></span> 
  
> <span data-ttu-id="ae602-122">收件人是抄送 (抄) 抄送收件人，即除了主要收件人之外接收邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-122">The recipient is a carbon copy (CC) recipient, a recipient that receives a message in addition to the primary recipients.</span></span>
    
<span data-ttu-id="ae602-123">MAPI_BCC</span><span class="sxs-lookup"><span data-stu-id="ae602-123">MAPI_BCC</span></span> 
  
> <span data-ttu-id="ae602-124">收件人是 BCC 收件人 (的) 副本。</span><span class="sxs-lookup"><span data-stu-id="ae602-124">The recipient is a blind carbon copy (BCC) recipient.</span></span> <span data-ttu-id="ae602-125">主要收件人和抄送收件人不知道是否存在 BCC 收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-125">Primary and carbon copy recipients are unaware of the existence of BCC recipients.</span></span> 
    
<span data-ttu-id="ae602-126">MAPI_P1</span><span class="sxs-lookup"><span data-stu-id="ae602-126">MAPI_P1</span></span> 
  
> <span data-ttu-id="ae602-127">收件人在上一次尝试中未成功收到邮件。</span><span class="sxs-lookup"><span data-stu-id="ae602-127">The recipient did not successfully receive the message on the previous attempt.</span></span> <span data-ttu-id="ae602-128">这是之前传输的重新发送。</span><span class="sxs-lookup"><span data-stu-id="ae602-128">This is a resend of an earlier transmission.</span></span>
    
<span data-ttu-id="ae602-129">此外，还可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ae602-129">In addition, the following flag can be set:</span></span>
  
<span data-ttu-id="ae602-130">MAPI_SUBMITTED</span><span class="sxs-lookup"><span data-stu-id="ae602-130">MAPI_SUBMITTED</span></span> 
  
> <span data-ttu-id="ae602-131">收件人已收到邮件，无需再次接收邮件。</span><span class="sxs-lookup"><span data-stu-id="ae602-131">The recipient has already received the message and does not need to receive it again.</span></span> <span data-ttu-id="ae602-132">这是之前传输的重新发送。</span><span class="sxs-lookup"><span data-stu-id="ae602-132">This is a resend of an earlier transmission.</span></span> <span data-ttu-id="ae602-133">此标志与值 MAPI_TO、MAPI_CC和 **MAPI_BCC\*\*\*\*一起** 设置。</span><span class="sxs-lookup"><span data-stu-id="ae602-133">This flag is set in conjunction with the **MAPI_TO**, **MAPI_CC**, and **MAPI_BCC** values.</span></span> 
    
<span data-ttu-id="ae602-134">由于MAPI_P1一个或多个目标收件人而重新传递邮件时，使用 MAPI_P1 值和 MAPI_SUBMITTED 标志。</span><span class="sxs-lookup"><span data-stu-id="ae602-134">The MAPI_P1 value and the **MAPI_SUBMITTED** flag are used when a message is being retransmitted due to nondelivery to one or more of the intended recipients.</span></span> <span data-ttu-id="ae602-135">对于此重新传输，客户端MAPI_SUBMITTED设置每个不需要再次发送邮件但应显示在收件人列表中的收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="ae602-135">For this retransmission, the client sets **MAPI_SUBMITTED** on every recipient that does not need the message again but should be displayed in the recipient list.</span></span> <span data-ttu-id="ae602-136">对于之前未收到邮件的每一个收件人，客户端会保留原始收件人的 **PR_RECIPIENT_TYPE** 值不变，但另外提交收件人的副本，MAPI_P1以更改原始值。</span><span class="sxs-lookup"><span data-stu-id="ae602-136">For every recipient that did not receive the message previously, the client retains the original recipient with its **PR_RECIPIENT_TYPE** value unchanged, but additionally submits a copy of the recipient with MAPI_P1 in place of the original value.</span></span> <span data-ttu-id="ae602-137">在实际传递之前放弃此副本会强制收件人进入 P1 信封，并保证实际重新传输给该收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-137">This copy, which is discarded before actual delivery, forces the recipient into the P1 envelope and guarantees physical retransmission to that recipient.</span></span> <span data-ttu-id="ae602-138">对于 **PR_RESPONSIBILITY (** [PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE，MAPI_P1 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ae602-138">The **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property is set to FALSE for MAPI_P1 recipients.</span></span>
  
<span data-ttu-id="ae602-139">当客户端显示重新发送窗体时，只有MAPI_P1收件人可见。</span><span class="sxs-lookup"><span data-stu-id="ae602-139">When a client displays a resend form, only the MAPI_P1 recipients are visible.</span></span> <span data-ttu-id="ae602-140">除非用户输入其他收件人，否则在邮件传递时，收件人列表的显示方式与首次发送邮件时完全相同。</span><span class="sxs-lookup"><span data-stu-id="ae602-140">Unless the user enters additional recipients, when the message is delivered, the recipient list appears exactly as it did when the message was sent for the first time.</span></span> 
  
<span data-ttu-id="ae602-141">[PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) PR_DISPLAY_TO (、PR_DISPLAY_CC ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和 **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) 属性与收件人类型相关。  </span><span class="sxs-lookup"><span data-stu-id="ae602-141">The **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)), **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) and **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)) properties are related to recipient type.</span></span> <span data-ttu-id="ae602-142">当客户端调用邮件 **的 IMAPIProp：：SaveChanges** 且收件人列表中至少有一个收件人时，邮件存储提供程序将按如下方式设置这些属性：</span><span class="sxs-lookup"><span data-stu-id="ae602-142">When a client calls a message's **IMAPIProp::SaveChanges** and there is at least one recipient in the recipient list, the message store provider sets these properties as follows:</span></span> 
  
|<span data-ttu-id="ae602-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="ae602-143">**Property**</span></span>|<span data-ttu-id="ae602-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae602-144">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae602-145">PR_DISPLAY_TO</span><span class="sxs-lookup"><span data-stu-id="ae602-145">PR_DISPLAY_TO</span></span>  <br/> |<span data-ttu-id="ae602-146">如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_TO** 收件人。</span><span class="sxs-lookup"><span data-stu-id="ae602-146">Set to TRUE if one or more of the recipients are **MAPI_TO** recipients.</span></span>  <br/> |
|<span data-ttu-id="ae602-147">PR_DISPLAY_CC</span><span class="sxs-lookup"><span data-stu-id="ae602-147">PR_DISPLAY_CC</span></span>  <br/> |<span data-ttu-id="ae602-148">如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_CC收件人** 。</span><span class="sxs-lookup"><span data-stu-id="ae602-148">Set to TRUE if one or more of the recipients are **MAPI_CC** recipients.</span></span>  <br/> |
| <span data-ttu-id="ae602-149">PR_DISPLAY_BCC</span><span class="sxs-lookup"><span data-stu-id="ae602-149">PR_DISPLAY_BCC</span></span>  <br/> |<span data-ttu-id="ae602-150">如果一个或多个收件人是收件人，则设置为 TRUE **MAPI_BCC收件人** 。</span><span class="sxs-lookup"><span data-stu-id="ae602-150">Set to TRUE if one or more of the recipients are **MAPI_BCC** recipients.</span></span>  <br/> |
   
<span data-ttu-id="ae602-151">在 X.400 中，P1 或传递信封是传递邮件时需要的信息，包括收件人的地址属性以及控制传递和答复的任何选项标志。</span><span class="sxs-lookup"><span data-stu-id="ae602-151">In X.400, the P1 or delivery envelope is the information needed to deliver a message, including the recipient's address properties and any option flags controlling delivery and replies.</span></span> <span data-ttu-id="ae602-152">P2 或显示信封是通常向除邮件文本本身外的其他每个收件人显示的信息。</span><span class="sxs-lookup"><span data-stu-id="ae602-152">The P2 or display envelope is the information usually displayed to each recipient other than the message text itself.</span></span> <span data-ttu-id="ae602-153">通常包括主题、重要性、优先级、敏感度和提交时间，以及主要和复制的收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="ae602-153">It typically includes the subject, importance, priority, sensitivity, and submission time, as well as the primary and copied recipient names.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ae602-154">相关资源</span><span class="sxs-lookup"><span data-stu-id="ae602-154">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ae602-155">协议规范</span><span class="sxs-lookup"><span data-stu-id="ae602-155">Protocol specifications</span></span>

<span data-ttu-id="ae602-156">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae602-156">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae602-157">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ae602-157">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ae602-158">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae602-158">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae602-159">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ae602-159">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ae602-160">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae602-160">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae602-161">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ae602-161">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="ae602-162">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae602-162">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae602-163">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ae602-163">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ae602-164">头文件</span><span class="sxs-lookup"><span data-stu-id="ae602-164">Header files</span></span>

<span data-ttu-id="ae602-165">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ae602-165">Mapidefs.h</span></span>
  
> <span data-ttu-id="ae602-166">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ae602-166">Provides data type definitions.</span></span>
    
<span data-ttu-id="ae602-167">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ae602-167">Mapitags.h</span></span>
  
> <span data-ttu-id="ae602-168">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ae602-168">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae602-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae602-169">See also</span></span>



[<span data-ttu-id="ae602-170">PidTagRecipientStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-170">PidTagRecipientStatus Canonical Property</span></span>](pidtagrecipientstatus-canonical-property.md)
  
[<span data-ttu-id="ae602-171">PidTagDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-171">PidTagDisplayTo Canonical Property</span></span>](pidtagdisplayto-canonical-property.md)
  
[<span data-ttu-id="ae602-172">PidTagDisplayBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-172">PidTagDisplayBcc Canonical Property</span></span>](pidtagdisplaybcc-canonical-property.md)
  
[<span data-ttu-id="ae602-173">PidTagDisplayCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-173">PidTagDisplayCc Canonical Property</span></span>](pidtagdisplaycc-canonical-property.md)


[<span data-ttu-id="ae602-174">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ae602-174">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ae602-175">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae602-175">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ae602-176">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ae602-176">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ae602-177">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ae602-177">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

