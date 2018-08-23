---
title: PidTagLongTermEntryIdFromTable 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLongTermEntryIdFromTable
api_type:
- HeaderDef
ms.assetid: d9457fea-4b1e-4cf6-9c4b-14c98fbec2a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddec060af73d61a4a39c59b35f0442d6b9b1db66
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590314"
---
# <a name="pidtaglongtermentryidfromtable-canonical-property"></a><span data-ttu-id="d74cc-103">PidTagLongTermEntryIdFromTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-103">PidTagLongTermEntryIdFromTable Canonical Property</span></span>

  
  
<span data-ttu-id="d74cc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d74cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d74cc-105">获取项目的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="d74cc-105">Obtains the long- term entry identifier of an item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d74cc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d74cc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d74cc-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="d74cc-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span></span>  <br/> |
|<span data-ttu-id="d74cc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d74cc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d74cc-109">0x6670</span><span class="sxs-lookup"><span data-stu-id="d74cc-109">0x6670</span></span>  <br/> |
|<span data-ttu-id="d74cc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d74cc-110">Data type:</span></span>  <br/> |<span data-ttu-id="d74cc-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d74cc-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d74cc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d74cc-112">Area:</span></span>  <br/> |<span data-ttu-id="d74cc-113">表格属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-113">Table Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d74cc-114">注解</span><span class="sxs-lookup"><span data-stu-id="d74cc-114">Remarks</span></span>

<span data-ttu-id="d74cc-115">此属性可以用于内容表中而不是短期的项标识符的长期条目标识符获取项目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="d74cc-115">This property can be used in a contents table to get the entry identifier of an item as a long-term entry identifier instead of a short-term entry identifier.</span></span> <span data-ttu-id="d74cc-116">有关长期和短期标识符信息，请参阅**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="d74cc-116">For information about long-term and short-term identifiers, see **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d74cc-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d74cc-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d74cc-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d74cc-118">Header files</span></span>

<span data-ttu-id="d74cc-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d74cc-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d74cc-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d74cc-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d74cc-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d74cc-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d74cc-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d74cc-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d74cc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d74cc-123">See also</span></span>



[<span data-ttu-id="d74cc-124">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-124">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="d74cc-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d74cc-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d74cc-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d74cc-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d74cc-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d74cc-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

