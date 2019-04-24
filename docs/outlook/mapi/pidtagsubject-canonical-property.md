---
title: PidTagSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubject
api_type:
- COM
ms.assetid: aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cf9e9f8c10f8d27bd174b8b6f2bf19812dc269d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339254"
---
# <a name="pidtagsubject-canonical-property"></a><span data-ttu-id="d8354-103">PidTagSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8354-103">PidTagSubject Canonical Property</span></span>

  
  
<span data-ttu-id="d8354-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d8354-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d8354-105">包含邮件的完整主题。</span><span class="sxs-lookup"><span data-stu-id="d8354-105">Contains the full subject of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d8354-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d8354-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8354-107">PR_SUBJECT、PR_SUBJECT_A、PR_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="d8354-107">PR_SUBJECT, PR_SUBJECT_A, PR_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="d8354-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d8354-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8354-109">0x0037</span><span class="sxs-lookup"><span data-stu-id="d8354-109">0x0037</span></span>  <br/> |
|<span data-ttu-id="d8354-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d8354-110">Data type:</span></span>  <br/> |<span data-ttu-id="d8354-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d8354-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d8354-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8354-112">Area:</span></span>  <br/> |<span data-ttu-id="d8354-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="d8354-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8354-114">注解</span><span class="sxs-lookup"><span data-stu-id="d8354-114">Remarks</span></span>

<span data-ttu-id="d8354-115">对于所有邮件对象, 建议使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="d8354-115">These properties are recommended on all message objects.</span></span> 
  
<span data-ttu-id="d8354-116">这些属性始终是完整的主题文本, 即前缀和规范化主题的串联。</span><span class="sxs-lookup"><span data-stu-id="d8354-116">These properties are always the full subject text, that is, the concatenation of the prefix and the normalized subject.</span></span> <span data-ttu-id="d8354-117">如果没有前缀, 则正常化的主题应与主题相同。</span><span class="sxs-lookup"><span data-stu-id="d8354-117">If there is no prefix, the normalized subject should be the same as the subject.</span></span> <span data-ttu-id="d8354-118">邮件存储或传输提供程序使用这些 properties 和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性来计算正常化的主题, 使用**PR_NORMALIZED_SUBJECT** [中描述的规则。PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="d8354-118">A message store or transport provider uses both these properties and **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) properties to compute the normalized subject using the rule described under **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)).</span></span>
  
<span data-ttu-id="d8354-119">subject 属性通常是少于256个字符的小字符串, 而邮件存储提供程序并不是支持其上的**IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="d8354-119">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the **IStream** interface on them.</span></span> <span data-ttu-id="d8354-120">客户端应始终先尝试通过**IMAPIProp**接口访问, 并且只有在返回**MAPI_E_NOT_ENOUGH_MEMORY**时才会转到**IStream** 。</span><span class="sxs-lookup"><span data-stu-id="d8354-120">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
<span data-ttu-id="d8354-121">对于报表, 此属性包含原始邮件的主题, 其前面有一个指示邮件发生了什么情况的字符串。</span><span class="sxs-lookup"><span data-stu-id="d8354-121">For a report, this property contains the original message's subject preceded by a string indicating what has happened to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d8354-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8354-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d8354-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="d8354-123">Protocol specifications</span></span>

<span data-ttu-id="d8354-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8354-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8354-125">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d8354-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d8354-126">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8354-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8354-127">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d8354-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d8354-128">头文件</span><span class="sxs-lookup"><span data-stu-id="d8354-128">Header files</span></span>

<span data-ttu-id="d8354-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d8354-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8354-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8354-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8354-131">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d8354-131">Mapitags.h</span></span>
  
> <span data-ttu-id="d8354-132">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8354-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8354-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8354-133">See also</span></span>



[<span data-ttu-id="d8354-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8354-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8354-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8354-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8354-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d8354-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8354-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8354-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

