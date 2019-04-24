---
title: PidTagOriginalSubject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSubject
api_type:
- COM
ms.assetid: 8668ba4f-3236-4a87-a5aa-9cf7eea3d87b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de957c33165cc96eec82bf95c8f292c5b323676a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331141"
---
# <a name="pidtagoriginalsubject-canonical-property"></a><span data-ttu-id="b080b-103">PidTagOriginalSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="b080b-103">PidTagOriginalSubject Canonical Property</span></span>

  
  
<span data-ttu-id="b080b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b080b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b080b-105">包含原始邮件的主题, 以供在有关邮件的报告中使用。</span><span class="sxs-lookup"><span data-stu-id="b080b-105">Contains the subject of an original message for use in a report about the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b080b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b080b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b080b-107">PR_ORIGINAL_SUBJECT、PR_ORIGINAL_SUBJECT_A、PR_ORIGINAL_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="b080b-107">PR_ORIGINAL_SUBJECT, PR_ORIGINAL_SUBJECT_A, PR_ORIGINAL_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="b080b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b080b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b080b-109">0x0049</span><span class="sxs-lookup"><span data-stu-id="b080b-109">0x0049</span></span>  <br/> |
|<span data-ttu-id="b080b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b080b-110">Data type:</span></span>  <br/> |<span data-ttu-id="b080b-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b080b-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b080b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b080b-112">Area:</span></span>  <br/> |<span data-ttu-id="b080b-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="b080b-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b080b-114">注解</span><span class="sxs-lookup"><span data-stu-id="b080b-114">Remarks</span></span>

<span data-ttu-id="b080b-115">这些属性最初设置为与**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="b080b-115">These properties are originally set to the same value as the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="b080b-116">subject 属性通常是少于256个字符的较小字符串, 而邮件存储区提供程序并不是支持其上的对象链接和嵌入 (OLE) **IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="b080b-116">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the Object Linking and Embedding (OLE) **IStream** interface on them.</span></span> <span data-ttu-id="b080b-117">客户端应始终先尝试通过**IMAPIProp**接口访问, 并且只有在返回**MAPI_E_NOT_ENOUGH_MEMORY**时才会转到**IStream** 。</span><span class="sxs-lookup"><span data-stu-id="b080b-117">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b080b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b080b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b080b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b080b-119">Protocol specifications</span></span>

<span data-ttu-id="b080b-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b080b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b080b-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b080b-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b080b-122">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b080b-122">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b080b-123">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="b080b-123">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="b080b-124">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b080b-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b080b-125">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b080b-125">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b080b-126">头文件</span><span class="sxs-lookup"><span data-stu-id="b080b-126">Header files</span></span>

<span data-ttu-id="b080b-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b080b-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="b080b-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b080b-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="b080b-129">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b080b-129">Mapitags.h</span></span>
  
> <span data-ttu-id="b080b-130">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b080b-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b080b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b080b-131">See also</span></span>



[<span data-ttu-id="b080b-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b080b-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b080b-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b080b-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b080b-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b080b-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b080b-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b080b-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

