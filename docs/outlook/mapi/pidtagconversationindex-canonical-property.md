---
title: PidTagConversationIndex 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversationIndex
api_type:
- HeaderDef
ms.assetid: c65cdda7-9515-4da9-be75-43ebf45a02df
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77fee834108a603c1cd10e8e47776cc34fd75a2b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584162"
---
# <a name="pidtagconversationindex-canonical-property"></a><span data-ttu-id="405ef-103">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="405ef-103">PidTagConversationIndex Canonical Property</span></span>

  
  
<span data-ttu-id="405ef-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="405ef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="405ef-105">包含一个二进制值，指示此消息在对话线程中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="405ef-105">Contains a binary value that indicates the relative position of this message within a conversation thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="405ef-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="405ef-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="405ef-107">PR_CONVERSATION_INDEX</span><span class="sxs-lookup"><span data-stu-id="405ef-107">PR_CONVERSATION_INDEX</span></span>  <br/> |
|<span data-ttu-id="405ef-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="405ef-108">Identifier:</span></span>  <br/> |<span data-ttu-id="405ef-109">0x0071</span><span class="sxs-lookup"><span data-stu-id="405ef-109">0x0071</span></span>  <br/> |
|<span data-ttu-id="405ef-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="405ef-110">Data type:</span></span>  <br/> |<span data-ttu-id="405ef-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="405ef-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="405ef-112">区域：</span><span class="sxs-lookup"><span data-stu-id="405ef-112">Area:</span></span>  <br/> |<span data-ttu-id="405ef-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="405ef-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="405ef-114">注解</span><span class="sxs-lookup"><span data-stu-id="405ef-114">Remarks</span></span>

<span data-ttu-id="405ef-115">会话线索表示一系列邮件和答复。</span><span class="sxs-lookup"><span data-stu-id="405ef-115">A conversation thread represents a series of messages and replies.</span></span> <span data-ttu-id="405ef-116">此属性通常使用连接的时间戳值来实现。</span><span class="sxs-lookup"><span data-stu-id="405ef-116">This property is usually implemented using concatenated time stamp values.</span></span> <span data-ttu-id="405ef-117">即使设置**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md))，其用途是可选的。</span><span class="sxs-lookup"><span data-stu-id="405ef-117">Its use is optional, even if **PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) is set.</span></span> 
  
<span data-ttu-id="405ef-118">MAPI 提供了用于创建或更新的对话索引的[ScCreateConversationIndex](sccreateconversationindex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="405ef-118">MAPI provides the [ScCreateConversationIndex](sccreateconversationindex.md) function to create or update a conversation index.</span></span> <span data-ttu-id="405ef-119">该函数将作为计数的字节数组的当前索引值，并返回具有在结尾处连接时间戳的索引值。</span><span class="sxs-lookup"><span data-stu-id="405ef-119">The function takes the current index value as a counted byte array and returns the index value with a time stamp concatenated onto the end.</span></span> <span data-ttu-id="405ef-120">表示对其他邮件的答复邮件应使用**ScCreateConversationIndex**更新此属性。</span><span class="sxs-lookup"><span data-stu-id="405ef-120">A message representing a reply to another message should use **ScCreateConversationIndex** to update this property.</span></span> 
  
<span data-ttu-id="405ef-121">消息存储提供程序具有**PR_CONVERSATION_INDEX**始终对传入或传出邮件设置的选项的保证。</span><span class="sxs-lookup"><span data-stu-id="405ef-121">A message store provider has the option of assuring that **PR_CONVERSATION_INDEX** is always set on incoming or outgoing messages.</span></span> <span data-ttu-id="405ef-122">它可以通过调用**ScCreateConversationIndex**，如果此属性设置的现有值或空如果不是执行此操作。</span><span class="sxs-lookup"><span data-stu-id="405ef-122">It can do this by calling **ScCreateConversationIndex**, either with the existing value if this property is set or with NULL if it is not.</span></span> <span data-ttu-id="405ef-123">调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)之前，应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="405ef-123">This action should be taken before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
  
<span data-ttu-id="405ef-124">可以在此属性以显示邮件的分层关系排序**PR_CONVERSATION_TOPIC**具有相同的值的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="405ef-124">All messages that have the same value for **PR_CONVERSATION_TOPIC** can be sorted on this property to reveal the hierarchical relationship of the messages.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="405ef-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="405ef-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="405ef-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="405ef-126">Protocol specifications</span></span>

<span data-ttu-id="405ef-127">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="405ef-127">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="405ef-128">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="405ef-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="405ef-129">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="405ef-129">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="405ef-130">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="405ef-130">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="405ef-131">头文件</span><span class="sxs-lookup"><span data-stu-id="405ef-131">Header files</span></span>

<span data-ttu-id="405ef-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="405ef-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="405ef-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="405ef-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="405ef-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="405ef-134">Mapitags.h</span></span>
  
> <span data-ttu-id="405ef-135">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="405ef-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="405ef-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="405ef-136">See also</span></span>



[<span data-ttu-id="405ef-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="405ef-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="405ef-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="405ef-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="405ef-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="405ef-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="405ef-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="405ef-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

