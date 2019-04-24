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
ms.openlocfilehash: c6fa0d8f1323e8562a78080f50dbf448b8019ec2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334718"
---
# <a name="pidtagconversationindex-canonical-property"></a><span data-ttu-id="a57ce-103">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="a57ce-103">PidTagConversationIndex Canonical Property</span></span>

  
  
<span data-ttu-id="a57ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a57ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a57ce-105">包含一个二进制值, 该值指示此邮件在会话线程中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="a57ce-105">Contains a binary value that indicates the relative position of this message within a conversation thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a57ce-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a57ce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a57ce-107">PR_CONVERSATION_INDEX</span><span class="sxs-lookup"><span data-stu-id="a57ce-107">PR_CONVERSATION_INDEX</span></span>  <br/> |
|<span data-ttu-id="a57ce-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a57ce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a57ce-109">0x0071</span><span class="sxs-lookup"><span data-stu-id="a57ce-109">0x0071</span></span>  <br/> |
|<span data-ttu-id="a57ce-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a57ce-110">Data type:</span></span>  <br/> |<span data-ttu-id="a57ce-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a57ce-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a57ce-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a57ce-112">Area:</span></span>  <br/> |<span data-ttu-id="a57ce-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="a57ce-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a57ce-114">注解</span><span class="sxs-lookup"><span data-stu-id="a57ce-114">Remarks</span></span>

<span data-ttu-id="a57ce-115">会话线程代表一系列邮件和答复。</span><span class="sxs-lookup"><span data-stu-id="a57ce-115">A conversation thread represents a series of messages and replies.</span></span> <span data-ttu-id="a57ce-116">此属性通常是使用串联时间戳值实现的。</span><span class="sxs-lookup"><span data-stu-id="a57ce-116">This property is usually implemented using concatenated time stamp values.</span></span> <span data-ttu-id="a57ce-117">它的使用是可选的, 即使设置了**PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) 也是如此。</span><span class="sxs-lookup"><span data-stu-id="a57ce-117">Its use is optional, even if **PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) is set.</span></span> 
  
<span data-ttu-id="a57ce-118">MAPI 提供了用于创建或更新会话索引的[ScCreateConversationIndex](sccreateconversationindex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a57ce-118">MAPI provides the [ScCreateConversationIndex](sccreateconversationindex.md) function to create or update a conversation index.</span></span> <span data-ttu-id="a57ce-119">函数将当前索引值作为计数字节数组, 并返回一个与末尾串联的时间戳的索引值。</span><span class="sxs-lookup"><span data-stu-id="a57ce-119">The function takes the current index value as a counted byte array and returns the index value with a time stamp concatenated onto the end.</span></span> <span data-ttu-id="a57ce-120">表示对另一封邮件的答复的邮件应使用**ScCreateConversationIndex**更新该属性。</span><span class="sxs-lookup"><span data-stu-id="a57ce-120">A message representing a reply to another message should use **ScCreateConversationIndex** to update this property.</span></span> 
  
<span data-ttu-id="a57ce-121">邮件存储提供程序可以选择确保始终在传入或传出邮件上设置**PR_CONVERSATION_INDEX** 。</span><span class="sxs-lookup"><span data-stu-id="a57ce-121">A message store provider has the option of assuring that **PR_CONVERSATION_INDEX** is always set on incoming or outgoing messages.</span></span> <span data-ttu-id="a57ce-122">它可以通过调用**ScCreateConversationIndex**(如果设置了此属性, 则使用现有值) 或使用 NULL (如果未设置) 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a57ce-122">It can do this by calling **ScCreateConversationIndex**, either with the existing value if this property is set or with NULL if it is not.</span></span> <span data-ttu-id="a57ce-123">应在调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a57ce-123">This action should be taken before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
  
<span data-ttu-id="a57ce-124">对**PR_CONVERSATION_TOPIC**具有相同值的所有邮件都可以在此属性上进行排序, 以显示邮件的层次结构关系。</span><span class="sxs-lookup"><span data-stu-id="a57ce-124">All messages that have the same value for **PR_CONVERSATION_TOPIC** can be sorted on this property to reveal the hierarchical relationship of the messages.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a57ce-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="a57ce-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a57ce-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="a57ce-126">Protocol specifications</span></span>

<span data-ttu-id="a57ce-127">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a57ce-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a57ce-128">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a57ce-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a57ce-129">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a57ce-129">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a57ce-130">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a57ce-130">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a57ce-131">头文件</span><span class="sxs-lookup"><span data-stu-id="a57ce-131">Header files</span></span>

<span data-ttu-id="a57ce-132">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a57ce-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="a57ce-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a57ce-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="a57ce-134">Mapitags</span><span class="sxs-lookup"><span data-stu-id="a57ce-134">Mapitags.h</span></span>
  
> <span data-ttu-id="a57ce-135">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a57ce-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a57ce-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a57ce-136">See also</span></span>



[<span data-ttu-id="a57ce-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a57ce-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a57ce-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a57ce-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a57ce-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a57ce-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a57ce-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a57ce-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

