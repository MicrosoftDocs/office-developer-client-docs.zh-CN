---
title: PidTagAgingGranularity 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAgingGranularity
api_type:
- HeaderDef
ms.assetid: b79ec87d-d97c-4e6c-899b-78ebf1b485a7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b4006b62758b32598a64eaa4eb333c7ce5b12605
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325583"
---
# <a name="pidtagaginggranularity-canonical-property"></a><span data-ttu-id="12916-103">PidTagAgingGranularity 规范属性</span><span class="sxs-lookup"><span data-stu-id="12916-103">PidTagAgingGranularity Canonical Property</span></span>

  
  
<span data-ttu-id="12916-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12916-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12916-105">表示用于确定项目在存档项目之前保留在该文件夹中的时间长度时使用的时间单位。</span><span class="sxs-lookup"><span data-stu-id="12916-105">Represents the unit of time that is used in determining the length of time an item remains in a folder before the item is archived.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="12916-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12916-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="12916-107">PR_AGING_GRANULARITY</span><span class="sxs-lookup"><span data-stu-id="12916-107">PR_AGING_GRANULARITY</span></span>  <br/> |
|<span data-ttu-id="12916-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="12916-108">Identifier:</span></span>  <br/> |<span data-ttu-id="12916-109">0x36EE</span><span class="sxs-lookup"><span data-stu-id="12916-109">0x36EE</span></span>  <br/> |
|<span data-ttu-id="12916-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12916-110">Data type:</span></span>  <br/> |<span data-ttu-id="12916-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="12916-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="12916-112">区域：</span><span class="sxs-lookup"><span data-stu-id="12916-112">Area:</span></span>  <br/> |<span data-ttu-id="12916-113">其他</span><span class="sxs-lookup"><span data-stu-id="12916-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12916-114">注解</span><span class="sxs-lookup"><span data-stu-id="12916-114">Remarks</span></span>

<span data-ttu-id="12916-115">**PR_AGING_GRANULARITY**的可能值可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="12916-115">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
|<span data-ttu-id="12916-116">**Name**</span><span class="sxs-lookup"><span data-stu-id="12916-116">**Name**</span></span>|<span data-ttu-id="12916-117">**Value**</span><span class="sxs-lookup"><span data-stu-id="12916-117">**Value**</span></span>|<span data-ttu-id="12916-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="12916-118">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12916-119">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="12916-119">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="12916-120">0</span><span class="sxs-lookup"><span data-stu-id="12916-120">0</span></span>  <br/> |<span data-ttu-id="12916-121">**PR_AGING_PERIOD**是在月数内定义的。</span><span class="sxs-lookup"><span data-stu-id="12916-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="12916-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="12916-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="12916-123">1</span><span class="sxs-lookup"><span data-stu-id="12916-123">1</span></span>  <br/> |<span data-ttu-id="12916-124">**PR_AGING_PERIOD**是在周数内定义的。</span><span class="sxs-lookup"><span data-stu-id="12916-124">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="12916-125">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="12916-125">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="12916-126">双面</span><span class="sxs-lookup"><span data-stu-id="12916-126">2</span></span>  <br/> |<span data-ttu-id="12916-127">**PR_AGING_PERIOD**是在天数内定义的。</span><span class="sxs-lookup"><span data-stu-id="12916-127">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="12916-128">项目在存档项目之前保留在文件夹中的时间长度由两个属性[PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)和**PR_AGING_GRANULARITY**确定。</span><span class="sxs-lookup"><span data-stu-id="12916-128">The length of time that an item remains in a folder before the item is archived is determined by two properties, [PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md) and **PR_AGING_GRANULARITY**.</span></span> <span data-ttu-id="12916-129">**PR_AGING_PERIOD**表示项目在存档前保留在文件夹中的时间单位的数量。</span><span class="sxs-lookup"><span data-stu-id="12916-129">**PR_AGING_PERIOD** represents the number of time units that the item remains in the folder before it is archived.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="12916-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="12916-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12916-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="12916-131">Protocol specifications</span></span>

<span data-ttu-id="12916-132">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12916-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12916-133">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="12916-133">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12916-134">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12916-134">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12916-135">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="12916-135">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="12916-136">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12916-136">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12916-137">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="12916-137">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12916-138">头文件</span><span class="sxs-lookup"><span data-stu-id="12916-138">Header files</span></span>

<span data-ttu-id="12916-139">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="12916-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="12916-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12916-140">Provides data type definitions.</span></span>
    
<span data-ttu-id="12916-141">Mapitags</span><span class="sxs-lookup"><span data-stu-id="12916-141">Mapitags.h</span></span>
  
> <span data-ttu-id="12916-142">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="12916-142">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12916-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12916-143">See also</span></span>



[<span data-ttu-id="12916-144">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12916-144">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12916-145">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12916-145">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12916-146">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12916-146">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12916-147">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12916-147">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

