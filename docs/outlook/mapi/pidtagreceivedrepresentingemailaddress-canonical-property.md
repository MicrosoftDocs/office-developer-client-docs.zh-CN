---
title: PidTagReceivedRepresentingEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedRepresentingEmailAddress
api_type:
- COM
ms.assetid: f85ce31c-f621-47ed-badf-4f59a45ec0a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6916b1148caaf8283c6d7ae64ac2e05deb3ee0c3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359099"
---
# <a name="pidtagreceivedrepresentingemailaddress-canonical-property"></a><span data-ttu-id="24aa6-103">PidTagReceivedRepresentingEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="24aa6-103">PidTagReceivedRepresentingEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="24aa6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24aa6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24aa6-105">包含由接收用户表示的邮件用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="24aa6-105">Contains the email address for the messaging user who is represented by the receiving user.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24aa6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24aa6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24aa6-107">PR_RCVD_REPRESENTING_EMAIL_ADDRESS、PR_RCVD_REPRESENTING_EMAIL_ADDRESS_A、PR_RCVD_REPRESENTING_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="24aa6-107">PR_RCVD_REPRESENTING_EMAIL_ADDRESS, PR_RCVD_REPRESENTING_EMAIL_ADDRESS_A, PR_RCVD_REPRESENTING_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="24aa6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="24aa6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="24aa6-109">0x0078</span><span class="sxs-lookup"><span data-stu-id="24aa6-109">0x0078</span></span>  <br/> |
|<span data-ttu-id="24aa6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24aa6-110">Data type:</span></span>  <br/> |<span data-ttu-id="24aa6-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="24aa6-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="24aa6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="24aa6-112">Area:</span></span>  <br/> |<span data-ttu-id="24aa6-113">Address</span><span class="sxs-lookup"><span data-stu-id="24aa6-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24aa6-114">注解</span><span class="sxs-lookup"><span data-stu-id="24aa6-114">Remarks</span></span>

<span data-ttu-id="24aa6-115">这些属性是由接收用户表示的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="24aa6-115">These properties are examples of the address properties for the messaging user who is being represented by the receiving user.</span></span> <span data-ttu-id="24aa6-116">必须由传入传输提供程序 (它还负责授权或验证代理) 设置它们。</span><span class="sxs-lookup"><span data-stu-id="24aa6-116">They must be set by the incoming transport provider, which is also responsible for authorization or verification of the delegate.</span></span> <span data-ttu-id="24aa6-117">如果未表示邮件用户, 则应将这些属性设置为**PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md)) 属性中包含的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="24aa6-117">If no messaging user is being represented, these properties should be set to the email address contained in the **PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="24aa6-118">客户端应用程序答复代表另一个客户端收到的邮件时, 应将收到的邮件中的这些属性复制到**PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md)) 属性中。响应.</span><span class="sxs-lookup"><span data-stu-id="24aa6-118">A client application replying to a message received on behalf of another client should copy these properties from the received message into the **PR_SENT_REPRESENTING_EMAIL_ADDRESS** ([PidTagSentRepresentingEmailAddress](pidtagsentrepresentingemailaddress-canonical-property.md)) property for the reply.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="24aa6-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="24aa6-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24aa6-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="24aa6-120">Protocol specifications</span></span>

<span data-ttu-id="24aa6-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="24aa6-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="24aa6-123">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-124">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="24aa6-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="24aa6-125">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-125">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-126">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="24aa6-126">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="24aa6-127">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-127">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-128">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="24aa6-128">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="24aa6-129">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-129">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-130">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="24aa6-130">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="24aa6-131">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24aa6-131">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24aa6-132">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="24aa6-132">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24aa6-133">头文件</span><span class="sxs-lookup"><span data-stu-id="24aa6-133">Header files</span></span>

<span data-ttu-id="24aa6-134">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="24aa6-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="24aa6-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24aa6-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="24aa6-136">Mapitags</span><span class="sxs-lookup"><span data-stu-id="24aa6-136">Mapitags.h</span></span>
  
> <span data-ttu-id="24aa6-137">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="24aa6-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24aa6-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24aa6-138">See also</span></span>



[<span data-ttu-id="24aa6-139">PidTagEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="24aa6-139">PidTagEmailAddress Canonical Property</span></span>](pidtagemailaddress-canonical-property.md)


[<span data-ttu-id="24aa6-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24aa6-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24aa6-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24aa6-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24aa6-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24aa6-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24aa6-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24aa6-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

