---
title: PidTagAgingPeriod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAgingPeriod
api_type:
- HeaderDef
ms.assetid: 762020d1-4bc8-d60d-0f66-3929aae24bfb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1fd1b06bbaa10c2d7c71ee4c161fd6a980da1865
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777305"
---
# <a name="pidtagagingperiod-canonical-property"></a><span data-ttu-id="b90db-103">PidTagAgingPeriod 规范属性</span><span class="sxs-lookup"><span data-stu-id="b90db-103">PidTagAgingPeriod Canonical Property</span></span>

  
  
<span data-ttu-id="b90db-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b90db-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b90db-105">代表用于确定的项目之前的项目存档文件夹中保留的时间长度的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="b90db-105">Represents the number of time units that are used to determine the length of time that an item remains in a folder before the item is archived.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="b90db-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b90db-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b90db-107">PR_AGING_PERIOD</span><span class="sxs-lookup"><span data-stu-id="b90db-107">PR_AGING_PERIOD</span></span>  <br/> |
|<span data-ttu-id="b90db-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b90db-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b90db-109">0x36EC</span><span class="sxs-lookup"><span data-stu-id="b90db-109">0x36EC</span></span>  <br/> |
|<span data-ttu-id="b90db-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="b90db-110">Property type:</span></span>  <br/> |<span data-ttu-id="b90db-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b90db-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b90db-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b90db-112">Area:</span></span>  <br/> |<span data-ttu-id="b90db-113">其他</span><span class="sxs-lookup"><span data-stu-id="b90db-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b90db-114">说明</span><span class="sxs-lookup"><span data-stu-id="b90db-114">Remarks</span></span>

<span data-ttu-id="b90db-115">由两个属性， **PR_AGING_PERIOD**和**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)** 确定的项目之前的项目存档文件夹中保留的时间长度。</span><span class="sxs-lookup"><span data-stu-id="b90db-115">The length of time that an item remains in a folder before the item is archived is determined by two properties, **PR_AGING_PERIOD** and **[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**.</span></span> <span data-ttu-id="b90db-116">**PR_AGING_GRANULARITY**表示用于**PR_AGING_PERIOD**表示，确定此时间长度时的时间单位。</span><span class="sxs-lookup"><span data-stu-id="b90db-116">**PR_AGING_GRANULARITY** represents the time unit in which **PR_AGING_PERIOD** is expressed, when determining this length of time.</span></span> 
  
<span data-ttu-id="b90db-117">**PR_AGING_GRANULARITY**的可能值可以是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="b90db-117">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
****

|<span data-ttu-id="b90db-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="b90db-118">**Name**</span></span>|<span data-ttu-id="b90db-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b90db-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b90db-120">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="b90db-120">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="b90db-121">**PR_AGING_PERIOD**定义中的月数。</span><span class="sxs-lookup"><span data-stu-id="b90db-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="b90db-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="b90db-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="b90db-123">**PR_AGING_PERIOD**定义中的周数。</span><span class="sxs-lookup"><span data-stu-id="b90db-123">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="b90db-124">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="b90db-124">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="b90db-125">**PR_AGING_PERIOD**定义中的天数。</span><span class="sxs-lookup"><span data-stu-id="b90db-125">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="b90db-126">例如，如果项目仅后已项目的文件夹中的两周，然后**PR_AGING_GRANULARITY**文件夹存档**AG_WEEKS**和**PR_AGING_PERIOD**为 2。</span><span class="sxs-lookup"><span data-stu-id="b90db-126">For example, if a folder archives an item only after the item has been in the folder for two weeks, then **PR_AGING_GRANULARITY** is **AG_WEEKS** and **PR_AGING_PERIOD** is 2.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b90db-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="b90db-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b90db-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="b90db-128">Protocol specifications</span></span>

<span data-ttu-id="b90db-129">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b90db-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b90db-130">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="b90db-130">Provides property set definitions.</span></span>
    
<span data-ttu-id="b90db-131">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b90db-131">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b90db-132">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="b90db-132">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="b90db-133">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b90db-133">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b90db-134">指定的属性和电子邮件消息对象允许的操作。</span><span class="sxs-lookup"><span data-stu-id="b90db-134">Specifies the properties and operations that are permitted for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b90db-135">头文件</span><span class="sxs-lookup"><span data-stu-id="b90db-135">Header files</span></span>

<span data-ttu-id="b90db-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b90db-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="b90db-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b90db-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="b90db-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b90db-138">Mapitags.h</span></span>
  
> <span data-ttu-id="b90db-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b90db-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b90db-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b90db-140">See also</span></span>



[<span data-ttu-id="b90db-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b90db-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b90db-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b90db-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b90db-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b90db-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b90db-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b90db-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

