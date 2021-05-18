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
ms.openlocfilehash: 74669d102462e1a825568615d1d30346e99e90a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360814"
---
# <a name="pidtagdisplaybcc-canonical-property"></a><span data-ttu-id="da58a-103">PidTagDisplayBcc 规范属性</span><span class="sxs-lookup"><span data-stu-id="da58a-103">PidTagDisplayBcc Canonical Property</span></span>

  
  
<span data-ttu-id="da58a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da58a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da58a-105">包含任何"BCC"邮件收件人的"BCC (") 的显示名称的 ASCII 列表，用分号 (;) 。</span><span class="sxs-lookup"><span data-stu-id="da58a-105">Contains an ASCII list of the display names of any blind carbon copy (BCC) message recipients, separated by semicolons (;).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="da58a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="da58a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="da58a-107">PR_DISPLAY_BCC、PR_DISPLAY_BCC_A、PR_DISPLAY_BCC_W</span><span class="sxs-lookup"><span data-stu-id="da58a-107">PR_DISPLAY_BCC, PR_DISPLAY_BCC_A, PR_DISPLAY_BCC_W</span></span>  <br/> |
|<span data-ttu-id="da58a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="da58a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="da58a-109">0x0E02</span><span class="sxs-lookup"><span data-stu-id="da58a-109">0x0E02</span></span>  <br/> |
|<span data-ttu-id="da58a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="da58a-110">Data type:</span></span>  <br/> |<span data-ttu-id="da58a-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="da58a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="da58a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="da58a-112">Area:</span></span>  <br/> |<span data-ttu-id="da58a-113">邮件</span><span class="sxs-lookup"><span data-stu-id="da58a-113">Message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="da58a-114">备注</span><span class="sxs-lookup"><span data-stu-id="da58a-114">Remarks</span></span>

<span data-ttu-id="da58a-115">邮件存储使用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法计算 message 对象上的这些属性。</span><span class="sxs-lookup"><span data-stu-id="da58a-115">The message store computes these properties on message objects by using the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> <span data-ttu-id="da58a-116">邮件存储还维护这些属性，以便它始终反映邮件的上次保存状态。</span><span class="sxs-lookup"><span data-stu-id="da58a-116">The message store also maintains these properties so that it always reflects the last saved state of a message.</span></span> <span data-ttu-id="da58a-117">每次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法时，将同步该值。</span><span class="sxs-lookup"><span data-stu-id="da58a-117">The value is synchronized at the time of every call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="da58a-118">如果邮件没有"无邮件副本"收件人，则邮件存储应响应 [IMAPIProp：：GetProps](imapiprop-getprops.md) 调用，其返回值为 S_OK 且空字符串表示 **PR_DISPLAY_BCC**。</span><span class="sxs-lookup"><span data-stu-id="da58a-118">If a message has no blind carbon copy recipients, the message store should respond to an [IMAPIProp::GetProps](imapiprop-getprops.md) call with a return value of S_OK and an empty string for **PR_DISPLAY_BCC**.</span></span> 
  
<span data-ttu-id="da58a-119">由于可能需要进行本地化，MAPI 针对所有收件人姓名提供了以下指南：</span><span class="sxs-lookup"><span data-stu-id="da58a-119">Because of the possible need for localization, MAPI provides these guidelines for all recipient names:</span></span>
  
- <span data-ttu-id="da58a-120">所有名称都应能够本地化。</span><span class="sxs-lookup"><span data-stu-id="da58a-120">All names should be able to be localized.</span></span> 
    
- <span data-ttu-id="da58a-121">分号应为用于分隔 **PR_DISPLAY_BCC、PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) 和 PR_DISPLAY_TO ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) 属性中的名称的字符。</span><span class="sxs-lookup"><span data-stu-id="da58a-121">The semicolon should be the character that is used to separate names in the **PR_DISPLAY_BCC**, **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)), and **PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) properties.</span></span> <span data-ttu-id="da58a-122">MAPI 中的收件人名称中不允许使用分号。</span><span class="sxs-lookup"><span data-stu-id="da58a-122">Semicolons are not permitted within recipient names in MAPI.</span></span> 
    
- <span data-ttu-id="da58a-123">客户端应在用户界面中显示属性信息之前，将此属性中遇到的每个分号转换为本地化分隔符。</span><span class="sxs-lookup"><span data-stu-id="da58a-123">Clients should translate each semicolon encountered in this property to a localized separator character before making the property information visible in the user interface.</span></span> 
    
- <span data-ttu-id="da58a-124">转发邮件时，客户端无需翻译"抄稿收件人行"上的分隔符。</span><span class="sxs-lookup"><span data-stu-id="da58a-124">When forwarding messages, clients do not need to translate the separator characters on the blind carbon copy recipient line.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="da58a-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="da58a-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="da58a-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="da58a-126">Protocol specifications</span></span>

<span data-ttu-id="da58a-127">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="da58a-127">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="da58a-128">描述用于发送与客户端上的共享文件夹有关的信息的邮件的格式。</span><span class="sxs-lookup"><span data-stu-id="da58a-128">Describes the format of messages used to send information related to sharing folders on the client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="da58a-129">头文件</span><span class="sxs-lookup"><span data-stu-id="da58a-129">Header files</span></span>

<span data-ttu-id="da58a-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="da58a-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="da58a-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="da58a-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="da58a-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="da58a-132">Mapitags.h</span></span>
  
> <span data-ttu-id="da58a-133">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="da58a-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da58a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da58a-134">See also</span></span>



[<span data-ttu-id="da58a-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="da58a-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="da58a-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="da58a-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="da58a-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="da58a-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="da58a-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="da58a-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

