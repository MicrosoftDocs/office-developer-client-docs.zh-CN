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
# <a name="pidtagagingperiod-canonical-property"></a><span data-ttu-id="2e3a2-103">PidTagAgingPeriod 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e3a2-103">PidTagAgingPeriod Canonical Property</span></span>

  
  
<span data-ttu-id="2e3a2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e3a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e3a2-105">表示用于确定项目在存档前保留在文件夹中的时间长度的时间单位。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-105">Represents the number of time units that are used to determine the length of time that an item remains in a folder before the item is archived.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="2e3a2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e3a2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e3a2-107">PR_AGING_PERIOD</span><span class="sxs-lookup"><span data-stu-id="2e3a2-107">PR_AGING_PERIOD</span></span>  <br/> |
|<span data-ttu-id="2e3a2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2e3a2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2e3a2-109">0x36EC</span><span class="sxs-lookup"><span data-stu-id="2e3a2-109">0x36EC</span></span>  <br/> |
|<span data-ttu-id="2e3a2-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="2e3a2-110">Property type:</span></span>  <br/> |<span data-ttu-id="2e3a2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2e3a2-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2e3a2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2e3a2-112">Area:</span></span>  <br/> |<span data-ttu-id="2e3a2-113">其他</span><span class="sxs-lookup"><span data-stu-id="2e3a2-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e3a2-114">备注</span><span class="sxs-lookup"><span data-stu-id="2e3a2-114">Remarks</span></span>

<span data-ttu-id="2e3a2-115">项目在存档项目之前保留在文件夹中的时间长度由两个属性决定，即 PR_AGING_PERIOD **和\*\*\*\*[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-115">The length of time that an item remains in a folder before the item is archived is determined by two properties, **PR_AGING_PERIOD** and **[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**.</span></span> <span data-ttu-id="2e3a2-116">**PR_AGING_GRANULARITY** 表示确定此时间长度 **PR_AGING_PERIOD** 表示时间单位。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-116">**PR_AGING_GRANULARITY** represents the time unit in which **PR_AGING_PERIOD** is expressed, when determining this length of time.</span></span> 
  
<span data-ttu-id="2e3a2-117">此参数 **PR_AGING_GRANULARITY** 可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-117">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
****

|<span data-ttu-id="2e3a2-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="2e3a2-118">**Name**</span></span>|<span data-ttu-id="2e3a2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e3a2-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e3a2-120">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="2e3a2-120">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="2e3a2-121">**PR_AGING_PERIOD** 以月数定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="2e3a2-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="2e3a2-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="2e3a2-123">**PR_AGING_PERIOD** 以周数定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-123">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="2e3a2-124">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="2e3a2-124">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="2e3a2-125">**PR_AGING_PERIOD** 天数进行定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-125">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="2e3a2-126">例如，如果某个文件夹仅在项目在文件夹中保存了两周后存档该项目，则PR_AGING_GRANULARITY为 AG_WEEKS，PR_AGING_PERIOD为 2。 </span><span class="sxs-lookup"><span data-stu-id="2e3a2-126">For example, if a folder archives an item only after the item has been in the folder for two weeks, then **PR_AGING_GRANULARITY** is **AG_WEEKS** and **PR_AGING_PERIOD** is 2.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2e3a2-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e3a2-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e3a2-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e3a2-128">Protocol specifications</span></span>

<span data-ttu-id="2e3a2-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e3a2-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e3a2-130">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-130">Provides property set definitions.</span></span>
    
<span data-ttu-id="2e3a2-131">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e3a2-131">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e3a2-132">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-132">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="2e3a2-133">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e3a2-133">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e3a2-134">指定允许电子邮件对象使用的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-134">Specifies the properties and operations that are permitted for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e3a2-135">头文件</span><span class="sxs-lookup"><span data-stu-id="2e3a2-135">Header files</span></span>

<span data-ttu-id="2e3a2-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e3a2-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e3a2-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="2e3a2-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2e3a2-138">Mapitags.h</span></span>
  
> <span data-ttu-id="2e3a2-139">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2e3a2-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e3a2-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e3a2-140">See also</span></span>



[<span data-ttu-id="2e3a2-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e3a2-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e3a2-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e3a2-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e3a2-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e3a2-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e3a2-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e3a2-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

