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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efa778f51ac047c911deb6a3c4d5d9e718dc33fb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565037"
---
# <a name="pidtagrowid-canonical-property"></a><span data-ttu-id="f3ee5-103">PidTagRowid 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3ee5-103">PidTagRowid Canonical Property</span></span>

  
  
<span data-ttu-id="f3ee5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3ee5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3ee5-105">包含的收件人的表或状态表中的收件人的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-105">Contains a unique identifier for a recipient in a recipient table or status table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f3ee5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f3ee5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f3ee5-107">PR_ROWID</span><span class="sxs-lookup"><span data-stu-id="f3ee5-107">PR_ROWID</span></span>  <br/> |
|<span data-ttu-id="f3ee5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f3ee5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f3ee5-109">0x3000</span><span class="sxs-lookup"><span data-stu-id="f3ee5-109">0x3000</span></span>  <br/> |
|<span data-ttu-id="f3ee5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f3ee5-110">Data type:</span></span>  <br/> |<span data-ttu-id="f3ee5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f3ee5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f3ee5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f3ee5-112">Area:</span></span>  <br/> |<span data-ttu-id="f3ee5-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="f3ee5-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f3ee5-114">注解</span><span class="sxs-lookup"><span data-stu-id="f3ee5-114">Remarks</span></span>

<span data-ttu-id="f3ee5-115">此属性是对象的仅对拥有表的生存期内有效临时值。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-115">This property is a temporary value that is valid only for the life of the object that owns the table.</span></span> <span data-ttu-id="f3ee5-116">它显示为表的列，但不是存储。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-116">It appears as a column of the table but is not stored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f3ee5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="f3ee5-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f3ee5-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="f3ee5-118">Protocol specifications</span></span>

<span data-ttu-id="f3ee5-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3ee5-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3ee5-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f3ee5-121">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f3ee5-121">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f3ee5-122">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-122">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f3ee5-123">头文件</span><span class="sxs-lookup"><span data-stu-id="f3ee5-123">Header files</span></span>

<span data-ttu-id="f3ee5-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f3ee5-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="f3ee5-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="f3ee5-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f3ee5-126">Mapitags.h</span></span>
  
> <span data-ttu-id="f3ee5-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f3ee5-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3ee5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3ee5-128">See also</span></span>



[<span data-ttu-id="f3ee5-129">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="f3ee5-129">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="f3ee5-130">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="f3ee5-130">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)


[<span data-ttu-id="f3ee5-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f3ee5-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f3ee5-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f3ee5-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f3ee5-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f3ee5-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f3ee5-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f3ee5-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

