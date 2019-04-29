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
# <a name="pidtagdiscretevalues-canonical-property"></a><span data-ttu-id="66333-103">PidTagDiscreteValues 规范属性</span><span class="sxs-lookup"><span data-stu-id="66333-103">PidTagDiscreteValues Canonical Property</span></span>

  
  
<span data-ttu-id="66333-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66333-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66333-105">如果 nondelivery 报表仅适用于通讯组列表的离散成员而不是整个列表, 则该参数包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="66333-105">Contains TRUE if a nondelivery report applies only to discrete members of a distribution list rather than the entire list.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="66333-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="66333-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="66333-107">PR_DISCRETE_VALUES</span><span class="sxs-lookup"><span data-stu-id="66333-107">PR_DISCRETE_VALUES</span></span>  <br/> |
|<span data-ttu-id="66333-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="66333-108">Identifier:</span></span>  <br/> |<span data-ttu-id="66333-109">0x0E0E</span><span class="sxs-lookup"><span data-stu-id="66333-109">0x0E0E</span></span>  <br/> |
|<span data-ttu-id="66333-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="66333-110">Data type:</span></span>  <br/> |<span data-ttu-id="66333-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="66333-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="66333-112">区域：</span><span class="sxs-lookup"><span data-stu-id="66333-112">Area:</span></span>  <br/> |<span data-ttu-id="66333-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="66333-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66333-114">说明</span><span class="sxs-lookup"><span data-stu-id="66333-114">Remarks</span></span>

<span data-ttu-id="66333-115">当无法将邮件传递给通讯组列表的一个或多个成员时, 将在 nondelivery 报告中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="66333-115">This property is used within a nondelivery report when the message could not be delivered to one or more members of a distribution list.</span></span> <span data-ttu-id="66333-116">其目的是将重新传输尝试限制为仅对单个成员进行, 而不是将通讯组列表限制为一个整体。</span><span class="sxs-lookup"><span data-stu-id="66333-116">Its purpose is to limit retransmission attempts to only those individual members and not the distribution list as a whole.</span></span> 
  
<span data-ttu-id="66333-117">nondelivery 报表的 "收件人" 表包含邮件无法传递到的所有收件人的条目, 以及它们所属的通讯组列表 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="66333-117">The recipient table of a nondelivery report contains entries for all recipients to whom the message could not be delivered, and also for the distribution lists, if any, to which they belong.</span></span> <span data-ttu-id="66333-118">对于每个通讯组列表条目, 传输提供程序应将此属性设置为 TRUE, 并且应复制**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))、 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 从通讯组列表到**PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))、 **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)) 和**PR_ORIGINAL_SEARCH_KEY** ([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) 属性分配给该通讯组列表中的每个成员。</span><span class="sxs-lookup"><span data-stu-id="66333-118">The transport provider should set this property to TRUE for each distribution list entry, and it should copy the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)), **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) from the distribution list to **PR_ORIGINAL_DISPLAY_NAME** ([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md)), **PR_ORIGINAL_ENTRYID** ([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md)), and **PR_ORIGINAL_SEARCH_KEY** ([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md)) properties for each member of that distribution list.</span></span> 
  
 <span data-ttu-id="66333-119">不应为除通讯组列表之外的任何 nondelivery 报告收件人条目设置**PR_DISCRETE_VALUES** 。</span><span class="sxs-lookup"><span data-stu-id="66333-119">**PR_DISCRETE_VALUES** should not be set for any nondelivery report recipient entry other than a distribution list.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="66333-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="66333-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="66333-121">头文件</span><span class="sxs-lookup"><span data-stu-id="66333-121">Header files</span></span>

<span data-ttu-id="66333-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="66333-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="66333-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="66333-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="66333-124">Mapitags</span><span class="sxs-lookup"><span data-stu-id="66333-124">Mapitags.h</span></span>
  
> <span data-ttu-id="66333-125">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="66333-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66333-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66333-126">See also</span></span>



[<span data-ttu-id="66333-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="66333-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="66333-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="66333-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="66333-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="66333-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="66333-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66333-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

