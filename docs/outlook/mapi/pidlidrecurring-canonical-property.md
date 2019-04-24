---
title: PidLidRecurring 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurring
api_type:
- COM
ms.assetid: 3d39a053-277f-4d59-ab2e-cee81710f2ab
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85e78695a7c4fca5a1e5cd28b0254d4559be0c13
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315916"
---
# <a name="pidlidrecurring-canonical-property"></a><span data-ttu-id="daaeb-103">PidLidRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="daaeb-103">PidLidRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="daaeb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="daaeb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="daaeb-105">指定是否反复出现约会邮件。</span><span class="sxs-lookup"><span data-stu-id="daaeb-105">Specifies whether an appointment message is recurrent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="daaeb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="daaeb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="daaeb-107">dispidRecurring</span><span class="sxs-lookup"><span data-stu-id="daaeb-107">dispidRecurring</span></span>  <br/> |
|<span data-ttu-id="daaeb-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="daaeb-108">Property set:</span></span>  <br/> |<span data-ttu-id="daaeb-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="daaeb-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="daaeb-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="daaeb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="daaeb-111">0x00008223</span><span class="sxs-lookup"><span data-stu-id="daaeb-111">0x00008223</span></span>  <br/> |
|<span data-ttu-id="daaeb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="daaeb-112">Data type:</span></span>  <br/> |<span data-ttu-id="daaeb-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="daaeb-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="daaeb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="daaeb-114">Area:</span></span>  <br/> |<span data-ttu-id="daaeb-115">日历</span><span class="sxs-lookup"><span data-stu-id="daaeb-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="daaeb-116">注解</span><span class="sxs-lookup"><span data-stu-id="daaeb-116">Remarks</span></span>

<span data-ttu-id="daaeb-117">如果约会是定期约会, 则此属性为 TRUE, 如果不是定期约会, 则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="daaeb-117">This property is TRUE if the appointment is a recurring appointment, and is FALSE if it is not recurring.</span></span>
  
<span data-ttu-id="daaeb-118">此属性指定对象是否表示定期系列。</span><span class="sxs-lookup"><span data-stu-id="daaeb-118">This property specifies whether or not the object represents a recurring series.</span></span> <span data-ttu-id="daaeb-119">如果值为 TRUE, 则表示对象表示定期系列。</span><span class="sxs-lookup"><span data-stu-id="daaeb-119">A value of TRUE indicates that the object represents a recurring series.</span></span> <span data-ttu-id="daaeb-120">值为 FALSE, 或缺少此属性时, 表示对象表示单个实例或异常 (包括孤立实例)。</span><span class="sxs-lookup"><span data-stu-id="daaeb-120">A value of FALSE, or the absence of this property, indicates that the object represents either a single instance or an exception (including an orphan instance).</span></span> <span data-ttu-id="daaeb-121">请注意此属性与**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性之间的差异。</span><span class="sxs-lookup"><span data-stu-id="daaeb-121">Note the difference between this property and the **LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="daaeb-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="daaeb-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="daaeb-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="daaeb-123">Protocol specifications</span></span>

<span data-ttu-id="daaeb-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="daaeb-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="daaeb-125">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="daaeb-125">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="daaeb-126">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="daaeb-126">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="daaeb-127">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="daaeb-127">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="daaeb-128">头文件</span><span class="sxs-lookup"><span data-stu-id="daaeb-128">Header files</span></span>

<span data-ttu-id="daaeb-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="daaeb-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="daaeb-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="daaeb-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="daaeb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daaeb-131">See also</span></span>



[<span data-ttu-id="daaeb-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="daaeb-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="daaeb-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="daaeb-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="daaeb-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="daaeb-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="daaeb-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="daaeb-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

