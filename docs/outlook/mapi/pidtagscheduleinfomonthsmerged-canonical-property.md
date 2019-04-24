---
title: PidTagScheduleInfoMonthsMerged 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoMonthsMerged
api_type:
- COM
ms.assetid: b13b5d7b-413e-4405-8a35-0422477a9e86
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 53bc27b4ddd05b4a52328c605a6d4f673c91afd2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336475"
---
# <a name="pidtagscheduleinfomonthsmerged-canonical-property"></a><span data-ttu-id="2d1d8-103">PidTagScheduleInfoMonthsMerged 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d1d8-103">PidTagScheduleInfoMonthsMerged Canonical Property</span></span>

  
  
<span data-ttu-id="2d1d8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d1d8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d1d8-105">包含在忙/闲邮件中出现的类型为 "忙碌" 或 "外出" (OOF) 的忙/闲数据的月份列表。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-105">Contains a list of the months for which free/busy data of type busy or an out of office (OOF) message is present in the free/busy message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2d1d8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2d1d8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2d1d8-107">PR_SCHDINFO_MONTHS_MERGED</span><span class="sxs-lookup"><span data-stu-id="2d1d8-107">PR_SCHDINFO_MONTHS_MERGED</span></span>  <br/> |
|<span data-ttu-id="2d1d8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2d1d8-109">0x684F</span><span class="sxs-lookup"><span data-stu-id="2d1d8-109">0x684F</span></span>  <br/> |
|<span data-ttu-id="2d1d8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2d1d8-110">Data type:</span></span>  <br/> |<span data-ttu-id="2d1d8-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="2d1d8-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="2d1d8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2d1d8-112">Area:</span></span>  <br/> |<span data-ttu-id="2d1d8-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="2d1d8-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2d1d8-114">注解</span><span class="sxs-lookup"><span data-stu-id="2d1d8-114">Remarks</span></span>

<span data-ttu-id="2d1d8-115">此属性中不包含忙/闲类型的 "暂定" 事件。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-115">Events of free/busy type tentative are not included in this property.</span></span> <span data-ttu-id="2d1d8-116">此属性的语法/格式和约束与**PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) 的语法/格式和约束相同, 但引用在关联的日历对象上标记为 "OOF" 或 "忙" 的约会。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-116">The syntax/format and constraints of this property are the same as those of **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) but refer to appointments that are marked OOF or Busy on the associated calendar object.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2d1d8-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="2d1d8-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2d1d8-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="2d1d8-118">Protocol specifications</span></span>

<span data-ttu-id="2d1d8-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d1d8-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2d1d8-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2d1d8-121">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d1d8-121">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2d1d8-122">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2d1d8-123">头文件</span><span class="sxs-lookup"><span data-stu-id="2d1d8-123">Header files</span></span>

<span data-ttu-id="2d1d8-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2d1d8-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="2d1d8-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="2d1d8-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="2d1d8-126">Mapitags.h</span></span>
  
> <span data-ttu-id="2d1d8-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2d1d8-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2d1d8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d1d8-128">See also</span></span>



[<span data-ttu-id="2d1d8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2d1d8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2d1d8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d1d8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2d1d8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2d1d8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2d1d8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2d1d8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

