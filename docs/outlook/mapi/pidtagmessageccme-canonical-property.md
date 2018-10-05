---
title: PidTagMessageCcMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageCcMe
api_type:
- HeaderDef
ms.assetid: 7310a0f2-a109-40a4-99bf-e963d754a067
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7605739dd6d0f0205a1a4f09eb8c45d235c0c179
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389769"
---
# <a name="pidtagmessageccme-canonical-property"></a><span data-ttu-id="be8e7-103">PidTagMessageCcMe 规范属性</span><span class="sxs-lookup"><span data-stu-id="be8e7-103">PidTagMessageCcMe Canonical Property</span></span>

  
  
<span data-ttu-id="be8e7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be8e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be8e7-105">如果此消息的用户专门命名为此邮件的抄送 (CC) 收件人，而不是通讯组列表的一部分，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="be8e7-105">Contains TRUE if this messaging user is specifically named as a carbon copy (CC) recipient of this message and is not part of a distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="be8e7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="be8e7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="be8e7-107">PR_MESSAGE_CC_ME</span><span class="sxs-lookup"><span data-stu-id="be8e7-107">PR_MESSAGE_CC_ME</span></span>  <br/> |
|<span data-ttu-id="be8e7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="be8e7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="be8e7-109">0x0058</span><span class="sxs-lookup"><span data-stu-id="be8e7-109">0x0058</span></span>  <br/> |
|<span data-ttu-id="be8e7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="be8e7-110">Data type:</span></span>  <br/> |<span data-ttu-id="be8e7-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="be8e7-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="be8e7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="be8e7-112">Area:</span></span>  <br/> |<span data-ttu-id="be8e7-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="be8e7-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="be8e7-114">说明</span><span class="sxs-lookup"><span data-stu-id="be8e7-114">Remarks</span></span>

<span data-ttu-id="be8e7-115">此属性提供方便地确定是否用户名显式中出现抄送收件人列表中，如果不检查列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="be8e7-115">This property provides a convenient way to determine whether the user name appears explicitly in the carbon copy recipient list, without examining all entries in the list.</span></span> 
  
<span data-ttu-id="be8e7-116">此属性还可帮助您接收的消息的回执时的自动的处理。</span><span class="sxs-lookup"><span data-stu-id="be8e7-116">This property also assists automated handling of received messages at the time of receipt.</span></span> <span data-ttu-id="be8e7-117">在传输提供程序的选项，此属性包含 FALSE 或未设置如果直接在收件人的表中未列出的消息的用户。</span><span class="sxs-lookup"><span data-stu-id="be8e7-117">At the transport provider's option, this property either contains FALSE or is not set if the messaging user is not listed directly in the recipient table.</span></span> 
  
<span data-ttu-id="be8e7-118">通讯组列表扩展或密件抄送副本标识生成的邮件传递不会导致要设置此属性。</span><span class="sxs-lookup"><span data-stu-id="be8e7-118">Message delivery resulting from distribution list expansion or a blind carbon copy designation does not cause this property to be set.</span></span> <span data-ttu-id="be8e7-119">必须明确名为收件人。</span><span class="sxs-lookup"><span data-stu-id="be8e7-119">The recipient must be explicitly named.</span></span> 
  
<span data-ttu-id="be8e7-120">通常未发送的邮件不设置此属性， **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)) 或**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="be8e7-120">Unsent messages generally do not set this property, **PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md)), or **PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)).</span></span> <span data-ttu-id="be8e7-121">如果它们存在用户可以访问公共消息中的存储区，其他用户的专用存储在磁盘上的文件中或嵌入其他接收的消息，它们通常会包含到他们已设置的值的邮件在上一次传输提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="be8e7-121">If they are present in messages the user can access in public message stores, in other users' private stores, in files on disk, or embedded inside other received messages, they generally contain the values to which they were set the last time a transport provider delivered the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="be8e7-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="be8e7-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="be8e7-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="be8e7-123">Protocol specifications</span></span>

<span data-ttu-id="be8e7-124">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be8e7-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be8e7-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="be8e7-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="be8e7-126">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="be8e7-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="be8e7-127">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="be8e7-127">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="be8e7-128">头文件</span><span class="sxs-lookup"><span data-stu-id="be8e7-128">Header files</span></span>

<span data-ttu-id="be8e7-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="be8e7-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="be8e7-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="be8e7-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="be8e7-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="be8e7-131">Mapitags.h</span></span>
  
> <span data-ttu-id="be8e7-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="be8e7-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="be8e7-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be8e7-133">See also</span></span>



[<span data-ttu-id="be8e7-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="be8e7-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="be8e7-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="be8e7-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="be8e7-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="be8e7-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="be8e7-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="be8e7-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

