---
title: PidTagDiscreteValues 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDiscreteValues
api_type:
- HeaderDef
ms.assetid: 958f3cf7-953a-43f4-9102-ad35edf5e813
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d6974302e3413db3590abbbd3e6567976c6ac72
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404839"
---
# <a name="pidtagdiscretevalues-canonical-property"></a><span data-ttu-id="1b1f4-103">PidTagDiscreteValues 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b1f4-103">PidTagDiscreteValues Canonical Property</span></span>

  
  
<span data-ttu-id="1b1f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b1f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b1f4-105">如果未送达报告仅适用于通讯组列表的离散成员，而不是整个列表，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-105">Contains TRUE if a nondelivery report applies only to discrete members of a distribution list rather than the entire list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1b1f4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1b1f4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1b1f4-107">PR_DISCRETE_VALUES</span><span class="sxs-lookup"><span data-stu-id="1b1f4-107">PR_DISCRETE_VALUES</span></span>  <br/> |
|<span data-ttu-id="1b1f4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1b1f4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1b1f4-109">0x0E0E</span><span class="sxs-lookup"><span data-stu-id="1b1f4-109">0x0E0E</span></span>  <br/> |
|<span data-ttu-id="1b1f4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1b1f4-110">Data type:</span></span>  <br/> |<span data-ttu-id="1b1f4-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1b1f4-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="1b1f4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1b1f4-112">Area:</span></span>  <br/> |<span data-ttu-id="1b1f4-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="1b1f4-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1b1f4-114">备注</span><span class="sxs-lookup"><span data-stu-id="1b1f4-114">Remarks</span></span>

<span data-ttu-id="1b1f4-115">当邮件无法传递到通讯组列表的一个或多个成员时，将在未送达报告中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-115">This property is used within a nondelivery report when the message could not be delivered to one or more members of a distribution list.</span></span> <span data-ttu-id="1b1f4-116">它的目的是将重新传输尝试限制为仅这些单个成员，而不是整个通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-116">Its purpose is to limit retransmission attempts to only those individual members and not the distribution list as a whole.</span></span> 
  
<span data-ttu-id="1b1f4-117">未送达报告的收件人表包含邮件无法传递到的所有收件人的条目，以及这些收件人所属的通讯组列表（如果有）的条目。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-117">The recipient table of a nondelivery report contains entries for all recipients to whom the message could not be delivered, and also for the distribution lists, if any, to which they belong.</span></span> <span data-ttu-id="1b1f4-118">传输提供程序应针对每个通讯组列表条目将此属性设置为 TRUE，并且应复制 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 、PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) ， 和 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 从通讯组列表到 **PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md)) 、PR_ORIGINAL_ENTRYID ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 以及该通讯组列表每个成员 PR_ORIGINAL_SEARCH_KEY **(** [PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="1b1f4-118">The transport provider should set this property to TRUE for each distribution list entry, and it should copy the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)), **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) from the distribution list to **PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md)), **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)), and **PR_ORIGINAL_SEARCH_KEY** ([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) properties for each member of that distribution list.</span></span> 
  
 <span data-ttu-id="1b1f4-119">**PR_DISCRETE_VALUES** 通讯组列表外的任何未送达报告收件人条目设置邮件。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-119">**PR_DISCRETE_VALUES** should not be set for any nondelivery report recipient entry other than a distribution list.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1b1f4-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="1b1f4-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1b1f4-121">头文件</span><span class="sxs-lookup"><span data-stu-id="1b1f4-121">Header files</span></span>

<span data-ttu-id="1b1f4-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1b1f4-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="1b1f4-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="1b1f4-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1b1f4-124">Mapitags.h</span></span>
  
> <span data-ttu-id="1b1f4-125">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1b1f4-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1b1f4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b1f4-126">See also</span></span>



[<span data-ttu-id="1b1f4-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1b1f4-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1b1f4-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b1f4-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1b1f4-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1b1f4-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1b1f4-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1b1f4-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

