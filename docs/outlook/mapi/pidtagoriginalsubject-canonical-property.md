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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6cf81a5b4c10cb7bff5f03a1b25d11bbaa8ff277
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777971"
---
# <a name="pidtagoriginalsubject-canonical-property"></a><span data-ttu-id="68075-103">PidTagOriginalSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="68075-103">PidTagOriginalSubject Canonical Property</span></span>

  
  
<span data-ttu-id="68075-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="68075-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="68075-105">包含用于报告有关邮件原始邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="68075-105">Contains the subject of an original message for use in a report about the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="68075-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="68075-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="68075-107">PR_ORIGINAL_SUBJECT，PR_ORIGINAL_SUBJECT_A，PR_ORIGINAL_SUBJECT_W</span><span class="sxs-lookup"><span data-stu-id="68075-107">PR_ORIGINAL_SUBJECT, PR_ORIGINAL_SUBJECT_A, PR_ORIGINAL_SUBJECT_W</span></span>  <br/> |
|<span data-ttu-id="68075-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="68075-108">Identifier:</span></span>  <br/> |<span data-ttu-id="68075-109">0x0049</span><span class="sxs-lookup"><span data-stu-id="68075-109">0x0049</span></span>  <br/> |
|<span data-ttu-id="68075-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="68075-110">Data type:</span></span>  <br/> |<span data-ttu-id="68075-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="68075-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="68075-112">区域：</span><span class="sxs-lookup"><span data-stu-id="68075-112">Area:</span></span>  <br/> |<span data-ttu-id="68075-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="68075-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68075-114">备注</span><span class="sxs-lookup"><span data-stu-id="68075-114">Remarks</span></span>

<span data-ttu-id="68075-115">这些属性最初设置为相同的值的**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="68075-115">These properties are originally set to the same value as the **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="68075-116">Subject 属性均通常较小字符串少于 256 个字符，并且消息存储提供程序不支持这些对象链接和嵌入 (OLE) **IStream**接口的义务。</span><span class="sxs-lookup"><span data-stu-id="68075-116">The subject properties are typically small strings of fewer than 256 characters, and a message store provider is not obligated to support the Object Linking and Embedding (OLE) **IStream** interface on them.</span></span> <span data-ttu-id="68075-117">客户端应始终尝试通过**IMAPIProp**接口访问首先，以及**IStream**仅当返回**MAPI_E_NOT_ENOUGH_MEMORY** 。</span><span class="sxs-lookup"><span data-stu-id="68075-117">The client should always attempt access through the **IMAPIProp** interface first, and resort to **IStream** only if **MAPI_E_NOT_ENOUGH_MEMORY** is returned.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="68075-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="68075-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="68075-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="68075-119">Protocol specifications</span></span>

<span data-ttu-id="68075-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68075-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68075-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="68075-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="68075-122">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68075-122">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68075-123">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="68075-123">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="68075-124">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68075-124">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68075-125">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="68075-125">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="68075-126">头文件</span><span class="sxs-lookup"><span data-stu-id="68075-126">Header files</span></span>

<span data-ttu-id="68075-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="68075-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="68075-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="68075-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="68075-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="68075-129">Mapitags.h</span></span>
  
> <span data-ttu-id="68075-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="68075-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="68075-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68075-131">See also</span></span>



[<span data-ttu-id="68075-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="68075-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="68075-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="68075-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="68075-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68075-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="68075-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68075-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

