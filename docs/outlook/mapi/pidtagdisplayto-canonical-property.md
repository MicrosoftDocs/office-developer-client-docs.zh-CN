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
ms.openlocfilehash: 0c7ae8951b02f099161871b17ff59ea23f8fbcc4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360786"
---
# <a name="pidtagdisplayto-canonical-property"></a><span data-ttu-id="bb47e-103">PidTagDisplayTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb47e-103">PidTagDisplayTo Canonical Property</span></span>

  
  
<span data-ttu-id="bb47e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb47e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb47e-105">包含主 (收件人) 邮件收件人的显示名称列表, 用分号 (;) 分隔)。</span><span class="sxs-lookup"><span data-stu-id="bb47e-105">Contains a list of the display names of the primary (To) message recipients, separated by semicolons (;).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb47e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bb47e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb47e-107">PR_DISPLAY_TO、PR_DISPLAY_TO_A、PR_DISPLAY_TO_W</span><span class="sxs-lookup"><span data-stu-id="bb47e-107">PR_DISPLAY_TO, PR_DISPLAY_TO_A, PR_DISPLAY_TO_W</span></span>  <br/> |
|<span data-ttu-id="bb47e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bb47e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bb47e-109">0x0E04</span><span class="sxs-lookup"><span data-stu-id="bb47e-109">0x0E04</span></span>  <br/> |
|<span data-ttu-id="bb47e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb47e-110">Data type:</span></span>  <br/> |<span data-ttu-id="bb47e-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="bb47e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="bb47e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bb47e-112">Area:</span></span>  <br/> |<span data-ttu-id="bb47e-113">消息</span><span class="sxs-lookup"><span data-stu-id="bb47e-113">Message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb47e-114">注解</span><span class="sxs-lookup"><span data-stu-id="bb47e-114">Remarks</span></span>

<span data-ttu-id="bb47e-115">邮件存储区使用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法计算邮件对象上的这些属性。</span><span class="sxs-lookup"><span data-stu-id="bb47e-115">The message store computes these properties on message objects by using the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="bb47e-116">邮件存储区还将维护这些属性, 以便它始终反映邮件的上次保存状态。</span><span class="sxs-lookup"><span data-stu-id="bb47e-116">The message store also maintains these properties so that it always reflects the last saved state of a message.</span></span> <span data-ttu-id="bb47e-117">值在每次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时进行同步。</span><span class="sxs-lookup"><span data-stu-id="bb47e-117">The value is synchronized at the time of every call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="bb47e-118">如果邮件没有主收件人, 则邮件存储应响应返回值 S_OK 的[IMAPIProp:: GetProps](imapiprop-getprops.md)调用和**PR_DISPLAY_TO**的空字符串。</span><span class="sxs-lookup"><span data-stu-id="bb47e-118">If a message has no primary recipients, the message store should respond to an [IMAPIProp::GetProps](imapiprop-getprops.md) call with a return value of S_OK and an empty string for **PR_DISPLAY_TO**.</span></span> 
  
<span data-ttu-id="bb47e-119">出于本地化的可能需要, MAPI 为所有收件人名称提供了以下准则:</span><span class="sxs-lookup"><span data-stu-id="bb47e-119">Because of the possible need for localization, MAPI provides these guidelines for all recipient names:</span></span>
  
- <span data-ttu-id="bb47e-120">所有名称都应能够本地化。</span><span class="sxs-lookup"><span data-stu-id="bb47e-120">All names should be able to be localized.</span></span> 
    
- <span data-ttu-id="bb47e-121">分号应为用于分隔**PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))、 **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和**PR_DISPLAY_TO**属性中的名称的字符。</span><span class="sxs-lookup"><span data-stu-id="bb47e-121">The semicolon should be the character that is used to separate names in the **PR_DISPLAY_BCC** ([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md)), **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)), and **PR_DISPLAY_TO** properties.</span></span> <span data-ttu-id="bb47e-122">MAPI 中的收件人名称内不允许使用分号。</span><span class="sxs-lookup"><span data-stu-id="bb47e-122">Semicolons are not permitted within recipient names in MAPI.</span></span> 
    
- <span data-ttu-id="bb47e-123">客户端应将在**PR_DISPLAY_TO**和相关属性中遇到的每个分号转换为本地化的分隔符, 然后再使信息在用户界面中可见。</span><span class="sxs-lookup"><span data-stu-id="bb47e-123">Clients should translate each semicolon encountered in the **PR_DISPLAY_TO** and related properties to a localized separator character before making the information visible in the user interface.</span></span> 
    
- <span data-ttu-id="bb47e-124">转发邮件时, 客户端无需翻译主收件人行上的分隔符。</span><span class="sxs-lookup"><span data-stu-id="bb47e-124">When forwarding messages, clients do not need to translate the separator characters on the primary recipient line.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="bb47e-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb47e-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb47e-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb47e-126">Protocol specifications</span></span>

<span data-ttu-id="bb47e-127">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb47e-127">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb47e-128">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="bb47e-128">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bb47e-129">头文件</span><span class="sxs-lookup"><span data-stu-id="bb47e-129">Header files</span></span>

<span data-ttu-id="bb47e-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="bb47e-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb47e-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb47e-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="bb47e-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="bb47e-132">Mapitags.h</span></span>
  
> <span data-ttu-id="bb47e-133">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bb47e-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb47e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb47e-134">See also</span></span>



[<span data-ttu-id="bb47e-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb47e-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb47e-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb47e-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb47e-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bb47e-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb47e-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb47e-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

