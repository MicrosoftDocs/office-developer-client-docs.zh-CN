---
title: PidTagReplyRecipientEntries 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientEntries
api_type:
- COM
ms.assetid: a903fd22-a3f2-464f-99b0-c087e211b124
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1ab8828dd2fc28a2fba1620fc251ba0a87c3e2bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778199"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a><span data-ttu-id="d1920-103">PidTagReplyRecipientEntries 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1920-103">PidTagReplyRecipientEntries Canonical Property</span></span>

  
  
<span data-ttu-id="d1920-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d1920-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d1920-105">包含要获取回复的收件人的项标识符的大小的数组。</span><span class="sxs-lookup"><span data-stu-id="d1920-105">Contains a sized array of entry identifiers for recipients that are to get a reply.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1920-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="d1920-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1920-107">PR_REPLY_RECIPIENT_ENTRIES</span><span class="sxs-lookup"><span data-stu-id="d1920-107">PR_REPLY_RECIPIENT_ENTRIES</span></span>  <br/> |
|<span data-ttu-id="d1920-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d1920-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d1920-109">0x004F</span><span class="sxs-lookup"><span data-stu-id="d1920-109">0x004F</span></span>  <br/> |
|<span data-ttu-id="d1920-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1920-110">Data type:</span></span>  <br/> |<span data-ttu-id="d1920-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d1920-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d1920-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d1920-112">Area:</span></span>  <br/> |<span data-ttu-id="d1920-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="d1920-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1920-114">备注</span><span class="sxs-lookup"><span data-stu-id="d1920-114">Remarks</span></span>

<span data-ttu-id="d1920-115">此属性包含一个[FLATENTRYLIST](flatentrylist.md)结构，并不是多值的属性。</span><span class="sxs-lookup"><span data-stu-id="d1920-115">This property contains a [FLATENTRYLIST](flatentrylist.md) structure and is not a multivalued property.</span></span> 
  
<span data-ttu-id="d1920-116">当此属性不存在时，仅对**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 属性标识的用户发送答复。</span><span class="sxs-lookup"><span data-stu-id="d1920-116">When this property is not present, a reply is sent only to the user identified by the **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="d1920-117">定义了这和**PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 属性，向所有由这两个属性标识的收件人发送答复。</span><span class="sxs-lookup"><span data-stu-id="d1920-117">When this and the **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) properties are defined, the reply is sent to all of the recipients identified by these two properties.</span></span> <span data-ttu-id="d1920-118">传输提供程序使用这些属性重写通常的应答逻辑。</span><span class="sxs-lookup"><span data-stu-id="d1920-118">A transport provider uses these properties to override the usual reply logic.</span></span>
  
<span data-ttu-id="d1920-119">如果设置此属性或**PR_REPLY_RECIPIENT_NAMES**属性，还必须设置其他属性。</span><span class="sxs-lookup"><span data-stu-id="d1920-119">If either this property or the **PR_REPLY_RECIPIENT_NAMES** property is set, the other property must be set also.</span></span> <span data-ttu-id="d1920-120">这些属性必须包含相同数量的收件人，并且它们必须包含它们的顺序。</span><span class="sxs-lookup"><span data-stu-id="d1920-120">These properties must contain the same number of recipients, and they must contain them in the same order.</span></span> <span data-ttu-id="d1920-121">遵守这些要求会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="d1920-121">Failure to observe these requirements can cause unpredictable results.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d1920-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1920-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d1920-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="d1920-123">Protocol specifications</span></span>

<span data-ttu-id="d1920-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1920-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1920-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d1920-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d1920-126">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1920-126">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1920-127">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="d1920-127">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="d1920-128">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1920-128">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1920-129">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="d1920-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d1920-130">头文件</span><span class="sxs-lookup"><span data-stu-id="d1920-130">Header files</span></span>

<span data-ttu-id="d1920-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d1920-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1920-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1920-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="d1920-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d1920-133">Mapitags.h</span></span>
  
> <span data-ttu-id="d1920-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d1920-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1920-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1920-135">See also</span></span>



[<span data-ttu-id="d1920-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1920-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1920-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1920-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1920-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1920-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1920-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1920-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

