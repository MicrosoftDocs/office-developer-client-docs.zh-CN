---
title: PidTagMessageRecipientMe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageRecipientMe
api_type:
- HeaderDef
ms.assetid: 90333258-8913-4f98-aefb-4cc2ab34abcf
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e8ae52df1dd9775f706e2b1b2dc8b17b1f47a0bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777877"
---
# <a name="pidtagmessagerecipientme-canonical-property"></a><span data-ttu-id="a0029-103">PidTagMessageRecipientMe 规范属性</span><span class="sxs-lookup"><span data-stu-id="a0029-103">PidTagMessageRecipientMe Canonical Property</span></span>

  
  
<span data-ttu-id="a0029-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a0029-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a0029-105">如果此消息的用户 （收件人）、 抄送 (CC) 或此邮件的密件抄送 (BCC) 收件人为主专门名为而不是通讯组列表的一部分，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a0029-105">Contains TRUE if this messaging user is specifically named as a primary (To), carbon copy (CC), or blind carbon copy (BCC) recipient of this message and is not part of a distribution list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a0029-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="a0029-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a0029-107">PR_MESSAGE_RECIP_ME</span><span class="sxs-lookup"><span data-stu-id="a0029-107">PR_MESSAGE_RECIP_ME</span></span>  <br/> |
|<span data-ttu-id="a0029-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a0029-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a0029-109">0x0059</span><span class="sxs-lookup"><span data-stu-id="a0029-109">0x0059</span></span>  <br/> |
|<span data-ttu-id="a0029-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a0029-110">Data type:</span></span>  <br/> |<span data-ttu-id="a0029-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a0029-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a0029-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a0029-112">Area:</span></span>  <br/> |<span data-ttu-id="a0029-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="a0029-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a0029-114">备注</span><span class="sxs-lookup"><span data-stu-id="a0029-114">Remarks</span></span>

<span data-ttu-id="a0029-115">此属性提供方便地确定是否用户名显示显式在收件人列表中，如果不检查列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="a0029-115">This property provides a convenient way to determine whether the user name appears explicitly in the recipient list, without examining all entries in the list.</span></span> <span data-ttu-id="a0029-116">值表示逻辑**或**运算属性**PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)) 和**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)) 和密件抄送信息 (其否则未显示在属性）。</span><span class="sxs-lookup"><span data-stu-id="a0029-116">The value represents the logical **OR** operation of the properties **PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md)) and **PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md)), and the BCC information (which does not otherwise appear in a property).</span></span> 
  
<span data-ttu-id="a0029-117">此属性可帮助您接收的消息的回执时的自动的处理。</span><span class="sxs-lookup"><span data-stu-id="a0029-117">This property assists automated handling of received messages at the time of receipt.</span></span> <span data-ttu-id="a0029-118">在传输提供程序的选项，此属性包含 FALSE 或时不包括直接在收件人的表中未列出的消息的用户。</span><span class="sxs-lookup"><span data-stu-id="a0029-118">At the transport provider's option, this property either contains FALSE or is not included if the messaging user is not listed directly in the recipient table.</span></span> 
  
<span data-ttu-id="a0029-119">邮件传递的通讯组列表扩展的结果不会导致要设置此属性。</span><span class="sxs-lookup"><span data-stu-id="a0029-119">Message delivery that results from distribution list expansion does not cause this property to be set.</span></span> <span data-ttu-id="a0029-120">必须明确名为收件人。</span><span class="sxs-lookup"><span data-stu-id="a0029-120">The recipient must be explicitly named.</span></span> 
  
<span data-ttu-id="a0029-121">通常未发送的邮件不设置此属性、 **PR_MESSAGE_CC_ME**或**PR_MESSAGE_TO_ME**。</span><span class="sxs-lookup"><span data-stu-id="a0029-121">Unsent messages generally do not set this property, **PR_MESSAGE_CC_ME**, or **PR_MESSAGE_TO_ME**.</span></span> <span data-ttu-id="a0029-122">如果它们存在用户可以访问公共消息中的存储区，其他用户的专用存储在磁盘上的文件中或嵌入其他接收的消息，它们通常会包含到他们已设置的值的邮件在上一次传输提供程序发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a0029-122">If they are present in messages the user can access in public message stores, in other users' private stores, in files on disk, or embedded inside other received messages, they generally contain the values to which they were set the last time a transport provider delivered the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a0029-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="a0029-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a0029-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="a0029-124">Protocol specifications</span></span>

<span data-ttu-id="a0029-125">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0029-125">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0029-126">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a0029-126">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a0029-127">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a0029-127">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a0029-128">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="a0029-128">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a0029-129">头文件</span><span class="sxs-lookup"><span data-stu-id="a0029-129">Header files</span></span>

<span data-ttu-id="a0029-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a0029-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="a0029-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a0029-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="a0029-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a0029-132">Mapitags.h</span></span>
  
> <span data-ttu-id="a0029-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a0029-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a0029-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0029-134">See also</span></span>



[<span data-ttu-id="a0029-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a0029-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a0029-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a0029-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a0029-137">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a0029-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a0029-138">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a0029-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

