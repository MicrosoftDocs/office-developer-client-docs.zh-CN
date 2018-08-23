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
ms.openlocfilehash: c1b8c55a019ee3243de18d5e20ee4084bf6ca11f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581249"
---
# <a name="pidlidrecurring-canonical-property"></a><span data-ttu-id="a2674-103">PidLidRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2674-103">PidLidRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="a2674-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a2674-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a2674-105">指定是否定期约会消息。</span><span class="sxs-lookup"><span data-stu-id="a2674-105">Specifies whether an appointment message is recurrent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a2674-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a2674-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a2674-107">dispidRecurring</span><span class="sxs-lookup"><span data-stu-id="a2674-107">dispidRecurring</span></span>  <br/> |
|<span data-ttu-id="a2674-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="a2674-108">Property set:</span></span>  <br/> |<span data-ttu-id="a2674-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="a2674-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="a2674-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="a2674-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a2674-111">0x00008223</span><span class="sxs-lookup"><span data-stu-id="a2674-111">0x00008223</span></span>  <br/> |
|<span data-ttu-id="a2674-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a2674-112">Data type:</span></span>  <br/> |<span data-ttu-id="a2674-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a2674-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a2674-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a2674-114">Area:</span></span>  <br/> |<span data-ttu-id="a2674-115">日历</span><span class="sxs-lookup"><span data-stu-id="a2674-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a2674-116">注解</span><span class="sxs-lookup"><span data-stu-id="a2674-116">Remarks</span></span>

<span data-ttu-id="a2674-117">如果约会的定期约会，并且如果它不定期为 FALSE，则此属性为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="a2674-117">This property is TRUE if the appointment is a recurring appointment, and is FALSE if it is not recurring.</span></span>
  
<span data-ttu-id="a2674-118">此属性指定对象代表定期系列。</span><span class="sxs-lookup"><span data-stu-id="a2674-118">This property specifies whether or not the object represents a recurring series.</span></span> <span data-ttu-id="a2674-119">TRUE 表示该对象代表定期系列。</span><span class="sxs-lookup"><span data-stu-id="a2674-119">A value of TRUE indicates that the object represents a recurring series.</span></span> <span data-ttu-id="a2674-120">值为 FALSE 或不存在此属性，指示该对象表示单个实例或异常 （包括孤立实例）。</span><span class="sxs-lookup"><span data-stu-id="a2674-120">A value of FALSE, or the absence of this property, indicates that the object represents either a single instance or an exception (including an orphan instance).</span></span> <span data-ttu-id="a2674-121">请注意此属性与**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a2674-121">Note the difference between this property and the **LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a2674-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="a2674-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a2674-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="a2674-123">Protocol specifications</span></span>

<span data-ttu-id="a2674-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2674-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a2674-125">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a2674-125">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a2674-126">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2674-126">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a2674-127">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="a2674-127">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a2674-128">头文件</span><span class="sxs-lookup"><span data-stu-id="a2674-128">Header files</span></span>

<span data-ttu-id="a2674-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a2674-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="a2674-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a2674-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a2674-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2674-131">See also</span></span>



[<span data-ttu-id="a2674-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a2674-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a2674-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a2674-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a2674-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a2674-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a2674-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a2674-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

