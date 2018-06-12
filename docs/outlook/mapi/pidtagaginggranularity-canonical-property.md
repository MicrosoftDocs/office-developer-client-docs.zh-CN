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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 09a79a68d7619ded9edf3ec4ac67733bdec1e32c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777317"
---
# <a name="pidtagaginggranularity-canonical-property"></a><span data-ttu-id="351e4-103">PidTagAgingGranularity 规范属性</span><span class="sxs-lookup"><span data-stu-id="351e4-103">PidTagAgingGranularity Canonical Property</span></span>

  
  
<span data-ttu-id="351e4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="351e4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="351e4-105">代表用于决定的项目之前的项目存档文件夹中保留的时间长度的时间单位。</span><span class="sxs-lookup"><span data-stu-id="351e4-105">Represents the unit of time that is used in determining the length of time an item remains in a folder before the item is archived.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="351e4-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="351e4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="351e4-107">PR_AGING_GRANULARITY</span><span class="sxs-lookup"><span data-stu-id="351e4-107">PR_AGING_GRANULARITY</span></span>  <br/> |
|<span data-ttu-id="351e4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="351e4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="351e4-109">0x36EE</span><span class="sxs-lookup"><span data-stu-id="351e4-109">0x36EE</span></span>  <br/> |
|<span data-ttu-id="351e4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="351e4-110">Data type:</span></span>  <br/> |<span data-ttu-id="351e4-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="351e4-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="351e4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="351e4-112">Area:</span></span>  <br/> |<span data-ttu-id="351e4-113">其他</span><span class="sxs-lookup"><span data-stu-id="351e4-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="351e4-114">备注</span><span class="sxs-lookup"><span data-stu-id="351e4-114">Remarks</span></span>

<span data-ttu-id="351e4-115">**PR_AGING_GRANULARITY**的可能值可以是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="351e4-115">The possible values for **PR_AGING_GRANULARITY** can be one of the following.</span></span> 
  
|<span data-ttu-id="351e4-116">**名称**</span><span class="sxs-lookup"><span data-stu-id="351e4-116">**Name**</span></span>|<span data-ttu-id="351e4-117">**值**</span><span class="sxs-lookup"><span data-stu-id="351e4-117">**Value**</span></span>|<span data-ttu-id="351e4-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="351e4-118">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="351e4-119">**AG_MONTHS**</span><span class="sxs-lookup"><span data-stu-id="351e4-119">**AG_MONTHS**</span></span> <br/> |<span data-ttu-id="351e4-120">0</span><span class="sxs-lookup"><span data-stu-id="351e4-120">0</span></span>  <br/> |<span data-ttu-id="351e4-121">**PR_AGING_PERIOD**定义中的月数。</span><span class="sxs-lookup"><span data-stu-id="351e4-121">**PR_AGING_PERIOD** is defined in number of months.</span></span>  <br/> |
|<span data-ttu-id="351e4-122">**AG_WEEKS**</span><span class="sxs-lookup"><span data-stu-id="351e4-122">**AG_WEEKS**</span></span> <br/> |<span data-ttu-id="351e4-123">1</span><span class="sxs-lookup"><span data-stu-id="351e4-123">1</span></span>  <br/> |<span data-ttu-id="351e4-124">**PR_AGING_PERIOD**定义中的周数。</span><span class="sxs-lookup"><span data-stu-id="351e4-124">**PR_AGING_PERIOD** is defined in number of weeks.</span></span>  <br/> |
|<span data-ttu-id="351e4-125">**AG_DAYS**</span><span class="sxs-lookup"><span data-stu-id="351e4-125">**AG_DAYS**</span></span> <br/> |<span data-ttu-id="351e4-126">2</span><span class="sxs-lookup"><span data-stu-id="351e4-126">2</span></span>  <br/> |<span data-ttu-id="351e4-127">**PR_AGING_PERIOD**定义中的天数。</span><span class="sxs-lookup"><span data-stu-id="351e4-127">**PR_AGING_PERIOD** is defined in number of days.</span></span>  <br/> |
   
<span data-ttu-id="351e4-128">由两个属性， [PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md)和**PR_AGING_GRANULARITY**确定的项目之前的项目存档文件夹中保留的时间长度。</span><span class="sxs-lookup"><span data-stu-id="351e4-128">The length of time that an item remains in a folder before the item is archived is determined by two properties, [PR_AGING_PERIOD](pidtagagingperiod-canonical-property.md) and **PR_AGING_GRANULARITY**.</span></span> <span data-ttu-id="351e4-129">**PR_AGING_PERIOD**表示项目之前对其进行存档的文件夹中保留的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="351e4-129">**PR_AGING_PERIOD** represents the number of time units that the item remains in the folder before it is archived.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="351e4-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="351e4-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="351e4-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="351e4-131">Protocol specifications</span></span>

<span data-ttu-id="351e4-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="351e4-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="351e4-133">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="351e4-133">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="351e4-134">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="351e4-134">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="351e4-135">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="351e4-135">Defines the basic data structures that are used in remote operations.</span></span>
    
<span data-ttu-id="351e4-136">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="351e4-136">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="351e4-137">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="351e4-137">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="351e4-138">头文件</span><span class="sxs-lookup"><span data-stu-id="351e4-138">Header files</span></span>

<span data-ttu-id="351e4-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="351e4-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="351e4-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="351e4-140">Provides data type definitions.</span></span>
    
<span data-ttu-id="351e4-141">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="351e4-141">Mapitags.h</span></span>
  
> <span data-ttu-id="351e4-142">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="351e4-142">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="351e4-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="351e4-143">See also</span></span>



[<span data-ttu-id="351e4-144">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="351e4-144">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="351e4-145">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="351e4-145">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="351e4-146">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="351e4-146">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="351e4-147">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="351e4-147">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

