---
title: PidTagScheduleInfoFreeBusyBusy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyBusy
api_type:
- COM
ms.assetid: 84d9c5b5-e734-4c07-b4cc-1d7b13c1ed19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fbf0d8b80fdb48e44480b2739a71aec43b88a05
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338652"
---
# <a name="pidtagscheduleinfofreebusybusy-canonical-property"></a><span data-ttu-id="a6c28-103">PidTagScheduleInfoFreeBusyBusy 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6c28-103">PidTagScheduleInfoFreeBusyBusy Canonical Property</span></span>

  
  
<span data-ttu-id="a6c28-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6c28-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6c28-105">包含状态繁忙的时间块。</span><span class="sxs-lookup"><span data-stu-id="a6c28-105">Contains the blocks of time for which the status is busy.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a6c28-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a6c28-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a6c28-107">PR_SCHDINFO_FREEBUSY_BUSY</span><span class="sxs-lookup"><span data-stu-id="a6c28-107">PR_SCHDINFO_FREEBUSY_BUSY</span></span>  <br/> |
|<span data-ttu-id="a6c28-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a6c28-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a6c28-109">0x6854</span><span class="sxs-lookup"><span data-stu-id="a6c28-109">0x6854</span></span>  <br/> |
|<span data-ttu-id="a6c28-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a6c28-110">Data type:</span></span>  <br/> |<span data-ttu-id="a6c28-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="a6c28-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="a6c28-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a6c28-112">Area:</span></span>  <br/> |<span data-ttu-id="a6c28-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="a6c28-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a6c28-114">备注</span><span class="sxs-lookup"><span data-stu-id="a6c28-114">Remarks</span></span>

<span data-ttu-id="a6c28-115">此属性的格式、计算和约束与 **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) 相同，但指在关联的日历对象上标记为忙碌的约会。</span><span class="sxs-lookup"><span data-stu-id="a6c28-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_FREEBUSY_TENTATIVE** ([PidTagScheduleInfoFreeBusyTentative](pidtagscheduleinfofreebusytentative-canonical-property.md)) but refer to appointments that are marked busy on the associated calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a6c28-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="a6c28-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a6c28-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="a6c28-117">Protocol specifications</span></span>

<span data-ttu-id="a6c28-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6c28-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6c28-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="a6c28-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a6c28-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6c28-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6c28-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="a6c28-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a6c28-122">头文件</span><span class="sxs-lookup"><span data-stu-id="a6c28-122">Header files</span></span>

<span data-ttu-id="a6c28-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a6c28-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="a6c28-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a6c28-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="a6c28-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a6c28-125">Mapitags.h</span></span>
  
> <span data-ttu-id="a6c28-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a6c28-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6c28-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c28-127">See also</span></span>



[<span data-ttu-id="a6c28-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a6c28-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a6c28-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6c28-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a6c28-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a6c28-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a6c28-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a6c28-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

