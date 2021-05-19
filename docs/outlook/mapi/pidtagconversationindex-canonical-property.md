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
# <a name="pidtagconversationindex-canonical-property"></a><span data-ttu-id="6ed5a-103">PidTagConversationIndex 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ed5a-103">PidTagConversationIndex Canonical Property</span></span>

  
  
<span data-ttu-id="6ed5a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6ed5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6ed5a-105">包含指示此消息在对话线程中的相对位置的二进制值。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-105">Contains a binary value that indicates the relative position of this message within a conversation thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6ed5a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6ed5a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6ed5a-107">PR_CONVERSATION_INDEX</span><span class="sxs-lookup"><span data-stu-id="6ed5a-107">PR_CONVERSATION_INDEX</span></span>  <br/> |
|<span data-ttu-id="6ed5a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6ed5a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6ed5a-109">0x0071</span><span class="sxs-lookup"><span data-stu-id="6ed5a-109">0x0071</span></span>  <br/> |
|<span data-ttu-id="6ed5a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6ed5a-110">Data type:</span></span>  <br/> |<span data-ttu-id="6ed5a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6ed5a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6ed5a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6ed5a-112">Area:</span></span>  <br/> |<span data-ttu-id="6ed5a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="6ed5a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6ed5a-114">备注</span><span class="sxs-lookup"><span data-stu-id="6ed5a-114">Remarks</span></span>

<span data-ttu-id="6ed5a-115">对话线程表示一系列消息和回复。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-115">A conversation thread represents a series of messages and replies.</span></span> <span data-ttu-id="6ed5a-116">通常使用连接时间戳值实现此属性。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-116">This property is usually implemented using concatenated time stamp values.</span></span> <span data-ttu-id="6ed5a-117">即使设置了[PidTagConversationTopic PR_CONVERSATION_TOPIC (PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) 也是可选的。 </span><span class="sxs-lookup"><span data-stu-id="6ed5a-117">Its use is optional, even if **PR_CONVERSATION_TOPIC** ([PidTagConversationTopic](pidtagconversationtopic-canonical-property.md)) is set.</span></span> 
  
<span data-ttu-id="6ed5a-118">MAPI 提供 [ScCreateConversationIndex](sccreateconversationindex.md) 函数来创建或更新对话索引。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-118">MAPI provides the [ScCreateConversationIndex](sccreateconversationindex.md) function to create or update a conversation index.</span></span> <span data-ttu-id="6ed5a-119">该函数将当前索引值作为计数型字节数组，并返回最后连接有时间戳的索引值。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-119">The function takes the current index value as a counted byte array and returns the index value with a time stamp concatenated onto the end.</span></span> <span data-ttu-id="6ed5a-120">表示对另一封邮件的答复的邮件应该使用 **ScCreateConversationIndex** 更新此属性。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-120">A message representing a reply to another message should use **ScCreateConversationIndex** to update this property.</span></span> 
  
<span data-ttu-id="6ed5a-121">邮件存储提供程序可以选择确保始终PR_CONVERSATION_INDEX传入或传出邮件上设置邮件。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-121">A message store provider has the option of assuring that **PR_CONVERSATION_INDEX** is always set on incoming or outgoing messages.</span></span> <span data-ttu-id="6ed5a-122">它可以通过调用 **ScCreateConversationIndex** 来实现此操作，如果此属性已设置，则使用现有值;如果未设置，则使用 NULL。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-122">It can do this by calling **ScCreateConversationIndex**, either with the existing value if this property is set or with NULL if it is not.</span></span> <span data-ttu-id="6ed5a-123">应在调用 [IMAPIProp：：SaveChanges 之前](imapiprop-savechanges.md) 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-123">This action should be taken before [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called.</span></span> 
  
<span data-ttu-id="6ed5a-124">可以基于此属性对PR_CONVERSATION_TOPIC相同值的所有邮件进行排序，以显示邮件的层次结构关系。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-124">All messages that have the same value for **PR_CONVERSATION_TOPIC** can be sorted on this property to reveal the hierarchical relationship of the messages.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6ed5a-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="6ed5a-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6ed5a-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="6ed5a-126">Protocol specifications</span></span>

<span data-ttu-id="6ed5a-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ed5a-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ed5a-128">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6ed5a-129">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ed5a-129">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ed5a-130">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-130">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6ed5a-131">头文件</span><span class="sxs-lookup"><span data-stu-id="6ed5a-131">Header files</span></span>

<span data-ttu-id="6ed5a-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6ed5a-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="6ed5a-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="6ed5a-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6ed5a-134">Mapitags.h</span></span>
  
> <span data-ttu-id="6ed5a-135">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6ed5a-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6ed5a-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ed5a-136">See also</span></span>



[<span data-ttu-id="6ed5a-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6ed5a-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6ed5a-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ed5a-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6ed5a-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6ed5a-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6ed5a-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6ed5a-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

