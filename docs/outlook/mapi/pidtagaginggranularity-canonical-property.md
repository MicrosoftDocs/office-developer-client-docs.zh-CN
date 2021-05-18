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
# <a name="pidtagaginggranularity-canonical-property"></a><span data-ttu-id="1b7a3-103">PidTagAgingGranularity 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b7a3-103">PidTagAgingGranularity Canonical Property</span></span>

  
  
<span data-ttu-id="1b7a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b7a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b7a3-105">表示用于确定项目在存档前保留在文件夹中的时间长度的时间单位。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-105">Represents the unit of time that is used in determining the length of time an item remains in a folder before the item is archived.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1b7a3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1b7a3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1b7a3-107">PR_AGING_GRANULARITY</span><span class="sxs-lookup"><span data-stu-id="1b7a3-107">PR_AGING_GRANULARITY</span></span>  <br/> |
|<span data-ttu-id="1b7a3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1b7a3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1b7a3-109">0x36EE</span><span class="sxs-lookup"><span data-stu-id="1b7a3-109">0x36EE</span></span>  <br/> |
|<span data-ttu-id="1b7a3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1b7a3-110">Data type:</span></span>  <br/> |<span data-ttu-id="1b7a3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1b7a3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1b7a3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1b7a3-112">Area:</span></span>  <br/> |<span data-ttu-id="1b7a3-113">其他</span><span class="sxs-lookup"><span data-stu-id="1b7a3-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1b7a3-114">备注</span><span class="sxs-lookup"><span data-stu-id="1b7a3-114">Remarks</span></span>

<span data-ttu-id="1b7a3-115">此参数 **PR_AGING_GRANULARITY** 可以是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-115">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
|<span data-ttu-id="1b7a3-116">**名称**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-116">**Name**</span></span>|<span data-ttu-id="1b7a3-117">**值**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-117">**Value**</span></span>|<span data-ttu-id="1b7a3-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-118">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1b7a3-119">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-119">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="1b7a3-120">0</span><span class="sxs-lookup"><span data-stu-id="1b7a3-120">0</span></span>  <br/> |<span data-ttu-id="1b7a3-121">**PR_AGING_PERIOD** 以月数定义。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="1b7a3-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="1b7a3-123">1</span><span class="sxs-lookup"><span data-stu-id="1b7a3-123">1</span></span>  <br/> |<span data-ttu-id="1b7a3-124">**PR_AGING_PERIOD** 以周数定义。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-124">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="1b7a3-125">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="1b7a3-125">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="1b7a3-126">2</span><span class="sxs-lookup"><span data-stu-id="1b7a3-126">2</span></span>  <br/> |<span data-ttu-id="1b7a3-127">**PR_AGING_PERIOD** 天数进行定义。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-127">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="1b7a3-128">项目在存档项目之前保留在文件夹中的时间长度由两个属性决定，即 PR_AGING_PERIOD [和](pidtagagingperiod-canonical-property.md)**PR_AGING_GRANULARITY**。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-128">The length of time that an item remains in a folder before the item is archived is determined by two properties, [PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md) and **PR_AGING_GRANULARITY**.</span></span> <span data-ttu-id="1b7a3-129">**PR_AGING_PERIOD** 表示项目在存档之前保留在文件夹中的时间单位。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-129">**PR_AGING_PERIOD** represents the number of time units that the item remains in the folder before it is archived.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1b7a3-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="1b7a3-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1b7a3-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="1b7a3-131">Protocol specifications</span></span>

<span data-ttu-id="1b7a3-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b7a3-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b7a3-133">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-133">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1b7a3-134">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b7a3-134">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b7a3-135">定义远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-135">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="1b7a3-136">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b7a3-136">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b7a3-137">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-137">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1b7a3-138">头文件</span><span class="sxs-lookup"><span data-stu-id="1b7a3-138">Header files</span></span>

<span data-ttu-id="1b7a3-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1b7a3-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="1b7a3-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-140">Provides data type definitions.</span></span>
    
<span data-ttu-id="1b7a3-141">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1b7a3-141">Mapitags.h</span></span>
  
> <span data-ttu-id="1b7a3-142">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1b7a3-142">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1b7a3-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b7a3-143">See also</span></span>



[<span data-ttu-id="1b7a3-144">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1b7a3-144">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1b7a3-145">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b7a3-145">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1b7a3-146">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1b7a3-146">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1b7a3-147">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1b7a3-147">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

