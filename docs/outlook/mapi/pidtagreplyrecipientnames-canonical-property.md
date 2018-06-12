---
title: PidTagReplyRecipientNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientNames
api_type:
- COM
ms.assetid: f5ae6124-3e44-400f-95c2-24b19f3085b5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5abbe14576bec9f03f0b1bf5578b68032f95f8a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778200"
---
# <a name="pidtagreplyrecipientnames-canonical-property"></a><span data-ttu-id="63834-103">PidTagReplyRecipientNames 规范属性</span><span class="sxs-lookup"><span data-stu-id="63834-103">PidTagReplyRecipientNames Canonical Property</span></span>

  
  
<span data-ttu-id="63834-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="63834-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="63834-105">包含要获取回复的收件人的显示名称的列表。</span><span class="sxs-lookup"><span data-stu-id="63834-105">Contains a list of display names for recipients that are to get a reply.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="63834-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="63834-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="63834-107">PR_REPLY_RECIPIENT_NAMES，PR_REPLY_RECIPIENT_NAMES_A，PR_REPLY_RECIPIENT_NAMES_W</span><span class="sxs-lookup"><span data-stu-id="63834-107">PR_REPLY_RECIPIENT_NAMES, PR_REPLY_RECIPIENT_NAMES_A, PR_REPLY_RECIPIENT_NAMES_W</span></span>  <br/> |
|<span data-ttu-id="63834-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="63834-108">Identifier:</span></span>  <br/> |<span data-ttu-id="63834-109">0x0050</span><span class="sxs-lookup"><span data-stu-id="63834-109">0x0050</span></span>  <br/> |
|<span data-ttu-id="63834-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="63834-110">Data type:</span></span>  <br/> |<span data-ttu-id="63834-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="63834-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="63834-112">区域：</span><span class="sxs-lookup"><span data-stu-id="63834-112">Area:</span></span>  <br/> |<span data-ttu-id="63834-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="63834-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="63834-114">备注</span><span class="sxs-lookup"><span data-stu-id="63834-114">Remarks</span></span>

<span data-ttu-id="63834-115">这些属性包含由分号分隔的显示名称。</span><span class="sxs-lookup"><span data-stu-id="63834-115">These properties contain the display names separated by semicolons.</span></span>
  
<span data-ttu-id="63834-116">当此属性不存在时，仅对**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性标识的用户发送答复。</span><span class="sxs-lookup"><span data-stu-id="63834-116">When this property is not present, a reply is sent only to the user identified by the **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) property.</span></span> <span data-ttu-id="63834-117">定义了**PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) 和这些属性，向所有由这两个属性标识的收件人发送答复。</span><span class="sxs-lookup"><span data-stu-id="63834-117">When **PR_REPLY_RECIPIENT_ENTRIES** ([PidTagReplyRecipientEntries](pidtagreplyrecipiententries-canonical-property.md)) and these properties are defined, the reply is sent to all of the recipients identified by these two properties.</span></span> <span data-ttu-id="63834-118">传输提供程序使用这些属性重写通常的应答逻辑。</span><span class="sxs-lookup"><span data-stu-id="63834-118">A transport provider uses these properties to override the usual reply logic.</span></span>
  
<span data-ttu-id="63834-119">如果设置**PR_REPLY_RECIPIENT_ENTRIES**或这些属性，还必须设置其他属性。</span><span class="sxs-lookup"><span data-stu-id="63834-119">If either **PR_REPLY_RECIPIENT_ENTRIES** or these properties are set, the other property must be set also.</span></span> <span data-ttu-id="63834-120">这些属性必须包含相同数量的收件人，并且它们必须包含它们的顺序。</span><span class="sxs-lookup"><span data-stu-id="63834-120">These properties must contain the same number of recipients, and they must contain them in the same order.</span></span> <span data-ttu-id="63834-121">遵守这些要求会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="63834-121">Failure to observe these requirements can cause unpredictable results.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="63834-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="63834-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="63834-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="63834-123">Protocol specifications</span></span>

<span data-ttu-id="63834-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="63834-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="63834-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="63834-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="63834-126">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="63834-126">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="63834-127">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="63834-127">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="63834-128">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="63834-128">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="63834-129">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="63834-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="63834-130">头文件</span><span class="sxs-lookup"><span data-stu-id="63834-130">Header files</span></span>

<span data-ttu-id="63834-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="63834-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="63834-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="63834-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="63834-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="63834-133">Mapitags.h</span></span>
  
> <span data-ttu-id="63834-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="63834-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="63834-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63834-135">See also</span></span>



[<span data-ttu-id="63834-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="63834-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="63834-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="63834-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="63834-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="63834-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="63834-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="63834-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

