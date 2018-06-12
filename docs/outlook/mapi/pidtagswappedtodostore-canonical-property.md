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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cbe1915df46010c5574065826ac1814f45c8c093
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778521"
---
# <a name="pidtagswappedtodostore-canonical-property"></a><span data-ttu-id="4301f-103">PidTagSwappedToDoStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="4301f-103">PidTagSwappedToDoStore Canonical Property</span></span>

  
  
<span data-ttu-id="4301f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4301f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4301f-105">确定是否需要为后传送的电子邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="4301f-105">Determines the need for post-transmit processing of an email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4301f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="4301f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4301f-107">PR_SWAPPED_TODO_STORE</span><span class="sxs-lookup"><span data-stu-id="4301f-107">PR_SWAPPED_TODO_STORE</span></span>  <br/> |
|<span data-ttu-id="4301f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4301f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4301f-109">0x0E2C</span><span class="sxs-lookup"><span data-stu-id="4301f-109">0x0E2C</span></span>  <br/> |
|<span data-ttu-id="4301f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4301f-110">Data type:</span></span>  <br/> |<span data-ttu-id="4301f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4301f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4301f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4301f-112">Area:</span></span>  <br/> |<span data-ttu-id="4301f-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="4301f-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4301f-114">备注</span><span class="sxs-lookup"><span data-stu-id="4301f-114">Remarks</span></span>

<span data-ttu-id="4301f-115">如果邮件草稿上设置此属性，然后它的值必须设置为**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 的邮件的属性的值。</span><span class="sxs-lookup"><span data-stu-id="4301f-115">If this property is set on a draft message, then its value must be set to the value of **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property of the message.</span></span>
  
<span data-ttu-id="4301f-116">有关详细信息，请参阅[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)节"后传输处理已标记邮件。"</span><span class="sxs-lookup"><span data-stu-id="4301f-116">For more information, see [[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx) section "Post-Transmit Processing of a Flagged Message."</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4301f-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="4301f-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4301f-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="4301f-118">Protocol specifications</span></span>

<span data-ttu-id="4301f-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4301f-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4301f-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4301f-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4301f-121">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4301f-121">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4301f-122">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="4301f-122">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="4301f-123">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4301f-123">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4301f-124">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="4301f-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4301f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="4301f-125">Header files</span></span>

<span data-ttu-id="4301f-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4301f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="4301f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4301f-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="4301f-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4301f-128">Mapitags.h</span></span>
  
> <span data-ttu-id="4301f-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4301f-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4301f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4301f-130">See also</span></span>



[<span data-ttu-id="4301f-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4301f-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4301f-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4301f-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4301f-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4301f-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4301f-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4301f-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

