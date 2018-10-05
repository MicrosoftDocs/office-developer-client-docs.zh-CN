---
title: PidTagSubjectPrefix 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubjectPrefix
api_type:
- COM
ms.assetid: 07fcb881-d873-45bf-b048-30f41d0d8d85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8257c3c3583072d16e96e6ea9bba4632fc78f9ef
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385646"
---
# <a name="pidtagsubjectprefix-canonical-property"></a><span data-ttu-id="8b45a-103">PidTagSubjectPrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b45a-103">PidTagSubjectPrefix Canonical Property</span></span>

  
  
<span data-ttu-id="8b45a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b45a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b45a-105">包含通常如指示上一条消息，某些操作的主题前缀"FW:"用于呼叫转移。</span><span class="sxs-lookup"><span data-stu-id="8b45a-105">Contains a subject prefix that typically indicates some action on a message, such as "FW: " for forwarding.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8b45a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8b45a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8b45a-107">PR_SUBJECT_PREFIX，PR_SUBJECT_PREFIX_A，PR_SUBJECT_PREFIX_W</span><span class="sxs-lookup"><span data-stu-id="8b45a-107">PR_SUBJECT_PREFIX, PR_SUBJECT_PREFIX_A, PR_SUBJECT_PREFIX_W</span></span>  <br/> |
|<span data-ttu-id="8b45a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8b45a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8b45a-109">0x003D</span><span class="sxs-lookup"><span data-stu-id="8b45a-109">0x003D</span></span>  <br/> |
|<span data-ttu-id="8b45a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8b45a-110">Data type:</span></span>  <br/> |<span data-ttu-id="8b45a-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8b45a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8b45a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8b45a-112">Area:</span></span>  <br/> |<span data-ttu-id="8b45a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="8b45a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b45a-114">说明</span><span class="sxs-lookup"><span data-stu-id="8b45a-114">Remarks</span></span>

<span data-ttu-id="8b45a-115">建议对所有的消息对象都使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="8b45a-115">These properties are recommended on all message objects.</span></span> 
  
<span data-ttu-id="8b45a-116">主题前缀包括一个或多个字母数字字符后, 跟一个冒号和一个空格 （这是前缀的一部分）。</span><span class="sxs-lookup"><span data-stu-id="8b45a-116">The subject prefix consists of one or more alphanumeric characters, followed by a colon and a space (which are part of the prefix).</span></span> <span data-ttu-id="8b45a-117">它必须包含冒号前的任何非字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="8b45a-117">It must not contain any nonalphanumeric characters before the colon.</span></span> <span data-ttu-id="8b45a-118">通过为空字符串或未设置此属性，则可以表示前缀不存在。</span><span class="sxs-lookup"><span data-stu-id="8b45a-118">Absence of a prefix can be represented by an empty string or by this property not being set.</span></span> 
  
<span data-ttu-id="8b45a-119">如果显式设置这些属性，字符串可以是任意长度和使用任何字母数字字符，但它必须匹配**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性开头的子字符串。</span><span class="sxs-lookup"><span data-stu-id="8b45a-119">If these properties are set explicitly, the string can be of any length and use any alphanumeric characters, but it must match a substring at the beginning of the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span> <span data-ttu-id="8b45a-120">如果这些属性未设置发件人，并且必须计算，其内容的更多的限制。</span><span class="sxs-lookup"><span data-stu-id="8b45a-120">If these properties are not set by the sender and must be computed, their contents are more restricted.</span></span> <span data-ttu-id="8b45a-121">计算前缀的规则是**PR_SUBJECT**必须开始使用一个、 两个或三个字母 (字母仅) 后跟一个冒号和一个空格。</span><span class="sxs-lookup"><span data-stu-id="8b45a-121">The rule for computing the prefix is that **PR_SUBJECT** must begin with one, two, or three letters (alphabetic only) followed by a colon and a space.</span></span> <span data-ttu-id="8b45a-122">如果**PR_SUBJECT**开头找到此类子字符串，则随后将成为这些属性的字符串 （及其还保持**PR_SUBJECT**开头）。</span><span class="sxs-lookup"><span data-stu-id="8b45a-122">If such a substring is found at the beginning of **PR_SUBJECT**, it then becomes the string for these properties (and also stays at the beginning of **PR_SUBJECT**).</span></span> <span data-ttu-id="8b45a-123">否则，这些属性保留未设置。</span><span class="sxs-lookup"><span data-stu-id="8b45a-123">Otherwise, these properties remain unset.</span></span> 
  
<span data-ttu-id="8b45a-124">这些属性和**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 应计算作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)实现的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b45a-124">These properties and **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) should be computed as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) implementation.</span></span> <span data-ttu-id="8b45a-125">客户端应不提示[IMAPIProp::GetProps](imapiprop-getprops.md)它们的值之前已经提交由**IMAPIProp::SaveChanges**呼叫。</span><span class="sxs-lookup"><span data-stu-id="8b45a-125">A client should not prompt [IMAPIProp::GetProps](imapiprop-getprops.md) for their values until they have been committed by an **IMAPIProp::SaveChanges** call.</span></span> 
  
<span data-ttu-id="8b45a-126">Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些 OLE **IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="8b45a-126">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the OLE **IStream** interface on them.</span></span> <span data-ttu-id="8b45a-127">客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。</span><span class="sxs-lookup"><span data-stu-id="8b45a-127">A client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8b45a-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="8b45a-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8b45a-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="8b45a-129">Protocol specifications</span></span>

<span data-ttu-id="8b45a-130">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b45a-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8b45a-131">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8b45a-131">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8b45a-132">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b45a-132">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8b45a-133">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="8b45a-133">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="8b45a-134">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8b45a-134">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8b45a-135">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="8b45a-135">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8b45a-136">头文件</span><span class="sxs-lookup"><span data-stu-id="8b45a-136">Header files</span></span>

<span data-ttu-id="8b45a-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8b45a-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="8b45a-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8b45a-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="8b45a-139">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8b45a-139">Mapitags.h</span></span>
  
> <span data-ttu-id="8b45a-140">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8b45a-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b45a-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b45a-141">See also</span></span>



[<span data-ttu-id="8b45a-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8b45a-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8b45a-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b45a-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8b45a-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8b45a-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8b45a-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b45a-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

