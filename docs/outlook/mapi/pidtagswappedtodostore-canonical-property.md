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
ms.openlocfilehash: fff9e488a83246f78058a699e637d83bb159ed33
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577343"
---
# <a name="pidtagswappedtodostore-canonical-property"></a><span data-ttu-id="5fa3a-103">PidTagSwappedToDoStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fa3a-103">PidTagSwappedToDoStore Canonical Property</span></span>

  
  
<span data-ttu-id="5fa3a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5fa3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5fa3a-105">确定是否需要为后传送的电子邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-105">Determines the need for post-transmit processing of an email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5fa3a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5fa3a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5fa3a-107">PR_SWAPPED_TODO_STORE</span><span class="sxs-lookup"><span data-stu-id="5fa3a-107">PR_SWAPPED_TODO_STORE</span></span>  <br/> |
|<span data-ttu-id="5fa3a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5fa3a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5fa3a-109">0x0E2C</span><span class="sxs-lookup"><span data-stu-id="5fa3a-109">0x0E2C</span></span>  <br/> |
|<span data-ttu-id="5fa3a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5fa3a-110">Data type:</span></span>  <br/> |<span data-ttu-id="5fa3a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5fa3a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5fa3a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5fa3a-112">Area:</span></span>  <br/> |<span data-ttu-id="5fa3a-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="5fa3a-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5fa3a-114">注解</span><span class="sxs-lookup"><span data-stu-id="5fa3a-114">Remarks</span></span>

<span data-ttu-id="5fa3a-115">如果邮件草稿上设置此属性，然后它的值必须设置为**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 的邮件的属性的值。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-115">If this property is set on a draft message, then its value must be set to the value of **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property of the message.</span></span>
  
<span data-ttu-id="5fa3a-116">有关详细信息，请参阅[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)节"后传输处理已标记邮件。"</span><span class="sxs-lookup"><span data-stu-id="5fa3a-116">For more information, see [[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx) section "Post-Transmit Processing of a Flagged Message."</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5fa3a-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5fa3a-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5fa3a-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="5fa3a-118">Protocol specifications</span></span>

<span data-ttu-id="5fa3a-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fa3a-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5fa3a-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5fa3a-121">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fa3a-121">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5fa3a-122">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-122">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="5fa3a-123">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5fa3a-123">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5fa3a-124">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-124">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5fa3a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="5fa3a-125">Header files</span></span>

<span data-ttu-id="5fa3a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5fa3a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="5fa3a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="5fa3a-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5fa3a-128">Mapitags.h</span></span>
  
> <span data-ttu-id="5fa3a-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5fa3a-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5fa3a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa3a-130">See also</span></span>



[<span data-ttu-id="5fa3a-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5fa3a-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5fa3a-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fa3a-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5fa3a-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5fa3a-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5fa3a-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5fa3a-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

