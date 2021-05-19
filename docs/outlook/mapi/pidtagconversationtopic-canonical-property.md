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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfd437fac3a784212807c495f6e8f1adbe759cb0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334683"
---
# <a name="pidtagconversationtopic-canonical-property"></a><span data-ttu-id="0358d-103">PidTagConversationTopic 规范属性</span><span class="sxs-lookup"><span data-stu-id="0358d-103">PidTagConversationTopic Canonical Property</span></span>

  
  
<span data-ttu-id="0358d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0358d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0358d-105">包含对话线程中第一封邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="0358d-105">Contains the topic of the first message in a conversation thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0358d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0358d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0358d-107">PR_CONVERSATION_TOPIC、PR_CONVERSATION_TOPIC_A、PR_CONVERSATION_TOPIC_W</span><span class="sxs-lookup"><span data-stu-id="0358d-107">PR_CONVERSATION_TOPIC, PR_CONVERSATION_TOPIC_A, PR_CONVERSATION_TOPIC_W</span></span>  <br/> |
|<span data-ttu-id="0358d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0358d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0358d-109">0x0070</span><span class="sxs-lookup"><span data-stu-id="0358d-109">0x0070</span></span>  <br/> |
|<span data-ttu-id="0358d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0358d-110">Data type:</span></span>  <br/> |<span data-ttu-id="0358d-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0358d-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0358d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0358d-112">Area:</span></span>  <br/> |<span data-ttu-id="0358d-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="0358d-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0358d-114">备注</span><span class="sxs-lookup"><span data-stu-id="0358d-114">Remarks</span></span>

<span data-ttu-id="0358d-115">对话线程表示一系列消息和回复。</span><span class="sxs-lookup"><span data-stu-id="0358d-115">A conversation thread represents a series of messages and replies.</span></span> <span data-ttu-id="0358d-116">这些属性设置为线程中第一条消息，通常设置为[PidTagNormalizedSubject PR_NORMALIZED_SUBJECT (PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="0358d-116">These properties are set for the first message in a thread, usually to the **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) property.</span></span> <span data-ttu-id="0358d-117">线程中的后续消息应使用相同的主题，无需进行修改。</span><span class="sxs-lookup"><span data-stu-id="0358d-117">Subsequent messages in the thread should use the same topic without modification.</span></span> 
  
<span data-ttu-id="0358d-118">The **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property indicates the order relationship between subsequent messages and replies.</span><span class="sxs-lookup"><span data-stu-id="0358d-118">The **PR_CONVERSATION_INDEX** ([PidTagConversationIndex](pidtagconversationindex-canonical-property.md)) property indicates the order relationship between subsequent messages and replies.</span></span> <span data-ttu-id="0358d-119">它的使用是可选的，即使这些属性已设置。</span><span class="sxs-lookup"><span data-stu-id="0358d-119">Its use is optional, even if these properties are set.</span></span> 
  
<span data-ttu-id="0358d-120">邮件存储提供程序可以选择确保始终对传入或传出邮件设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="0358d-120">A message store provider has the option of assuring that these properties are always set on incoming or outgoing messages.</span></span> <span data-ttu-id="0358d-121">如果这些属性已经设置，则不应更改它们。</span><span class="sxs-lookup"><span data-stu-id="0358d-121">If these properties are already set they should not be altered.</span></span> <span data-ttu-id="0358d-122">如果没有，可以设置为 **"PR_NORMALIZED_SUBJECT"。**</span><span class="sxs-lookup"><span data-stu-id="0358d-122">If not, they can be set to **PR_NORMALIZED_SUBJECT**.</span></span> <span data-ttu-id="0358d-123">在调用 [IMAPIProp：：SaveChanges 之前，应执行任何](imapiprop-savechanges.md) 操作。</span><span class="sxs-lookup"><span data-stu-id="0358d-123">Any action should be taken before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0358d-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="0358d-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0358d-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="0358d-125">Protocol specifications</span></span>

<span data-ttu-id="0358d-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0358d-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0358d-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="0358d-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0358d-128">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0358d-128">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0358d-129">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0358d-129">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0358d-130">头文件</span><span class="sxs-lookup"><span data-stu-id="0358d-130">Header files</span></span>

<span data-ttu-id="0358d-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0358d-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="0358d-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0358d-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="0358d-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0358d-133">Mapitags.h</span></span>
  
> <span data-ttu-id="0358d-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0358d-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0358d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0358d-135">See also</span></span>



[<span data-ttu-id="0358d-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0358d-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0358d-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0358d-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0358d-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0358d-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0358d-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0358d-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

