---
title: PidTagInReplyToId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInReplyToId
api_type:
- HeaderDef
ms.assetid: d435a65a-de01-4fb0-bc54-a87a2c4462ac
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 036f38c1228e08cfc9a2093c027195a802904f19
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392170"
---
# <a name="pidtaginreplytoid-canonical-property"></a><span data-ttu-id="766b6-103">PidTagInReplyToId 规范属性</span><span class="sxs-lookup"><span data-stu-id="766b6-103">PidTagInReplyToId Canonical Property</span></span>

  
  
<span data-ttu-id="766b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="766b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="766b6-105">包含原始消息的**PR_INTERNET_MESSAGE_ID** ([PidTagInternetMessageId](pidtaginternetmessageid-canonical-property.md)) 属性值。</span><span class="sxs-lookup"><span data-stu-id="766b6-105">Contains the original message's **PR_INTERNET_MESSAGE_ID** ([PidTagInternetMessageId](pidtaginternetmessageid-canonical-property.md)) property value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="766b6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="766b6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="766b6-107">PR_IN_REPLY_TO_ID，PR_IN_REPLY_TO_ID_A，PR_IN_REPLY_TO_ID_W</span><span class="sxs-lookup"><span data-stu-id="766b6-107">PR_IN_REPLY_TO_ID, PR_IN_REPLY_TO_ID_A, PR_IN_REPLY_TO_ID_W</span></span>  <br/> |
|<span data-ttu-id="766b6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="766b6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="766b6-109">0x1042</span><span class="sxs-lookup"><span data-stu-id="766b6-109">0x1042</span></span>  <br/> |
|<span data-ttu-id="766b6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="766b6-110">Data type:</span></span>  <br/> |<span data-ttu-id="766b6-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="766b6-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="766b6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="766b6-112">Area:</span></span>  <br/> |<span data-ttu-id="766b6-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="766b6-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="766b6-114">说明</span><span class="sxs-lookup"><span data-stu-id="766b6-114">Remarks</span></span>

<span data-ttu-id="766b6-115">必须在所有邮件答复设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="766b6-115">These properties must be set on all message replies.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="766b6-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="766b6-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="766b6-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="766b6-117">Protocol specifications</span></span>

<span data-ttu-id="766b6-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="766b6-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="766b6-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="766b6-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="766b6-120">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="766b6-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="766b6-121">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="766b6-121">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
<span data-ttu-id="766b6-122">[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="766b6-122">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="766b6-123">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="766b6-123">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="766b6-124">头文件</span><span class="sxs-lookup"><span data-stu-id="766b6-124">Header files</span></span>

<span data-ttu-id="766b6-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="766b6-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="766b6-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="766b6-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="766b6-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="766b6-127">Mapitags.h</span></span>
  
> <span data-ttu-id="766b6-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="766b6-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="766b6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="766b6-129">See also</span></span>



[<span data-ttu-id="766b6-130">PidTagInternetMessageId 规范属性</span><span class="sxs-lookup"><span data-stu-id="766b6-130">PidTagInternetMessageId Canonical Property</span></span>](pidtaginternetmessageid-canonical-property.md)


[<span data-ttu-id="766b6-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="766b6-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="766b6-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="766b6-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="766b6-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="766b6-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="766b6-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="766b6-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

