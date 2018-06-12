---
title: PidTagConversationTopic 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversationTopic
api_type:
- HeaderDef
ms.assetid: db852b99-ce04-49bf-a714-7549571502e2
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2e656679fcf76992ec0b648274bd5ffa673b4007
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777505"
---
# <a name="pidtagconversationtopic-canonical-property"></a><span data-ttu-id="9492c-103">PidTagConversationTopic 规范属性</span><span class="sxs-lookup"><span data-stu-id="9492c-103">PidTagConversationTopic Canonical Property</span></span>

  
  
<span data-ttu-id="9492c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9492c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9492c-105">包含会话线索中的第一个邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="9492c-105">Contains the topic of the first message in a conversation thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9492c-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="9492c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9492c-107">PR_CONVERSATION_TOPIC，PR_CONVERSATION_TOPIC_A，PR_CONVERSATION_TOPIC_W</span><span class="sxs-lookup"><span data-stu-id="9492c-107">PR_CONVERSATION_TOPIC, PR_CONVERSATION_TOPIC_A, PR_CONVERSATION_TOPIC_W</span></span>  <br/> |
|<span data-ttu-id="9492c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9492c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9492c-109">0x0070</span><span class="sxs-lookup"><span data-stu-id="9492c-109">0x0070</span></span>  <br/> |
|<span data-ttu-id="9492c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9492c-110">Data type:</span></span>  <br/> |<span data-ttu-id="9492c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9492c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="9492c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9492c-112">Area:</span></span>  <br/> |<span data-ttu-id="9492c-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="9492c-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9492c-114">备注</span><span class="sxs-lookup"><span data-stu-id="9492c-114">Remarks</span></span>

<span data-ttu-id="9492c-115">会话线索表示一系列邮件和答复。</span><span class="sxs-lookup"><span data-stu-id="9492c-115">A conversation thread represents a series of messages and replies.</span></span> <span data-ttu-id="9492c-116">设置这些属性是线程，通常为**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性中的第一条消息。</span><span class="sxs-lookup"><span data-stu-id="9492c-116">These properties are set for the first message in a thread, usually to the **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span> <span data-ttu-id="9492c-117">后续的消息的线程中应使用同一主题不做任何修改。</span><span class="sxs-lookup"><span data-stu-id="9492c-117">Subsequent messages in the thread should use the same topic without modification.</span></span> 
  
<span data-ttu-id="9492c-118">**PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) 属性指示后续的消息和回复的顺序关系。</span><span class="sxs-lookup"><span data-stu-id="9492c-118">The **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property indicates the order relationship between subsequent messages and replies.</span></span> <span data-ttu-id="9492c-119">即使设置这些属性，其用途是可选的。</span><span class="sxs-lookup"><span data-stu-id="9492c-119">Its use is optional, even if these properties are set.</span></span> 
  
<span data-ttu-id="9492c-120">消息存储提供程序具有这些属性始终对传入或传出邮件设置的选项的保证。</span><span class="sxs-lookup"><span data-stu-id="9492c-120">A message store provider has the option of assuring that these properties are always set on incoming or outgoing messages.</span></span> <span data-ttu-id="9492c-121">如果已设置这些属性应不会更改它们。</span><span class="sxs-lookup"><span data-stu-id="9492c-121">If these properties are already set they should not be altered.</span></span> <span data-ttu-id="9492c-122">如果没有，它们可以设置为**PR_NORMALIZED_SUBJECT**。</span><span class="sxs-lookup"><span data-stu-id="9492c-122">If not, they can be set to **PR_NORMALIZED_SUBJECT**.</span></span> <span data-ttu-id="9492c-123">调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前，应执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="9492c-123">Any action should be taken before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9492c-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="9492c-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9492c-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="9492c-125">Protocol specifications</span></span>

<span data-ttu-id="9492c-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9492c-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9492c-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="9492c-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9492c-128">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9492c-128">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9492c-129">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="9492c-129">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9492c-130">头文件</span><span class="sxs-lookup"><span data-stu-id="9492c-130">Header files</span></span>

<span data-ttu-id="9492c-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9492c-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="9492c-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9492c-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="9492c-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9492c-133">Mapitags.h</span></span>
  
> <span data-ttu-id="9492c-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9492c-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9492c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9492c-135">See also</span></span>



[<span data-ttu-id="9492c-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9492c-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9492c-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9492c-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9492c-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9492c-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9492c-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9492c-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

