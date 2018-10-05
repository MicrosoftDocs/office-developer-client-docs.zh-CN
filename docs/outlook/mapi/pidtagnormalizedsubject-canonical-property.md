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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393227"
---
# <a name="pidtagnormalizedsubject-canonical-property"></a><span data-ttu-id="33992-103">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="33992-103">PidTagNormalizedSubject Canonical Property</span></span>

  
  
<span data-ttu-id="33992-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33992-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33992-105">包含与删除任何前缀的邮件主题。</span><span class="sxs-lookup"><span data-stu-id="33992-105">Contains the message subject with any prefix removed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="33992-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="33992-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="33992-107">PR_NORMALIZED_SUBJECT，PR_NORMALIZED_SUBJECT_A，PR_NORMALIZED_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="33992-107">PR_NORMALIZED_SUBJECT, PR_NORMALIZED_SUBJECT_A, PR_NORMALIZED_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="33992-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="33992-108">Identifier:</span></span>  <br/> |<span data-ttu-id="33992-109">0x0E1D</span><span class="sxs-lookup"><span data-stu-id="33992-109">0x0E1D</span></span>  <br/> |
|<span data-ttu-id="33992-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="33992-110">Data type:</span></span>  <br/> |<span data-ttu-id="33992-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="33992-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="33992-112">区域：</span><span class="sxs-lookup"><span data-stu-id="33992-112">Area:</span></span>  <br/> |<span data-ttu-id="33992-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="33992-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="33992-114">说明</span><span class="sxs-lookup"><span data-stu-id="33992-114">Remarks</span></span>

<span data-ttu-id="33992-115">这些属性由消息存储计算，或按以下方式传输提供程序从**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 和**PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="33992-115">These properties are computed by message store or transport providers from the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) and **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) properties in the following manner.</span></span>
  
- <span data-ttu-id="33992-116">如果**PR_SUBJECT_PREFIX**存在并且**PR_SUBJECT**初始子， **PR_NORMALIZED_SUBJECT**和关联的属性设置为的**PR_SUBJECT**内容移除了前缀。</span><span class="sxs-lookup"><span data-stu-id="33992-116">If the **PR_SUBJECT_PREFIX** is present and is an initial substring of **PR_SUBJECT**, **PR_NORMALIZED_SUBJECT** and associated properties are set to the contents of **PR_SUBJECT** with the prefix removed.</span></span> 
    
- <span data-ttu-id="33992-117">如果**PR_SUBJECT_PREFIX**是存在此参数，但它并不**PR_SUBJECT**初始子， **PR_SUBJECT_PREFIX**删除和重新计算从**PR_SUBJECT**使用以下规则： 如果**PR_SUBJECT**中包含的字符串开头一到三个非数字字符后跟一个冒号和一个空格，则与冒号和空白一起字符串成为前缀。</span><span class="sxs-lookup"><span data-stu-id="33992-117">If **PR_SUBJECT_PREFIX** is present, but it is not an initial substring of **PR_SUBJECT**, **PR_SUBJECT_PREFIX** is deleted and recalculated from **PR_SUBJECT** using the following rule: If the string contained in **PR_SUBJECT** begins with one to three non-numeric characters followed by a colon and a space, then the string together with the colon and the blank becomes the prefix.</span></span> <span data-ttu-id="33992-118">数字、 空格和标点的字符不是有效的前缀字符。</span><span class="sxs-lookup"><span data-stu-id="33992-118">Numbers, blanks, and punctuation characters are not valid prefix characters.</span></span> 
    
- <span data-ttu-id="33992-119">如果**PR_SUBJECT_PREFIX**不存在，它是从**PR_SUBJECT**使用上一步中所述的规则进行计算。</span><span class="sxs-lookup"><span data-stu-id="33992-119">If **PR_SUBJECT_PREFIX** is not present, it is calculated from **PR_SUBJECT** using the rule outlined in the previous step.</span></span> <span data-ttu-id="33992-120">此属性然后设置为的**PR_SUBJECT**内容移除了前缀。</span><span class="sxs-lookup"><span data-stu-id="33992-120">This property then is set to the contents of **PR_SUBJECT** with the prefix removed.</span></span> 
    
 <span data-ttu-id="33992-121">**注释**当**PR_SUBJECT_PREFIX**就为空字符串时， **PR_SUBJECT**和此属性是相同。</span><span class="sxs-lookup"><span data-stu-id="33992-121">**Note** When **PR_SUBJECT_PREFIX** is an empty string, **PR_SUBJECT** and this property are the same.</span></span> 
  
<span data-ttu-id="33992-122">最后，此属性应为**PR_SUBJECT**关注前缀的一部分。</span><span class="sxs-lookup"><span data-stu-id="33992-122">Ultimately, this property should be the part of **PR_SUBJECT** following the prefix.</span></span> <span data-ttu-id="33992-123">如果没有前缀，此属性将成为**PR_SUBJECT**相同。</span><span class="sxs-lookup"><span data-stu-id="33992-123">If there is no prefix, this property becomes the same as **PR_SUBJECT**.</span></span>
  
 <span data-ttu-id="33992-124">**PR_SUBJECT_PREFIX**和此属性应计算作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)实现的一部分。</span><span class="sxs-lookup"><span data-stu-id="33992-124">**PR_SUBJECT_PREFIX** and this property should be computed as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) implementation.</span></span> <span data-ttu-id="33992-125">客户端应用程序应不提示其值的[IMAPIProp::GetProps](imapiprop-getprops.md)方法之前已经提交由**IMAPIProp::SaveChanges**呼叫。</span><span class="sxs-lookup"><span data-stu-id="33992-125">A client application should not prompt the [IMAPIProp::GetProps](imapiprop-getprops.md) method for their values until they have been committed by an **IMAPIProp::SaveChanges** call.</span></span> 
  
<span data-ttu-id="33992-126">Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些对象链接和嵌入 (OLE) **IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="33992-126">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the Object Linking and Embedding (OLE) **IStream** interface on them.</span></span> <span data-ttu-id="33992-127">客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回 MAPI_E_NOT_ENOUGH_MEMORY。</span><span class="sxs-lookup"><span data-stu-id="33992-127">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if MAPI_E_NOT_ENOUGH_MEMORY is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="33992-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="33992-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="33992-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="33992-129">Protocol specifications</span></span>

<span data-ttu-id="33992-130">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33992-130">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33992-131">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="33992-131">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="33992-132">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33992-132">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33992-133">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="33992-133">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="33992-134">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="33992-134">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="33992-135">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="33992-135">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="33992-136">头文件</span><span class="sxs-lookup"><span data-stu-id="33992-136">Header files</span></span>

<span data-ttu-id="33992-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="33992-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="33992-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="33992-138">Provides data type definitions.</span></span>
    
<span data-ttu-id="33992-139">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="33992-139">Mapitags.h</span></span>
  
> <span data-ttu-id="33992-140">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="33992-140">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33992-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33992-141">See also</span></span>



[<span data-ttu-id="33992-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="33992-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="33992-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="33992-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="33992-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="33992-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="33992-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="33992-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

