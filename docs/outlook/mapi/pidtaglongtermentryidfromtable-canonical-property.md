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
ms.openlocfilehash: 574c7d305f105709aebcd41e30b034fbac1892a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425664"
---
# <a name="pidtaglongtermentryidfromtable-canonical-property"></a><span data-ttu-id="e6fbb-103">PidTagLongTermEntryIdFromTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6fbb-103">PidTagLongTermEntryIdFromTable Canonical Property</span></span>

  
  
<span data-ttu-id="e6fbb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6fbb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6fbb-105">获取项目的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e6fbb-105">Obtains the long- term entry identifier of an item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e6fbb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6fbb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6fbb-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="e6fbb-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span></span>  <br/> |
|<span data-ttu-id="e6fbb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e6fbb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e6fbb-109">0x6670</span><span class="sxs-lookup"><span data-stu-id="e6fbb-109">0x6670</span></span>  <br/> |
|<span data-ttu-id="e6fbb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6fbb-110">Data type:</span></span>  <br/> |<span data-ttu-id="e6fbb-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6fbb-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e6fbb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e6fbb-112">Area:</span></span>  <br/> |<span data-ttu-id="e6fbb-113">表属性</span><span class="sxs-lookup"><span data-stu-id="e6fbb-113">Table Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6fbb-114">备注</span><span class="sxs-lookup"><span data-stu-id="e6fbb-114">Remarks</span></span>

<span data-ttu-id="e6fbb-115">此属性可在内容表中使用，以作为长期条目标识符（而不是短期条目标识符）获取项的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e6fbb-115">This property can be used in a contents table to get the entry identifier of an item as a long-term entry identifier instead of a short-term entry identifier.</span></span> <span data-ttu-id="e6fbb-116">有关长期和短期标识符的信息，请参阅 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="e6fbb-116">For information about long-term and short-term identifiers, see **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e6fbb-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6fbb-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e6fbb-118">头文件</span><span class="sxs-lookup"><span data-stu-id="e6fbb-118">Header files</span></span>

<span data-ttu-id="e6fbb-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6fbb-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6fbb-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6fbb-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="e6fbb-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e6fbb-121">Mapitags.h</span></span>
  
> <span data-ttu-id="e6fbb-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e6fbb-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6fbb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6fbb-123">See also</span></span>



[<span data-ttu-id="e6fbb-124">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6fbb-124">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="e6fbb-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6fbb-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6fbb-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6fbb-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6fbb-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6fbb-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6fbb-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6fbb-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

