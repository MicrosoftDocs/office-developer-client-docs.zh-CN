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
ms.openlocfilehash: 8d58342e0460352bd9d260cb6e73de358cb2fc23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359533"
---
# <a name="pidtagrowid-canonical-property"></a><span data-ttu-id="48419-103">PidTagRowid 规范属性</span><span class="sxs-lookup"><span data-stu-id="48419-103">PidTagRowid Canonical Property</span></span>

  
  
<span data-ttu-id="48419-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48419-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48419-105">包含收件人表或状态表中的收件人的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="48419-105">Contains a unique identifier for a recipient in a recipient table or status table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="48419-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="48419-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48419-107">PR_ROWID</span><span class="sxs-lookup"><span data-stu-id="48419-107">PR_ROWID</span></span>  <br/> |
|<span data-ttu-id="48419-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="48419-108">Identifier:</span></span>  <br/> |<span data-ttu-id="48419-109">0x3000</span><span class="sxs-lookup"><span data-stu-id="48419-109">0x3000</span></span>  <br/> |
|<span data-ttu-id="48419-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48419-110">Data type:</span></span>  <br/> |<span data-ttu-id="48419-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="48419-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="48419-112">区域：</span><span class="sxs-lookup"><span data-stu-id="48419-112">Area:</span></span>  <br/> |<span data-ttu-id="48419-113">MAPI 通用</span><span class="sxs-lookup"><span data-stu-id="48419-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48419-114">注解</span><span class="sxs-lookup"><span data-stu-id="48419-114">Remarks</span></span>

<span data-ttu-id="48419-115">此属性是一个仅在拥有该表的对象的生命周期内有效的临时值。</span><span class="sxs-lookup"><span data-stu-id="48419-115">This property is a temporary value that is valid only for the life of the object that owns the table.</span></span> <span data-ttu-id="48419-116">它显示为表的一列, 但未存储。</span><span class="sxs-lookup"><span data-stu-id="48419-116">It appears as a column of the table but is not stored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="48419-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="48419-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="48419-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="48419-118">Protocol specifications</span></span>

<span data-ttu-id="48419-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48419-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48419-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="48419-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="48419-121">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48419-121">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48419-122">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="48419-122">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="48419-123">头文件</span><span class="sxs-lookup"><span data-stu-id="48419-123">Header files</span></span>

<span data-ttu-id="48419-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="48419-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="48419-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48419-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="48419-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="48419-126">Mapitags.h</span></span>
  
> <span data-ttu-id="48419-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="48419-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48419-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48419-128">See also</span></span>



[<span data-ttu-id="48419-129">IMessage::GetRecipientTable</span><span class="sxs-lookup"><span data-stu-id="48419-129">IMessage::GetRecipientTable</span></span>](imessage-getrecipienttable.md)
  
[<span data-ttu-id="48419-130">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="48419-130">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)


[<span data-ttu-id="48419-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48419-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48419-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48419-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48419-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="48419-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48419-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48419-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

