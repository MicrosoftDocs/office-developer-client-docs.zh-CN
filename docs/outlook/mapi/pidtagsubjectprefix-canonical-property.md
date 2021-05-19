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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339226"
---
# <a name="pidtagsubjectprefix-canonical-property"></a><span data-ttu-id="6e5ef-103">PidTagSubjectPrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="6e5ef-103">PidTagSubjectPrefix Canonical Property</span></span>

  
  
<span data-ttu-id="6e5ef-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e5ef-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e5ef-105">包含通常指示对邮件执行某些操作的主题前缀，例如"FW："用于转发。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-105">Contains a subject prefix that typically indicates some action on a message, such as "FW: " for forwarding.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6e5ef-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6e5ef-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6e5ef-107">PR_SUBJECT_PREFIX、PR_SUBJECT_PREFIX_A、PR_SUBJECT_PREFIX_W</span><span class="sxs-lookup"><span data-stu-id="6e5ef-107">PR_SUBJECT_PREFIX, PR_SUBJECT_PREFIX_A, PR_SUBJECT_PREFIX_W</span></span>  <br/> |
|<span data-ttu-id="6e5ef-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6e5ef-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6e5ef-109">0x003D</span><span class="sxs-lookup"><span data-stu-id="6e5ef-109">0x003D</span></span>  <br/> |
|<span data-ttu-id="6e5ef-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6e5ef-110">Data type:</span></span>  <br/> |<span data-ttu-id="6e5ef-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6e5ef-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6e5ef-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6e5ef-112">Area:</span></span>  <br/> |<span data-ttu-id="6e5ef-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="6e5ef-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6e5ef-114">备注</span><span class="sxs-lookup"><span data-stu-id="6e5ef-114">Remarks</span></span>

<span data-ttu-id="6e5ef-115">建议在所有邮件对象上使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-115">These properties are recommended on all message objects.</span></span> 
  
<span data-ttu-id="6e5ef-116">主题前缀由一个或多个字母数字字符组成，后跟冒号和空格 (作为前缀前缀) 。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-116">The subject prefix consists of one or more alphanumeric characters, followed by a colon and a space (which are part of the prefix).</span></span> <span data-ttu-id="6e5ef-117">冒号之前不得包含任何非字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-117">It must not contain any nonalphanumeric characters before the colon.</span></span> <span data-ttu-id="6e5ef-118">没有前缀可以表示为空字符串或此属性未设置。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-118">Absence of a prefix can be represented by an empty string or by this property not being set.</span></span> 
  
<span data-ttu-id="6e5ef-119">如果显式设置这些属性，则字符串的长度可以是任意长度并使用任何字母数字字符，但它必须与 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性开头的子字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-119">If these properties are set explicitly, the string can be of any length and use any alphanumeric characters, but it must match a substring at the beginning of the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span> <span data-ttu-id="6e5ef-120">如果发件人未设置这些属性并且必须计算这些属性，则其内容将受到限制。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-120">If these properties are not set by the sender and must be computed, their contents are more restricted.</span></span> <span data-ttu-id="6e5ef-121">计算前缀的规则是PR_SUBJECT必须以一、 (字母开头，) 后跟冒号和空格。 </span><span class="sxs-lookup"><span data-stu-id="6e5ef-121">The rule for computing the prefix is that **PR_SUBJECT** must begin with one, two, or three letters (alphabetic only) followed by a colon and a space.</span></span> <span data-ttu-id="6e5ef-122">如果在 PR_SUBJECT 开头找到这样的子字符串，则它将成为这些属性的字符串 (并且仍保留在PR_SUBJECT) 。 </span><span class="sxs-lookup"><span data-stu-id="6e5ef-122">If such a substring is found at the beginning of **PR_SUBJECT**, it then becomes the string for these properties (and also stays at the beginning of **PR_SUBJECT**).</span></span> <span data-ttu-id="6e5ef-123">否则，这些属性将保持未设置状态。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-123">Otherwise, these properties remain unset.</span></span> 
  
<span data-ttu-id="6e5ef-124">这些属性 **和** PR_NORMALIZED_SUBJECT ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 应作为 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 实现一部分进行计算。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-124">These properties and **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) should be computed as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) implementation.</span></span> <span data-ttu-id="6e5ef-125">在 **IMAPIProp：：SaveChanges 调用提交 IMAPIProp：：SaveChanges** 之前，客户端不应提示 [IMAPIProp：：GetProps](imapiprop-getprops.md)提供其值。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-125">A client should not prompt [IMAPIProp::GetProps](imapiprop-getprops.md) for their values until they have been committed by an **IMAPIProp::SaveChanges** call.</span></span> 
  
<span data-ttu-id="6e5ef-126">主题属性通常是少于 256 个字符的小字符串，并且邮件存储提供程序不必支持其上的 OLE **IStream** 接口。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-126">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the OLE **IStream** interface on them.</span></span> <span data-ttu-id="6e5ef-127">客户端应始终首先尝试通过 **IMAPIProp** 接口访问，并仅在返回 IStream **MAPI_E_NOT_ENOUGH_MEMORY使用\*\*\*\*IStream。**</span><span class="sxs-lookup"><span data-stu-id="6e5ef-127">A client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6e5ef-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="6e5ef-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6e5ef-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="6e5ef-129">Protocol specifications</span></span>

<span data-ttu-id="6e5ef-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6e5ef-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6e5ef-131">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-131">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6e5ef-132">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6e5ef-132">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6e5ef-133">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-133">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="6e5ef-134">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6e5ef-134">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6e5ef-135">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-135">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6e5ef-136">头文件</span><span class="sxs-lookup"><span data-stu-id="6e5ef-136">Header files</span></span>

<span data-ttu-id="6e5ef-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6e5ef-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="6e5ef-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="6e5ef-139">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6e5ef-139">Mapitags.h</span></span>
  
> <span data-ttu-id="6e5ef-140">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6e5ef-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6e5ef-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e5ef-141">See also</span></span>



[<span data-ttu-id="6e5ef-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6e5ef-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6e5ef-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6e5ef-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6e5ef-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6e5ef-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6e5ef-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6e5ef-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

