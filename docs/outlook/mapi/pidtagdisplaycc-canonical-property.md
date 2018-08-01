---
title: PidTagDisplayCc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayCc
api_type:
- HeaderDef
ms.assetid: 00377e78-a208-4942-a7a6-893b2a71ab0b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6257557a8848c1abbaf8ceb15f719c50e4fec8c4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777570"
---
# <a name="pidtagdisplaycc-canonical-property"></a><span data-ttu-id="f229f-103">PidTagDisplayCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="f229f-103">PidTagDisplayCc Canonical Property</span></span>

  
  
<span data-ttu-id="f229f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f229f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f229f-105">包含任何抄送 (CC) 收件人，用分号 （;） 分隔的显示名称 ASCII 的列表。</span><span class="sxs-lookup"><span data-stu-id="f229f-105">Contains an ASCII list of the display names of any carbon copy (CC) message recipients, separated by semicolons (;).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f229f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f229f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f229f-107">PR_DISPLAY_CC，PR_DISPLAY_CC_A，PR_DISPLAY_CC_W</span><span class="sxs-lookup"><span data-stu-id="f229f-107">PR_DISPLAY_CC, PR_DISPLAY_CC_A, PR_DISPLAY_CC_W</span></span>  <br/> |
|<span data-ttu-id="f229f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f229f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f229f-109">0x0E03</span><span class="sxs-lookup"><span data-stu-id="f229f-109">0x0E03</span></span>  <br/> |
|<span data-ttu-id="f229f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f229f-110">Data type:</span></span>  <br/> |<span data-ttu-id="f229f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f229f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f229f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f229f-112">Area:</span></span>  <br/> |<span data-ttu-id="f229f-113">Message</span><span class="sxs-lookup"><span data-stu-id="f229f-113">Message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f229f-114">说明</span><span class="sxs-lookup"><span data-stu-id="f229f-114">Remarks</span></span>

<span data-ttu-id="f229f-115">消息存储库使用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法计算这些消息对象的属性。</span><span class="sxs-lookup"><span data-stu-id="f229f-115">The message store computes these properties on message objects by using the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="f229f-116">消息存储还维护这些属性，以便它始终反映消息的上次保存的状态。</span><span class="sxs-lookup"><span data-stu-id="f229f-116">The message store also maintains these properties so that it always reflects the last saved state of a message.</span></span> <span data-ttu-id="f229f-117">在每次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)时同步值。</span><span class="sxs-lookup"><span data-stu-id="f229f-117">The value is synchronized at the time of every call to [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span> 
  
<span data-ttu-id="f229f-118">如果邮件没有抄送收件人，消息存储应当给出答复的返回值为 S_OK 和这些属性为空字符串[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫。</span><span class="sxs-lookup"><span data-stu-id="f229f-118">If a message has no carbon copy recipients, the message store should respond to an [IMAPIProp::GetProps](imapiprop-getprops.md) call with a return value of S_OK and an empty string for these properties.</span></span> 
  
<span data-ttu-id="f229f-119">由于可能需要本地化，MAPI 为所有收件人姓名提供以下准则：</span><span class="sxs-lookup"><span data-stu-id="f229f-119">Because of the possible need for localization, MAPI provides these guidelines for all recipient names:</span></span>
  
- <span data-ttu-id="f229f-120">所有名称应该都能够都进行本地化。</span><span class="sxs-lookup"><span data-stu-id="f229f-120">All names should be able to be localized.</span></span> 
    
- <span data-ttu-id="f229f-121">分号应为用于分隔名称**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC**和**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 属性中的字符。</span><span class="sxs-lookup"><span data-stu-id="f229f-121">The semicolon should be the character that is used to separate names in the **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)), **PR_DISPLAY_CC**, and **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) properties.</span></span> <span data-ttu-id="f229f-122">MAPI 中的收件人姓名内不允许使用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="f229f-122">Semicolons are not permitted within recipient names in MAPI.</span></span> 
    
- <span data-ttu-id="f229f-123">客户端应翻译使属性信息的用户界面中可见之前遇到本地化的分隔符对此属性中的每个分号。</span><span class="sxs-lookup"><span data-stu-id="f229f-123">Clients should translate each semicolon encountered in this property to a localized separator character before making the property information visible in the user interface.</span></span> 
    
- <span data-ttu-id="f229f-124">将邮件转发，当客户端不需要翻译抄送收件人行上的分隔符。</span><span class="sxs-lookup"><span data-stu-id="f229f-124">When forwarding messages, clients do not need to translate the separator characters on the carbon copy recipient line.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="f229f-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="f229f-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f229f-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="f229f-126">Protocol specifications</span></span>

<span data-ttu-id="f229f-127">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f229f-127">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f229f-128">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="f229f-128">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f229f-129">头文件</span><span class="sxs-lookup"><span data-stu-id="f229f-129">Header files</span></span>

<span data-ttu-id="f229f-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f229f-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="f229f-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f229f-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="f229f-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f229f-132">Mapitags.h</span></span>
  
> <span data-ttu-id="f229f-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f229f-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f229f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f229f-134">See also</span></span>



[<span data-ttu-id="f229f-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f229f-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f229f-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f229f-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f229f-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f229f-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f229f-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f229f-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

