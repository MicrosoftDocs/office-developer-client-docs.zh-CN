---
title: PidTagDisplayTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayTo
api_type:
- HeaderDef
ms.assetid: 700cc03b-5d98-40ce-adb5-a11fdac8aa28
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 79a0307aaf8b91a50485234acc2e1cbdd2314b47
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574165"
---
# <a name="pidtagdisplayto-canonical-property"></a><span data-ttu-id="2592c-103">PidTagDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="2592c-103">PidTagDisplayTo Canonical Property</span></span>

  
  
<span data-ttu-id="2592c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2592c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2592c-105">包含主 （方法） 邮件的收件人，用分号 （;） 分隔的显示名称的列表。</span><span class="sxs-lookup"><span data-stu-id="2592c-105">Contains a list of the display names of the primary (To) message recipients, separated by semicolons (;).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2592c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2592c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2592c-107">仅包含显示名称，PR_DISPLAY_TO_A，PR_DISPLAY_TO_W</span><span class="sxs-lookup"><span data-stu-id="2592c-107">PR_DISPLAY_TO, PR_DISPLAY_TO_A, PR_DISPLAY_TO_W</span></span>  <br/> |
|<span data-ttu-id="2592c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2592c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2592c-109">0x0E04</span><span class="sxs-lookup"><span data-stu-id="2592c-109">0x0E04</span></span>  <br/> |
|<span data-ttu-id="2592c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2592c-110">Data type:</span></span>  <br/> |<span data-ttu-id="2592c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2592c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2592c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2592c-112">Area:</span></span>  <br/> |<span data-ttu-id="2592c-113">Message</span><span class="sxs-lookup"><span data-stu-id="2592c-113">Message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2592c-114">注解</span><span class="sxs-lookup"><span data-stu-id="2592c-114">Remarks</span></span>

<span data-ttu-id="2592c-115">消息存储库使用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法计算这些消息对象的属性。</span><span class="sxs-lookup"><span data-stu-id="2592c-115">The message store computes these properties on message objects by using the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="2592c-116">消息存储还维护这些属性，以便它始终反映消息的上次保存的状态。</span><span class="sxs-lookup"><span data-stu-id="2592c-116">The message store also maintains these properties so that it always reflects the last saved state of a message.</span></span> <span data-ttu-id="2592c-117">在每次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法时同步值。</span><span class="sxs-lookup"><span data-stu-id="2592c-117">The value is synchronized at the time of every call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="2592c-118">如果邮件没有主收件人，消息存储应**仅包含显示名称**的响应返回 S_OK 和为空字符串值的[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫中。</span><span class="sxs-lookup"><span data-stu-id="2592c-118">If a message has no primary recipients, the message store should respond to an [IMAPIProp::GetProps](imapiprop-getprops.md) call with a return value of S_OK and an empty string for **PR_DISPLAY_TO**.</span></span> 
  
<span data-ttu-id="2592c-119">由于可能需要本地化，MAPI 为所有收件人姓名提供以下准则：</span><span class="sxs-lookup"><span data-stu-id="2592c-119">Because of the possible need for localization, MAPI provides these guidelines for all recipient names:</span></span>
  
- <span data-ttu-id="2592c-120">所有名称应该都能够都进行本地化。</span><span class="sxs-lookup"><span data-stu-id="2592c-120">All names should be able to be localized.</span></span> 
    
- <span data-ttu-id="2592c-121">分号应为用于分隔名称**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**仅包含显示名称**属性中的字符。</span><span class="sxs-lookup"><span data-stu-id="2592c-121">The semicolon should be the character that is used to separate names in the **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)), **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)), and **PR_DISPLAY_TO** properties.</span></span> <span data-ttu-id="2592c-122">MAPI 中的收件人姓名内不允许使用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="2592c-122">Semicolons are not permitted within recipient names in MAPI.</span></span> 
    
- <span data-ttu-id="2592c-123">客户端应翻译遇到的每个分号中**仅包含显示名称**和相关的属性设置为之前使信息在用户界面中可见本地化的分隔符。</span><span class="sxs-lookup"><span data-stu-id="2592c-123">Clients should translate each semicolon encountered in the **PR_DISPLAY_TO** and related properties to a localized separator character before making the information visible in the user interface.</span></span> 
    
- <span data-ttu-id="2592c-124">将邮件转发，当客户端不需要翻译主收件人行上的分隔符。</span><span class="sxs-lookup"><span data-stu-id="2592c-124">When forwarding messages, clients do not need to translate the separator characters on the primary recipient line.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="2592c-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="2592c-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2592c-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="2592c-126">Protocol specifications</span></span>

<span data-ttu-id="2592c-127">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2592c-127">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2592c-128">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="2592c-128">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2592c-129">头文件</span><span class="sxs-lookup"><span data-stu-id="2592c-129">Header files</span></span>

<span data-ttu-id="2592c-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2592c-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="2592c-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2592c-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="2592c-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2592c-132">Mapitags.h</span></span>
  
> <span data-ttu-id="2592c-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2592c-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2592c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2592c-134">See also</span></span>



[<span data-ttu-id="2592c-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2592c-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2592c-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2592c-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2592c-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2592c-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2592c-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2592c-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

