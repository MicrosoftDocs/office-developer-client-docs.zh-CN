---
title: PidTagNormalizedSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNormalizedSubject
api_type:
- HeaderDef
ms.assetid: 2000e6e8-d908-4814-8093-28f8011250c8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 54a0f438dacc8a1c7838eb538ec05c5c263f1b0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329272"
---
# <a name="pidtagnormalizedsubject-canonical-property"></a><span data-ttu-id="90f99-103">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="90f99-103">PidTagNormalizedSubject Canonical Property</span></span>

  
  
<span data-ttu-id="90f99-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90f99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90f99-105">包含删除了任何前缀的邮件主题。</span><span class="sxs-lookup"><span data-stu-id="90f99-105">Contains the message subject with any prefix removed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="90f99-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="90f99-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="90f99-107">PR_NORMALIZED_SUBJECT、PR_NORMALIZED_SUBJECT_A、PR_NORMALIZED_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="90f99-107">PR_NORMALIZED_SUBJECT, PR_NORMALIZED_SUBJECT_A, PR_NORMALIZED_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="90f99-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="90f99-108">Identifier:</span></span>  <br/> |<span data-ttu-id="90f99-109">0x0E1D</span><span class="sxs-lookup"><span data-stu-id="90f99-109">0x0E1D</span></span>  <br/> |
|<span data-ttu-id="90f99-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="90f99-110">Data type:</span></span>  <br/> |<span data-ttu-id="90f99-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="90f99-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="90f99-112">区域：</span><span class="sxs-lookup"><span data-stu-id="90f99-112">Area:</span></span>  <br/> |<span data-ttu-id="90f99-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="90f99-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90f99-114">注解</span><span class="sxs-lookup"><span data-stu-id="90f99-114">Remarks</span></span>

<span data-ttu-id="90f99-115">这些属性由**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性中的邮件存储或传输提供程序按以下方式进行计算。</span><span class="sxs-lookup"><span data-stu-id="90f99-115">These properties are computed by message store or transport providers from the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) and **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) properties in the following manner.</span></span>
  
- <span data-ttu-id="90f99-116">如果**PR_SUBJECT_PREFIX**存在, 并且是**PR_SUBJECT**的初始子字符串, 则将**PR_NORMALIZED_SUBJECT**和关联属性设置为删除了前缀的**PR_SUBJECT**的内容。</span><span class="sxs-lookup"><span data-stu-id="90f99-116">If the **PR_SUBJECT_PREFIX** is present and is an initial substring of **PR_SUBJECT**, **PR_NORMALIZED_SUBJECT** and associated properties are set to the contents of **PR_SUBJECT** with the prefix removed.</span></span> 
    
- <span data-ttu-id="90f99-117">如果存在**PR_SUBJECT_PREFIX** , 但它不是**PR_SUBJECT**的初始子字符串, 则使用以下规则从**PR_SUBJECT**中删除并重新计算**PR_SUBJECT_PREFIX** : 如果**PR_SUBJECT**中包含的字符串。以一个到三个非数字字符开头, 后跟一个冒号和一个空格, 然后将字符串与冒号一起使用, 空将成为前缀。</span><span class="sxs-lookup"><span data-stu-id="90f99-117">If **PR_SUBJECT_PREFIX** is present, but it is not an initial substring of **PR_SUBJECT**, **PR_SUBJECT_PREFIX** is deleted and recalculated from **PR_SUBJECT** using the following rule: If the string contained in **PR_SUBJECT** begins with one to three non-numeric characters followed by a colon and a space, then the string together with the colon and the blank becomes the prefix.</span></span> <span data-ttu-id="90f99-118">数字、空格和标点字符不是有效的前缀字符。</span><span class="sxs-lookup"><span data-stu-id="90f99-118">Numbers, blanks, and punctuation characters are not valid prefix characters.</span></span> 
    
