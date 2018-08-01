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
ms.openlocfilehash: 9911d6cee40637a69dfaf432be0e6d42bf38bccd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777577"
---
# <a name="pidtagdiscretevalues-canonical-property"></a><span data-ttu-id="d53dc-103">PidTagDiscreteValues 规范属性</span><span class="sxs-lookup"><span data-stu-id="d53dc-103">PidTagDiscreteValues Canonical Property</span></span>

  
  
<span data-ttu-id="d53dc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d53dc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d53dc-105">包含 TRUE，则原件报表适用的通讯组列表，而不是整个列表仅为离散成员。</span><span class="sxs-lookup"><span data-stu-id="d53dc-105">Contains TRUE if a nondelivery report applies only to discrete members of a distribution list rather than the entire list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d53dc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d53dc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d53dc-107">PR_DISCRETE_VALUES</span><span class="sxs-lookup"><span data-stu-id="d53dc-107">PR_DISCRETE_VALUES</span></span>  <br/> |
|<span data-ttu-id="d53dc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d53dc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d53dc-109">0x0E0E</span><span class="sxs-lookup"><span data-stu-id="d53dc-109">0x0E0E</span></span>  <br/> |
|<span data-ttu-id="d53dc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d53dc-110">Data type:</span></span>  <br/> |<span data-ttu-id="d53dc-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d53dc-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="d53dc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d53dc-112">Area:</span></span>  <br/> |<span data-ttu-id="d53dc-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="d53dc-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d53dc-114">说明</span><span class="sxs-lookup"><span data-stu-id="d53dc-114">Remarks</span></span>

<span data-ttu-id="d53dc-115">邮件无法传递给一个或多个成员的通讯组列表时，将原件报告中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="d53dc-115">This property is used within a nondelivery report when the message could not be delivered to one or more members of a distribution list.</span></span> <span data-ttu-id="d53dc-116">其目的是限制重新传输尝试只有的单个成员和不是作为一个整体的通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d53dc-116">Its purpose is to limit retransmission attempts to only those individual members and not the distribution list as a whole.</span></span> 
  
<span data-ttu-id="d53dc-117">原件报告收件人表包含条目的所有收件人添加到其消息无法送达，以及通讯组列表中，如果有，它们属于。</span><span class="sxs-lookup"><span data-stu-id="d53dc-117">The recipient table of a nondelivery report contains entries for all recipients to whom the message could not be delivered, and also for the distribution lists, if any, to which they belong.</span></span> <span data-ttu-id="d53dc-118">传输提供程序应将此属性设置为 TRUE 为每个通讯组列表项，它应**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))、 和复制**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))， **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 从**PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))、 **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 和**PR_ORIGINAL_SEARCH_KEY** ([通讯组列表PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) 的每个成员的通讯组列表的属性。</span><span class="sxs-lookup"><span data-stu-id="d53dc-118">The transport provider should set this property to TRUE for each distribution list entry, and it should copy the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)), **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) from the distribution list to **PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md)), **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)), and **PR_ORIGINAL_SEARCH_KEY** ([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) properties for each member of that distribution list.</span></span> 
  
 <span data-ttu-id="d53dc-119">不应为通讯组列表之外任何原件报告收件人条目设置**PR_DISCRETE_VALUES** 。</span><span class="sxs-lookup"><span data-stu-id="d53dc-119">**PR_DISCRETE_VALUES** should not be set for any nondelivery report recipient entry other than a distribution list.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d53dc-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="d53dc-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d53dc-121">头文件</span><span class="sxs-lookup"><span data-stu-id="d53dc-121">Header files</span></span>

<span data-ttu-id="d53dc-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d53dc-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="d53dc-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d53dc-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="d53dc-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d53dc-124">Mapitags.h</span></span>
  
> <span data-ttu-id="d53dc-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d53dc-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d53dc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d53dc-126">See also</span></span>



[<span data-ttu-id="d53dc-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d53dc-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d53dc-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d53dc-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d53dc-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d53dc-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d53dc-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d53dc-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

