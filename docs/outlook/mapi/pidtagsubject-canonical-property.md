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
ms.openlocfilehash: 63bb5534756f44aebd9e6ca21c336534b279909d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778480"
---
# <a name="pidtagsubject-canonical-property"></a><span data-ttu-id="6a672-103">PidTagSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a672-103">PidTagSubject Canonical Property</span></span>

  
  
<span data-ttu-id="6a672-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6a672-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6a672-105">包含邮件的完整主题。</span><span class="sxs-lookup"><span data-stu-id="6a672-105">Contains the full subject of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a672-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a672-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a672-107">PR_SUBJECT，PR_SUBJECT_A，PR_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="6a672-107">PR_SUBJECT, PR_SUBJECT_A, PR_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="6a672-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6a672-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a672-109">0x0037</span><span class="sxs-lookup"><span data-stu-id="6a672-109">0x0037</span></span>  <br/> |
|<span data-ttu-id="6a672-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a672-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a672-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6a672-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6a672-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a672-112">Area:</span></span>  <br/> |<span data-ttu-id="6a672-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="6a672-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a672-114">说明</span><span class="sxs-lookup"><span data-stu-id="6a672-114">Remarks</span></span>

<span data-ttu-id="6a672-115">建议对所有的消息对象都使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="6a672-115">These properties are recommended on all message objects.</span></span> 
  
<span data-ttu-id="6a672-116">这些属性将始终的完整主题文本，即前缀和规范化的主题串联。</span><span class="sxs-lookup"><span data-stu-id="6a672-116">These properties are always the full subject text, that is, the concatenation of the prefix and the normalized subject.</span></span> <span data-ttu-id="6a672-117">如果没有前缀，规范化的主题应与相同主题。</span><span class="sxs-lookup"><span data-stu-id="6a672-117">If there is no prefix, the normalized subject should be the same as the subject.</span></span> <span data-ttu-id="6a672-118">消息存储或传输提供程序使用这些属性和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性来计算使用规则规范化的主题所述在**PR_NORMALIZED_SUBJECT** ([下PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6a672-118">A message store or transport provider uses both these properties and **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) properties to compute the normalized subject using the rule described under **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)).</span></span>
  
<span data-ttu-id="6a672-119">Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些**IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="6a672-119">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the **IStream** interface on them.</span></span> <span data-ttu-id="6a672-120">客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。</span><span class="sxs-lookup"><span data-stu-id="6a672-120">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
<span data-ttu-id="6a672-121">对于报表，此属性包含一个 string，指示邮件发生前面的原始消息的主题。</span><span class="sxs-lookup"><span data-stu-id="6a672-121">For a report, this property contains the original message's subject preceded by a string indicating what has happened to the message.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6a672-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a672-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6a672-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="6a672-123">Protocol specifications</span></span>

<span data-ttu-id="6a672-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a672-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a672-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6a672-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6a672-126">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a672-126">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a672-127">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="6a672-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6a672-128">头文件</span><span class="sxs-lookup"><span data-stu-id="6a672-128">Header files</span></span>

<span data-ttu-id="6a672-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6a672-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a672-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a672-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a672-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6a672-131">Mapitags.h</span></span>
  
> <span data-ttu-id="6a672-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a672-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a672-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a672-133">See also</span></span>



[<span data-ttu-id="6a672-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a672-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a672-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a672-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a672-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a672-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a672-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a672-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

