---
title: PidTagSwappedToDoStore 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSwappedToDoStore
api_type:
- COM
ms.assetid: 1edae9ac-fc9a-4bfe-b053-99de848c5144
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41aa97a52176cf68775d6fd507d3d042888092cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358903"
---
# <a name="pidtagswappedtodostore-canonical-property"></a><span data-ttu-id="9549f-103">PidTagSwappedToDoStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="9549f-103">PidTagSwappedToDoStore Canonical Property</span></span>

  
  
<span data-ttu-id="9549f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9549f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9549f-105">确定是否需要对电子邮件进行后传输处理。</span><span class="sxs-lookup"><span data-stu-id="9549f-105">Determines the need for post-transmit processing of an email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9549f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9549f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9549f-107">PR_SWAPPED_TODO_STORE</span><span class="sxs-lookup"><span data-stu-id="9549f-107">PR_SWAPPED_TODO_STORE</span></span>  <br/> |
|<span data-ttu-id="9549f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9549f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9549f-109">0x0E2C</span><span class="sxs-lookup"><span data-stu-id="9549f-109">0x0E2C</span></span>  <br/> |
|<span data-ttu-id="9549f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9549f-110">Data type:</span></span>  <br/> |<span data-ttu-id="9549f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9549f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9549f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9549f-112">Area:</span></span>  <br/> |<span data-ttu-id="9549f-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="9549f-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9549f-114">注解</span><span class="sxs-lookup"><span data-stu-id="9549f-114">Remarks</span></span>

<span data-ttu-id="9549f-115">如果在草稿邮件上设置此属性, 则必须将其值设置为邮件的**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="9549f-115">If this property is set on a draft message, then its value must be set to the value of **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property of the message.</span></span>
  
<span data-ttu-id="9549f-116">有关详细信息, 请参阅[[OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)一节 "已标记邮件的传送后处理" 部分。</span><span class="sxs-lookup"><span data-stu-id="9549f-116">For more information, see [[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx) section "Post-Transmit Processing of a Flagged Message."</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9549f-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9549f-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9549f-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="9549f-118">Protocol specifications</span></span>

<span data-ttu-id="9549f-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9549f-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9549f-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9549f-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9549f-121">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9549f-121">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9549f-122">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9549f-122">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="9549f-123">[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9549f-123">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9549f-124">指定用于电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="9549f-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9549f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="9549f-125">Header files</span></span>

<span data-ttu-id="9549f-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9549f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="9549f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9549f-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="9549f-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="9549f-128">Mapitags.h</span></span>
  
> <span data-ttu-id="9549f-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9549f-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9549f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9549f-130">See also</span></span>



[<span data-ttu-id="9549f-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9549f-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9549f-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9549f-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9549f-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9549f-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9549f-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9549f-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

