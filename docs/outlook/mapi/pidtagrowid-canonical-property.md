---
title: PidTagRowid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRowid
api_type:
- COM
ms.assetid: 0fdcb55a-2971-4c7d-b61e-7ada2d19d0e6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e8d0e79e01040c1cc3d46e73a7e6a456a915a67f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778232"
---
# <a name="pidtagrowid-canonical-property"></a><span data-ttu-id="202aa-103">PidTagRowid 规范属性</span><span class="sxs-lookup"><span data-stu-id="202aa-103">PidTagRowid Canonical Property</span></span>

  
  
<span data-ttu-id="202aa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="202aa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="202aa-105">包含的收件人的表或状态表中的收件人的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="202aa-105">Contains a unique identifier for a recipient in a recipient table or status table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="202aa-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="202aa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="202aa-107">PR_ROWID</span><span class="sxs-lookup"><span data-stu-id="202aa-107">PR_ROWID</span></span>  <br/> |
|<span data-ttu-id="202aa-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="202aa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="202aa-109">0x3000</span><span class="sxs-lookup"><span data-stu-id="202aa-109">0x3000</span></span>  <br/> |
|<span data-ttu-id="202aa-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="202aa-110">Data type:</span></span>  <br/> |<span data-ttu-id="202aa-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="202aa-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="202aa-112">区域：</span><span class="sxs-lookup"><span data-stu-id="202aa-112">Area:</span></span>  <br/> |<span data-ttu-id="202aa-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="202aa-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="202aa-114">备注</span><span class="sxs-lookup"><span data-stu-id="202aa-114">Remarks</span></span>

<span data-ttu-id="202aa-115">此属性是对象的仅对拥有表的生存期内有效临时值。</span><span class="sxs-lookup"><span data-stu-id="202aa-115">This property is a temporary value that is valid only for the life of the object that owns the table.</span></span> <span data-ttu-id="202aa-116">它显示为表的列，但不是存储。</span><span class="sxs-lookup"><span data-stu-id="202aa-116">It appears as a column of the table but is not stored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="202aa-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="202aa-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="202aa-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="202aa-118">Protocol specifications</span></span>

<span data-ttu-id="202aa-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="202aa-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="202aa-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="202aa-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="202aa-121">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="202aa-121">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="202aa-122">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="202aa-122">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="202aa-123">头文件</span><span class="sxs-lookup"><span data-stu-id="202aa-123">Header files</span></span>

<span data-ttu-id="202aa-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="202aa-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="202aa-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="202aa-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="202aa-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="202aa-126">Mapitags.h</span></span>
  
> <span data-ttu-id="202aa-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="202aa-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="202aa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="202aa-128">See also</span></span>



[<span data-ttu-id="202aa-129">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="202aa-129">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="202aa-130">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="202aa-130">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)


[<span data-ttu-id="202aa-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="202aa-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="202aa-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="202aa-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="202aa-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="202aa-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="202aa-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="202aa-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

