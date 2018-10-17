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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399478"
---
# <a name="pidlidrecurring-canonical-property"></a><span data-ttu-id="928c8-103">PidLidRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="928c8-103">PidLidRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="928c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="928c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="928c8-105">指定是否定期约会消息。</span><span class="sxs-lookup"><span data-stu-id="928c8-105">Specifies whether an appointment message is recurrent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="928c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="928c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="928c8-107">dispidRecurring</span><span class="sxs-lookup"><span data-stu-id="928c8-107">dispidRecurring</span></span>  <br/> |
|<span data-ttu-id="928c8-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="928c8-108">Property set:</span></span>  <br/> |<span data-ttu-id="928c8-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="928c8-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="928c8-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="928c8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="928c8-111">0x00008223</span><span class="sxs-lookup"><span data-stu-id="928c8-111">0x00008223</span></span>  <br/> |
|<span data-ttu-id="928c8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="928c8-112">Data type:</span></span>  <br/> |<span data-ttu-id="928c8-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="928c8-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="928c8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="928c8-114">Area:</span></span>  <br/> |<span data-ttu-id="928c8-115">日历</span><span class="sxs-lookup"><span data-stu-id="928c8-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="928c8-116">说明</span><span class="sxs-lookup"><span data-stu-id="928c8-116">Remarks</span></span>

<span data-ttu-id="928c8-117">如果约会的定期约会，并且如果它不定期为 FALSE，则此属性为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="928c8-117">This property is TRUE if the appointment is a recurring appointment, and is FALSE if it is not recurring.</span></span>
  
<span data-ttu-id="928c8-118">此属性指定对象代表定期系列。</span><span class="sxs-lookup"><span data-stu-id="928c8-118">This property specifies whether or not the object represents a recurring series.</span></span> <span data-ttu-id="928c8-119">TRUE 表示该对象代表定期系列。</span><span class="sxs-lookup"><span data-stu-id="928c8-119">A value of TRUE indicates that the object represents a recurring series.</span></span> <span data-ttu-id="928c8-120">值为 FALSE 或不存在此属性，指示该对象表示单个实例或异常 （包括孤立实例）。</span><span class="sxs-lookup"><span data-stu-id="928c8-120">A value of FALSE, or the absence of this property, indicates that the object represents either a single instance or an exception (including an orphan instance).</span></span> <span data-ttu-id="928c8-121">请注意此属性与**LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) 属性之间的差异。</span><span class="sxs-lookup"><span data-stu-id="928c8-121">Note the difference between this property and the **LID_IS_RECURRING** ([PidLidIsRecurring](pidlidisrecurring-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="928c8-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="928c8-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="928c8-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="928c8-123">Protocol specifications</span></span>

<span data-ttu-id="928c8-124">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="928c8-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="928c8-125">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="928c8-125">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="928c8-126">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="928c8-126">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="928c8-127">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="928c8-127">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="928c8-128">头文件</span><span class="sxs-lookup"><span data-stu-id="928c8-128">Header files</span></span>

<span data-ttu-id="928c8-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="928c8-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="928c8-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="928c8-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="928c8-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="928c8-131">See also</span></span>



[<span data-ttu-id="928c8-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="928c8-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="928c8-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="928c8-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="928c8-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="928c8-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="928c8-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="928c8-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
