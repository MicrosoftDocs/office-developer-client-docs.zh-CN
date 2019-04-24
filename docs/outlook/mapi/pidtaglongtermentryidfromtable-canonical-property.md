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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278776"
---
# <a name="pidtaglongtermentryidfromtable-canonical-property"></a><span data-ttu-id="4d483-103">PidTagLongTermEntryIdFromTable 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d483-103">PidTagLongTermEntryIdFromTable Canonical Property</span></span>

  
  
<span data-ttu-id="4d483-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d483-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d483-105">获取项目的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="4d483-105">Obtains the long- term entry identifier of an item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d483-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4d483-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4d483-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span><span class="sxs-lookup"><span data-stu-id="4d483-107">PR_LONGTERM_ENTRYID_FROM_TABLE</span></span>  <br/> |
|<span data-ttu-id="4d483-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4d483-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4d483-109">0x6670</span><span class="sxs-lookup"><span data-stu-id="4d483-109">0x6670</span></span>  <br/> |
|<span data-ttu-id="4d483-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4d483-110">Data type:</span></span>  <br/> |<span data-ttu-id="4d483-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4d483-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4d483-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4d483-112">Area:</span></span>  <br/> |<span data-ttu-id="4d483-113">表格属性</span><span class="sxs-lookup"><span data-stu-id="4d483-113">Table Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d483-114">注解</span><span class="sxs-lookup"><span data-stu-id="4d483-114">Remarks</span></span>

<span data-ttu-id="4d483-115">可以在内容表中使用此属性将项的条目标识符作为长期条目标识符 (而不是短期条目标识符) 获取。</span><span class="sxs-lookup"><span data-stu-id="4d483-115">This property can be used in a contents table to get the entry identifier of an item as a long-term entry identifier instead of a short-term entry identifier.</span></span> <span data-ttu-id="4d483-116">有关长期和短期标识符的信息, 请参阅**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="4d483-116">For information about long-term and short-term identifiers, see **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4d483-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="4d483-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="4d483-118">头文件</span><span class="sxs-lookup"><span data-stu-id="4d483-118">Header files</span></span>

<span data-ttu-id="4d483-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4d483-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="4d483-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4d483-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="4d483-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4d483-121">Mapitags.h</span></span>
  
> <span data-ttu-id="4d483-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4d483-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4d483-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d483-123">See also</span></span>



[<span data-ttu-id="4d483-124">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d483-124">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)


[<span data-ttu-id="4d483-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4d483-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4d483-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d483-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4d483-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4d483-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4d483-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4d483-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

