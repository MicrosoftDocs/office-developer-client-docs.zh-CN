---
title: PidTagScheduleInfoMonthsBusy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: b15447d6-89aa-40ad-93fc-21fbfa5e3d0e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08f8f6e016ff08211bc10e80588ab33e83d6441b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359789"
---
# <a name="pidtagscheduleinfomonthsbusy-canonical-property"></a><span data-ttu-id="6a55d-103">PidTagScheduleInfoMonthsBusy 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a55d-103">PidTagScheduleInfoMonthsBusy Canonical Property</span></span>

  
  
<span data-ttu-id="6a55d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a55d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a55d-105">包含忙/闲邮件中存在类型为 "忙" 的忙/闲数据的月份。</span><span class="sxs-lookup"><span data-stu-id="6a55d-105">Contains the months for which free/busy data of type busy is present in the free/busy message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a55d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a55d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a55d-107">PR_SCHDINFO_MONTHS_BUSY</span><span class="sxs-lookup"><span data-stu-id="6a55d-107">PR_SCHDINFO_MONTHS_BUSY</span></span>  <br/> |
|<span data-ttu-id="6a55d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6a55d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a55d-109">0x6853</span><span class="sxs-lookup"><span data-stu-id="6a55d-109">0x6853</span></span>  <br/> |
|<span data-ttu-id="6a55d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a55d-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a55d-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="6a55d-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="6a55d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a55d-112">Area:</span></span>  <br/> |<span data-ttu-id="6a55d-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="6a55d-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a55d-114">注解</span><span class="sxs-lookup"><span data-stu-id="6a55d-114">Remarks</span></span>

<span data-ttu-id="6a55d-115">此属性的格式、计算和约束与**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 的格式、计算和约束相同, 但引用在关联的日历对象上标记为 "忙碌" 的约会。</span><span class="sxs-lookup"><span data-stu-id="6a55d-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) but refer to appointments that are marked busy on the associated calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6a55d-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a55d-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6a55d-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6a55d-117">Protocol specifications</span></span>

<span data-ttu-id="6a55d-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a55d-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a55d-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6a55d-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6a55d-120">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a55d-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a55d-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="6a55d-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6a55d-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6a55d-122">Header files</span></span>

<span data-ttu-id="6a55d-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6a55d-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a55d-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a55d-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a55d-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6a55d-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6a55d-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a55d-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a55d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a55d-127">See also</span></span>



[<span data-ttu-id="6a55d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a55d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a55d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a55d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a55d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a55d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a55d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a55d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

