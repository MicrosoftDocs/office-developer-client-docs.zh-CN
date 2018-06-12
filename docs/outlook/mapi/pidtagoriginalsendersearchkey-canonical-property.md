---
title: PidTagOriginalSenderSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSenderSearchKey
api_type:
- COM
ms.assetid: 164eb9dd-e553-459e-99c1-3da0284bb01f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2aa0a8601a72b6d4c40167ac55d3d643bf946708
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777950"
---
# <a name="pidtagoriginalsendersearchkey-canonical-property"></a><span data-ttu-id="6022f-103">PidTagOriginalSenderSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="6022f-103">PidTagOriginalSenderSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="6022f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6022f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6022f-105">包含搜索关键字的第一个版本的一条消息，即之前正在转发或答复邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="6022f-105">Contains the search key for the sender of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6022f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6022f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6022f-107">PR_ORIGINAL_SENDER_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="6022f-107">PR_ORIGINAL_SENDER_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="6022f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6022f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6022f-109">0x005C</span><span class="sxs-lookup"><span data-stu-id="6022f-109">0x005C</span></span>  <br/> |
|<span data-ttu-id="6022f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6022f-110">Data type:</span></span>  <br/> |<span data-ttu-id="6022f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6022f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6022f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6022f-112">Area:</span></span>  <br/> |<span data-ttu-id="6022f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="6022f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6022f-114">备注</span><span class="sxs-lookup"><span data-stu-id="6022f-114">Remarks</span></span>

<span data-ttu-id="6022f-115">此属性是一条消息的原始发件人的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="6022f-115">This property is one of the address properties for the original sender of a message.</span></span> <span data-ttu-id="6022f-116">在首次提交邮件，客户端应用程序应将此属性设置为**PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6022f-116">At first submission of the message, the client application should set this property to the value of the **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)) property.</span></span> <span data-ttu-id="6022f-117">当转发或答复邮件永远不会更改它。</span><span class="sxs-lookup"><span data-stu-id="6022f-117">It is never changed when the message is forwarded or replied to.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6022f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6022f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6022f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6022f-119">Protocol specifications</span></span>

<span data-ttu-id="6022f-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6022f-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6022f-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6022f-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6022f-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6022f-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6022f-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="6022f-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6022f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6022f-124">Header files</span></span>

<span data-ttu-id="6022f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6022f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6022f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6022f-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="6022f-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6022f-127">Mapitags.h</span></span>
  
> <span data-ttu-id="6022f-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6022f-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6022f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6022f-129">See also</span></span>



[<span data-ttu-id="6022f-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6022f-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6022f-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6022f-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6022f-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6022f-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6022f-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6022f-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

