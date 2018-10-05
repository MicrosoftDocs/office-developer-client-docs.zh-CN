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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391176"
---
# <a name="pidtagagingperiod-canonical-property"></a><span data-ttu-id="43150-103">PidTagAgingPeriod 规范属性</span><span class="sxs-lookup"><span data-stu-id="43150-103">PidTagAgingPeriod Canonical Property</span></span>

  
  
<span data-ttu-id="43150-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="43150-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="43150-105">代表用于确定的项目之前的项目存档文件夹中保留的时间长度的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="43150-105">Represents the number of time units that are used to determine the length of time that an item remains in a folder before the item is archived.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="43150-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="43150-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43150-107">PR_AGING_PERIOD</span><span class="sxs-lookup"><span data-stu-id="43150-107">PR_AGING_PERIOD</span></span>  <br/> |
|<span data-ttu-id="43150-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="43150-108">Identifier:</span></span>  <br/> |<span data-ttu-id="43150-109">0x36EC</span><span class="sxs-lookup"><span data-stu-id="43150-109">0x36EC</span></span>  <br/> |
|<span data-ttu-id="43150-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="43150-110">Property type:</span></span>  <br/> |<span data-ttu-id="43150-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="43150-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="43150-112">区域：</span><span class="sxs-lookup"><span data-stu-id="43150-112">Area:</span></span>  <br/> |<span data-ttu-id="43150-113">其他</span><span class="sxs-lookup"><span data-stu-id="43150-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43150-114">说明</span><span class="sxs-lookup"><span data-stu-id="43150-114">Remarks</span></span>

<span data-ttu-id="43150-115">由两个属性， **PR_AGING_PERIOD**和**[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)** 确定的项目之前的项目存档文件夹中保留的时间长度。</span><span class="sxs-lookup"><span data-stu-id="43150-115">The length of time that an item remains in a folder before the item is archived is determined by two properties, **PR_AGING_PERIOD** and **[PR_AGING_GRANULARITY](pidtagaginggranularity-canonical-property.md)**.</span></span> <span data-ttu-id="43150-116">**PR_AGING_GRANULARITY**表示用于**PR_AGING_PERIOD**表示，确定此时间长度时的时间单位。</span><span class="sxs-lookup"><span data-stu-id="43150-116">**PR_AGING_GRANULARITY** represents the time unit in which **PR_AGING_PERIOD** is expressed, when determining this length of time.</span></span> 
  
<span data-ttu-id="43150-117">**PR_AGING_GRANULARITY**的可能值可以是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="43150-117">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
****

|<span data-ttu-id="43150-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="43150-118">**Name**</span></span>|<span data-ttu-id="43150-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="43150-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43150-120">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="43150-120">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="43150-121">**PR_AGING_PERIOD**定义中的月数。</span><span class="sxs-lookup"><span data-stu-id="43150-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="43150-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="43150-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="43150-123">**PR_AGING_PERIOD**定义中的周数。</span><span class="sxs-lookup"><span data-stu-id="43150-123">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="43150-124">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="43150-124">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="43150-125">**PR_AGING_PERIOD**定义中的天数。</span><span class="sxs-lookup"><span data-stu-id="43150-125">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="43150-126">例如，如果项目仅后已项目的文件夹中的两周，然后**PR_AGING_GRANULARITY**文件夹存档**AG_WEEKS**和**PR_AGING_PERIOD**为 2。</span><span class="sxs-lookup"><span data-stu-id="43150-126">For example, if a folder archives an item only after the item has been in the folder for two weeks, then **PR_AGING_GRANULARITY** is **AG_WEEKS** and **PR_AGING_PERIOD** is 2.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="43150-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="43150-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43150-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="43150-128">Protocol specifications</span></span>

<span data-ttu-id="43150-129">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43150-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43150-130">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="43150-130">Provides property set definitions.</span></span>
    
<span data-ttu-id="43150-131">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43150-131">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43150-132">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="43150-132">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="43150-133">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43150-133">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43150-134">指定的属性和电子邮件消息对象允许的操作。</span><span class="sxs-lookup"><span data-stu-id="43150-134">Specifies the properties and operations that are permitted for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43150-135">头文件</span><span class="sxs-lookup"><span data-stu-id="43150-135">Header files</span></span>

<span data-ttu-id="43150-136">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43150-136">Mapidefs.h</span></span>
  
> <span data-ttu-id="43150-137">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43150-137">Provides data type definitions.</span></span>
    
<span data-ttu-id="43150-138">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="43150-138">Mapitags.h</span></span>
  
> <span data-ttu-id="43150-139">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="43150-139">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43150-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43150-140">See also</span></span>



[<span data-ttu-id="43150-141">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43150-141">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43150-142">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43150-142">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43150-143">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="43150-143">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43150-144">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43150-144">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

