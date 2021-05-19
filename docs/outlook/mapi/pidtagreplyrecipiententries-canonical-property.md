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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 000132f052abb666ae844ec7d21b59c85ab43613
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355053"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a><span data-ttu-id="d3855-103">PidTagReplyRecipientEntries 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3855-103">PidTagReplyRecipientEntries Canonical Property</span></span>

  
  
<span data-ttu-id="d3855-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d3855-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d3855-105">包含用于获取回复的收件人的条目标识符大小数组。</span><span class="sxs-lookup"><span data-stu-id="d3855-105">Contains a sized array of entry identifiers for recipients that are to get a reply.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d3855-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d3855-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d3855-107">PR_REPLY_RECIPIENT_ENTRIES</span><span class="sxs-lookup"><span data-stu-id="d3855-107">PR_REPLY_RECIPIENT_ENTRIES</span></span>  <br/> |
|<span data-ttu-id="d3855-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d3855-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d3855-109">0x004F</span><span class="sxs-lookup"><span data-stu-id="d3855-109">0x004F</span></span>  <br/> |
|<span data-ttu-id="d3855-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d3855-110">Data type:</span></span>  <br/> |<span data-ttu-id="d3855-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d3855-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d3855-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d3855-112">Area:</span></span>  <br/> |<span data-ttu-id="d3855-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="d3855-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3855-114">备注</span><span class="sxs-lookup"><span data-stu-id="d3855-114">Remarks</span></span>

<span data-ttu-id="d3855-115">此属性包含 [FLATENTRYLIST](flatentrylist.md) 结构，而不是多值属性。</span><span class="sxs-lookup"><span data-stu-id="d3855-115">This property contains a [FLATENTRYLIST](flatentrylist.md) structure and is not a multivalued property.</span></span> 
  
<span data-ttu-id="d3855-116">当此属性不存在时，答复将仅发送给[PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md) PR_SENDER_ENTRYID (标识) 用户。 </span><span class="sxs-lookup"><span data-stu-id="d3855-116">When this property is not present, a reply is sent only to the user identified by the **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="d3855-117">定义此PR_REPLY_RECIPIENT_NAMES ( [PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) 属性时，答复将发送给这两个属性标识的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="d3855-117">When this and the **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md)) properties are defined, the reply is sent to all of the recipients identified by these two properties.</span></span> <span data-ttu-id="d3855-118">传输提供程序使用这些属性覆盖常见的回复逻辑。</span><span class="sxs-lookup"><span data-stu-id="d3855-118">A transport provider uses these properties to override the usual reply logic.</span></span>
  
<span data-ttu-id="d3855-119">如果设置了此属性或 **PR_REPLY_RECIPIENT_NAMES** 属性，则还必须设置另一个属性。</span><span class="sxs-lookup"><span data-stu-id="d3855-119">If either this property or the **PR_REPLY_RECIPIENT_NAMES** property is set, the other property must be set also.</span></span> <span data-ttu-id="d3855-120">这些属性必须包含相同数量的收件人，并且必须按相同的顺序包含它们。</span><span class="sxs-lookup"><span data-stu-id="d3855-120">These properties must contain the same number of recipients, and they must contain them in the same order.</span></span> <span data-ttu-id="d3855-121">如果未能遵守这些要求，可能会导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="d3855-121">Failure to observe these requirements can cause unpredictable results.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d3855-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="d3855-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d3855-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="d3855-123">Protocol specifications</span></span>

<span data-ttu-id="d3855-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3855-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d3855-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d3855-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d3855-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3855-126">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d3855-127">指定允许对电子邮件执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d3855-127">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="d3855-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d3855-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d3855-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="d3855-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d3855-130">头文件</span><span class="sxs-lookup"><span data-stu-id="d3855-130">Header files</span></span>

<span data-ttu-id="d3855-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d3855-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="d3855-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d3855-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="d3855-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d3855-133">Mapitags.h</span></span>
  
> <span data-ttu-id="d3855-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d3855-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d3855-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3855-135">See also</span></span>



[<span data-ttu-id="d3855-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d3855-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d3855-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d3855-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d3855-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d3855-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d3855-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d3855-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