- <span data-ttu-id="90f99-119">如果**PR_SUBJECT_PREFIX**不存在, 则使用上一步中所述的规则从**PR_SUBJECT**计算。</span><span class="sxs-lookup"><span data-stu-id="90f99-119">If **PR_SUBJECT_PREFIX** is not present, it is calculated from **PR_SUBJECT** using the rule outlined in the previous step.</span></span> <span data-ttu-id="90f99-120">然后, 将此属性设置为删除了前缀的**PR_SUBJECT**的内容。</span><span class="sxs-lookup"><span data-stu-id="90f99-120">This property then is set to the contents of **PR_SUBJECT** with the prefix removed.</span></span> 
    
 <span data-ttu-id="90f99-121">**注释**当**PR_SUBJECT_PREFIX**为空字符串时, **PR_SUBJECT**和此属性相同。</span><span class="sxs-lookup"><span data-stu-id="90f99-121">**Note** When **PR_SUBJECT_PREFIX** is an empty string, **PR_SUBJECT** and this property are the same.</span></span> 
  
<span data-ttu-id="90f99-122">最终, 此属性应是前缀后面的**PR_SUBJECT**的一部分。</span><span class="sxs-lookup"><span data-stu-id="90f99-122">Ultimately, this property should be the part of **PR_SUBJECT** following the prefix.</span></span> <span data-ttu-id="90f99-123">如果没有前缀, 则此属性将变为**PR_SUBJECT**。</span><span class="sxs-lookup"><span data-stu-id="90f99-123">If there is no prefix, this property becomes the same as **PR_SUBJECT**.</span></span>
  
 <span data-ttu-id="90f99-124">**PR_SUBJECT_PREFIX**和此属性应作为[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)实现的一部分进行计算。</span><span class="sxs-lookup"><span data-stu-id="90f99-124">**PR_SUBJECT_PREFIX** and this property should be computed as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) implementation.</span></span> <span data-ttu-id="90f99-125">客户端应用程序不应提示[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的值, 直到它们已被**IMAPIProp:: SaveChanges**调用提交。</span><span class="sxs-lookup"><span data-stu-id="90f99-125">A client application should not prompt the [IMAPIProp::GetProps](imapiprop-getprops.md) method for their values until they have been committed by an **IMAPIProp::SaveChanges** call.</span></span> 
  
<span data-ttu-id="90f99-126">subject 属性通常是少于256个字符的较小字符串, 而邮件存储区提供程序并不是支持其上的对象链接和嵌入 (OLE) **IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="90f99-126">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the Object Linking and Embedding (OLE) **IStream** interface on them.</span></span> <span data-ttu-id="90f99-127">客户端应始终先尝试通过**IMAPIProp**接口访问, 并且只有在返回 MAPI_E_NOT_ENOUGH_MEMORY 时才会转到**IStream** 。</span><span class="sxs-lookup"><span data-stu-id="90f99-127">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if MAPI_E_NOT_ENOUGH_MEMORY is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="90f99-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="90f99-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="90f99-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="90f99-129">Protocol specifications</span></span>

<span data-ttu-id="90f99-130">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90f99-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90f99-131">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="90f99-131">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="90f99-132">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90f99-132">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90f99-133">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="90f99-133">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="90f99-134">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90f99-134">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90f99-135">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="90f99-135">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="90f99-136">头文件</span><span class="sxs-lookup"><span data-stu-id="90f99-136">Header files</span></span>

<span data-ttu-id="90f99-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="90f99-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="90f99-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="90f99-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="90f99-139">Mapitags</span><span class="sxs-lookup"><span data-stu-id="90f99-139">Mapitags.h</span></span>
  
> <span data-ttu-id="90f99-140">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="90f99-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="90f99-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90f99-141">See also</span></span>



[<span data-ttu-id="90f99-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="90f99-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="90f99-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="90f99-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="90f99-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="90f99-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="90f99-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="90f99-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

