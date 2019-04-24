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
ms.openlocfilehash: d42b58bf4fd445f34064b179c873c8bc15b11b3f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360114"
---
# <a name="pidtagagingperiod-canonical-property"></a><span data-ttu-id="8c319-103">PidTagAgingPeriod 规范属性</span><span class="sxs-lookup"><span data-stu-id="8c319-103">PidTagAgingPeriod Canonical Property</span></span>

  
  
<span data-ttu-id="8c319-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8c319-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8c319-105">表示用于确定项目在存档项目之前保留在该文件夹中的时间长度的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="8c319-105">Represents the number of time units that are used to determine the length of time that an item remains in a folder before the item is archived.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="8c319-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8c319-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8c319-107">PR_AGING_PERIOD</span><span class="sxs-lookup"><span data-stu-id="8c319-107">PR_AGING_PERIOD</span></span>  <br/> |
|<span data-ttu-id="8c319-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8c319-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8c319-109">0x36EC</span><span class="sxs-lookup"><span data-stu-id="8c319-109">0x36EC</span></span>  <br/> |
|<span data-ttu-id="8c319-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="8c319-110">Property type:</span></span>  <br/> |<span data-ttu-id="8c319-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8c319-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8c319-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8c319-112">Area:</span></span>  <br/> |<span data-ttu-id="8c319-113">其他</span><span class="sxs-lookup"><span data-stu-id="8c319-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8c319-114">注解</span><span class="sxs-lookup"><span data-stu-id="8c319-114">Remarks</span></span>

<span data-ttu-id="8c319-115">项目在存档项目之前保留在文件夹中的时间长度由两个属性**PR_AGING_PERIOD**和**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)** 确定。</span><span class="sxs-lookup"><span data-stu-id="8c319-115">The length of time that an item remains in a folder before the item is archived is determined by two properties, **PR_AGING_PERIOD** and **[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**.</span></span> <span data-ttu-id="8c319-116">**PR_AGING_GRANULARITY**表示在确定此时间长度时表示**PR_AGING_PERIOD**表示的时间单位。</span><span class="sxs-lookup"><span data-stu-id="8c319-116">**PR_AGING_GRANULARITY** represents the time unit in which **PR_AGING_PERIOD** is expressed, when determining this length of time.</span></span> 
  
<span data-ttu-id="8c319-117">**PR_AGING_GRANULARITY**的可能值可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="8c319-117">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
****

|<span data-ttu-id="8c319-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="8c319-118">**Name**</span></span>|<span data-ttu-id="8c319-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8c319-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c319-120">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="8c319-120">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="8c319-121">**PR_AGING_PERIOD**是在月数内定义的。</span><span class="sxs-lookup"><span data-stu-id="8c319-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="8c319-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="8c319-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="8c319-123">**PR_AGING_PERIOD**是在周数内定义的。</span><span class="sxs-lookup"><span data-stu-id="8c319-123">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="8c319-124">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="8c319-124">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="8c319-125">**PR_AGING_PERIOD**是在天数内定义的。</span><span class="sxs-lookup"><span data-stu-id="8c319-125">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="8c319-126">例如, 如果某个文件夹只在项目在文件夹中的两周内存档项目, 则**PR_AGING_GRANULARITY**为**AG_WEEKS** , **PR_AGING_PERIOD**为2。</span><span class="sxs-lookup"><span data-stu-id="8c319-126">For example, if a folder archives an item only after the item has been in the folder for two weeks, then **PR_AGING_GRANULARITY** is **AG_WEEKS** and **PR_AGING_PERIOD** is 2.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8c319-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="8c319-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8c319-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="8c319-128">Protocol specifications</span></span>

<span data-ttu-id="8c319-129">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c319-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c319-130">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="8c319-130">Provides property set definitions.</span></span>
    
<span data-ttu-id="8c319-131">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c319-131">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c319-132">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="8c319-132">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="8c319-133">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8c319-133">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8c319-134">指定允许的电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8c319-134">Specifies the properties and operations that are permitted for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8c319-135">头文件</span><span class="sxs-lookup"><span data-stu-id="8c319-135">Header files</span></span>

<span data-ttu-id="8c319-136">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8c319-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="8c319-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8c319-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="8c319-138">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8c319-138">Mapitags.h</span></span>
  
> <span data-ttu-id="8c319-139">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8c319-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8c319-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c319-140">See also</span></span>



[<span data-ttu-id="8c319-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8c319-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8c319-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8c319-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8c319-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8c319-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8c319-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8c319-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

