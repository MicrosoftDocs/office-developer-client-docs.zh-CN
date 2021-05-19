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
# <a name="pidtagoriginalsubject-canonical-property"></a><span data-ttu-id="06d2b-103">PidTagOriginalSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="06d2b-103">PidTagOriginalSubject Canonical Property</span></span>

  
  
<span data-ttu-id="06d2b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06d2b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06d2b-105">包含原始邮件的主题，用于有关邮件的报告。</span><span class="sxs-lookup"><span data-stu-id="06d2b-105">Contains the subject of an original message for use in a report about the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="06d2b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="06d2b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="06d2b-107">PR_ORIGINAL_SUBJECT、PR_ORIGINAL_SUBJECT_A、PR_ORIGINAL_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="06d2b-107">PR_ORIGINAL_SUBJECT, PR_ORIGINAL_SUBJECT_A, PR_ORIGINAL_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="06d2b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="06d2b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="06d2b-109">0x0049</span><span class="sxs-lookup"><span data-stu-id="06d2b-109">0x0049</span></span>  <br/> |
|<span data-ttu-id="06d2b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="06d2b-110">Data type:</span></span>  <br/> |<span data-ttu-id="06d2b-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="06d2b-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="06d2b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="06d2b-112">Area:</span></span>  <br/> |<span data-ttu-id="06d2b-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="06d2b-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="06d2b-114">备注</span><span class="sxs-lookup"><span data-stu-id="06d2b-114">Remarks</span></span>

<span data-ttu-id="06d2b-115">这些属性最初设置为与[PidTagSubject](pidtagsubject-canonical-property.md)属性PR_SUBJECT (相同的) 值。 </span><span class="sxs-lookup"><span data-stu-id="06d2b-115">These properties are originally set to the same value as the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="06d2b-116">主题属性通常是少于 256 个字符的小字符串，邮件存储提供程序不必支持对象链接和嵌入 (OLE) **IStream** 接口。</span><span class="sxs-lookup"><span data-stu-id="06d2b-116">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the Object Linking and Embedding (OLE) **IStream** interface on them.</span></span> <span data-ttu-id="06d2b-117">客户端应始终首先尝试通过 **IMAPIProp** 接口访问，并仅在返回 IStream  MAPI_E_NOT_ENOUGH_MEMORY **IStream。**</span><span class="sxs-lookup"><span data-stu-id="06d2b-117">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="06d2b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="06d2b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="06d2b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="06d2b-119">Protocol specifications</span></span>

<span data-ttu-id="06d2b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="06d2b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="06d2b-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="06d2b-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="06d2b-122">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="06d2b-122">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="06d2b-123">处理在服务器和客户端之间同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="06d2b-123">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="06d2b-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="06d2b-124">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="06d2b-125">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="06d2b-125">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="06d2b-126">头文件</span><span class="sxs-lookup"><span data-stu-id="06d2b-126">Header files</span></span>

<span data-ttu-id="06d2b-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="06d2b-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="06d2b-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="06d2b-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="06d2b-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="06d2b-129">Mapitags.h</span></span>
  
> <span data-ttu-id="06d2b-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="06d2b-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="06d2b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06d2b-131">See also</span></span>



[<span data-ttu-id="06d2b-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="06d2b-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="06d2b-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="06d2b-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="06d2b-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="06d2b-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="06d2b-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="06d2b-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

