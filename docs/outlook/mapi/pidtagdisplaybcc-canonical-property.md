---
title: PidTagDisplayBcc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayBcc
api_type:
- HeaderDef
ms.assetid: ab5bcd67-d54e-46e9-b94e-a652aac3e81c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 55ee55fefd82f29c8b780a350ecdfe0285b3d649
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777564"
---
# <a name="pidtagdisplaybcc-canonical-property"></a><span data-ttu-id="3f286-103">PidTagDisplayBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f286-103">PidTagDisplayBcc Canonical Property</span></span>

  
  
<span data-ttu-id="3f286-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3f286-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3f286-105">包含任何密件抄送 (BCC) 邮件的收件人，用分号 （;） 分隔的显示名称 ASCII 的列表。</span><span class="sxs-lookup"><span data-stu-id="3f286-105">Contains an ASCII list of the display names of any blind carbon copy (BCC) message recipients, separated by semicolons (;).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3f286-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3f286-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3f286-107">PR_DISPLAY_BCC，PR_DISPLAY_BCC_A，PR_DISPLAY_BCC_W</span><span class="sxs-lookup"><span data-stu-id="3f286-107">PR_DISPLAY_BCC, PR_DISPLAY_BCC_A, PR_DISPLAY_BCC_W</span></span>  <br/> |
|<span data-ttu-id="3f286-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3f286-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3f286-109">0x0E02</span><span class="sxs-lookup"><span data-stu-id="3f286-109">0x0E02</span></span>  <br/> |
|<span data-ttu-id="3f286-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3f286-110">Data type:</span></span>  <br/> |<span data-ttu-id="3f286-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3f286-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3f286-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3f286-112">Area:</span></span>  <br/> |<span data-ttu-id="3f286-113">Message</span><span class="sxs-lookup"><span data-stu-id="3f286-113">Message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3f286-114">说明</span><span class="sxs-lookup"><span data-stu-id="3f286-114">Remarks</span></span>

<span data-ttu-id="3f286-115">消息存储库使用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法计算这些消息对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3f286-115">The message store computes these properties on message objects by using the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="3f286-116">消息存储还维护这些属性，以便它始终反映消息的上次保存的状态。</span><span class="sxs-lookup"><span data-stu-id="3f286-116">The message store also maintains these properties so that it always reflects the last saved state of a message.</span></span> <span data-ttu-id="3f286-117">在每次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法时同步值。</span><span class="sxs-lookup"><span data-stu-id="3f286-117">The value is synchronized at the time of every call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="3f286-118">如果邮件没有密件抄送收件人，消息存储应响应**PR_DISPLAY_BCC** [IMAPIProp::GetProps](imapiprop-getprops.md)呼叫的返回值为 S_OK 和为空字符串。</span><span class="sxs-lookup"><span data-stu-id="3f286-118">If a message has no blind carbon copy recipients, the message store should respond to an [IMAPIProp::GetProps](imapiprop-getprops.md) call with a return value of S_OK and an empty string for **PR_DISPLAY_BCC**.</span></span> 
  
<span data-ttu-id="3f286-119">由于可能需要本地化，MAPI 为所有收件人姓名提供以下准则：</span><span class="sxs-lookup"><span data-stu-id="3f286-119">Because of the possible need for localization, MAPI provides these guidelines for all recipient names:</span></span>
  
- <span data-ttu-id="3f286-120">所有名称应该都能够都进行本地化。</span><span class="sxs-lookup"><span data-stu-id="3f286-120">All names should be able to be localized.</span></span> 
    
- <span data-ttu-id="3f286-121">分号应为用于分隔名称**PR_DISPLAY_BCC**、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 属性中的字符。</span><span class="sxs-lookup"><span data-stu-id="3f286-121">The semicolon should be the character that is used to separate names in the **PR_DISPLAY_BCC**, **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)), and **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) properties.</span></span> <span data-ttu-id="3f286-122">MAPI 中的收件人姓名内不允许使用分号分隔。</span><span class="sxs-lookup"><span data-stu-id="3f286-122">Semicolons are not permitted within recipient names in MAPI.</span></span> 
    
- <span data-ttu-id="3f286-123">客户端应翻译使属性信息的用户界面中可见之前遇到本地化的分隔符对此属性中的每个分号。</span><span class="sxs-lookup"><span data-stu-id="3f286-123">Clients should translate each semicolon encountered in this property to a localized separator character before making the property information visible in the user interface.</span></span> 
    
- <span data-ttu-id="3f286-124">将邮件转发，当客户端不需要翻译密件抄送副本收件人行上的分隔符。</span><span class="sxs-lookup"><span data-stu-id="3f286-124">When forwarding messages, clients do not need to translate the separator characters on the blind carbon copy recipient line.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="3f286-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="3f286-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3f286-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="3f286-126">Protocol specifications</span></span>

<span data-ttu-id="3f286-127">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3f286-127">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3f286-128">介绍用于发送到客户端上共享文件夹相关的信息的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="3f286-128">Describes the format of messages used to send information related to sharing folders on the client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3f286-129">头文件</span><span class="sxs-lookup"><span data-stu-id="3f286-129">Header files</span></span>

<span data-ttu-id="3f286-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3f286-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="3f286-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3f286-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="3f286-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3f286-132">Mapitags.h</span></span>
  
> <span data-ttu-id="3f286-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3f286-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3f286-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f286-134">See also</span></span>



[<span data-ttu-id="3f286-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3f286-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3f286-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3f286-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3f286-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3f286-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3f286-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3f286-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

