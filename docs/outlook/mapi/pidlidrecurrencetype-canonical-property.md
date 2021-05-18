---
title: PidLidRecurrenceType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurrenceType
api_type:
- COM
ms.assetid: 81ad2e8a-661f-4fc7-bee4-848db3285e31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7a0ea0dfe236341815fe94fb570908d7034fc83e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315909"
---
# <a name="pidlidrecurrencetype-canonical-property"></a><span data-ttu-id="043e1-103">PidLidRecurrenceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="043e1-103">PidLidRecurrenceType Canonical Property</span></span>

  
  
<span data-ttu-id="043e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="043e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="043e1-105">指定定期系列的定期类型。</span><span class="sxs-lookup"><span data-stu-id="043e1-105">Specifies the recurrence type of the recurring series.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="043e1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="043e1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="043e1-107">dispidRecurType</span><span class="sxs-lookup"><span data-stu-id="043e1-107">dispidRecurType</span></span>  <br/> |
|<span data-ttu-id="043e1-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="043e1-108">Property set:</span></span>  <br/> |<span data-ttu-id="043e1-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="043e1-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="043e1-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="043e1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="043e1-111">0x00008231</span><span class="sxs-lookup"><span data-stu-id="043e1-111">0x00008231</span></span>  <br/> |
|<span data-ttu-id="043e1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="043e1-112">Data type:</span></span>  <br/> |<span data-ttu-id="043e1-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="043e1-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="043e1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="043e1-114">Area:</span></span>  <br/> |<span data-ttu-id="043e1-115">日历</span><span class="sxs-lookup"><span data-stu-id="043e1-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="043e1-116">备注</span><span class="sxs-lookup"><span data-stu-id="043e1-116">Remarks</span></span>

<span data-ttu-id="043e1-117">此属性通过使用下面列出的值之一来指定定期系列的定期类型。</span><span class="sxs-lookup"><span data-stu-id="043e1-117">This property specifies the recurrence type of the recurring series by using one of the values listed below.</span></span>
  
|<span data-ttu-id="043e1-118">**状态**</span><span class="sxs-lookup"><span data-stu-id="043e1-118">**Status**</span></span>|<span data-ttu-id="043e1-119">**值**</span><span class="sxs-lookup"><span data-stu-id="043e1-119">**Value**</span></span>|<span data-ttu-id="043e1-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="043e1-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="043e1-121">rectypeNone</span><span class="sxs-lookup"><span data-stu-id="043e1-121">rectypeNone</span></span>  <br/> |<span data-ttu-id="043e1-122">0</span><span class="sxs-lookup"><span data-stu-id="043e1-122">0</span></span>  <br/> |<span data-ttu-id="043e1-123">单实例约会。</span><span class="sxs-lookup"><span data-stu-id="043e1-123">A single instance appointment.</span></span>  <br/> |
|<span data-ttu-id="043e1-124">rectypeDaily</span><span class="sxs-lookup"><span data-stu-id="043e1-124">rectypeDaily</span></span>  <br/> |<span data-ttu-id="043e1-125">1</span><span class="sxs-lookup"><span data-stu-id="043e1-125">1</span></span>  <br/> |<span data-ttu-id="043e1-126">每日定期模式。</span><span class="sxs-lookup"><span data-stu-id="043e1-126">A daily recurrence pattern.</span></span>  <br/> |
|<span data-ttu-id="043e1-127">rectypeWeekly</span><span class="sxs-lookup"><span data-stu-id="043e1-127">rectypeWeekly</span></span>  <br/> |<span data-ttu-id="043e1-128">2</span><span class="sxs-lookup"><span data-stu-id="043e1-128">2</span></span>  <br/> |<span data-ttu-id="043e1-129">每周一定期模式。</span><span class="sxs-lookup"><span data-stu-id="043e1-129">A weekly recurrence pattern.</span></span>  <br/> |
|<span data-ttu-id="043e1-130">rectypeMonthly</span><span class="sxs-lookup"><span data-stu-id="043e1-130">rectypeMonthly</span></span>  <br/> |<span data-ttu-id="043e1-131">3</span><span class="sxs-lookup"><span data-stu-id="043e1-131">3</span></span>  <br/> |<span data-ttu-id="043e1-132">每月定期模式。</span><span class="sxs-lookup"><span data-stu-id="043e1-132">A monthly recurrence pattern.</span></span>  <br/> |
|<span data-ttu-id="043e1-133">rectypeYearly</span><span class="sxs-lookup"><span data-stu-id="043e1-133">rectypeYearly</span></span>  <br/> |<span data-ttu-id="043e1-134">4 </span><span class="sxs-lookup"><span data-stu-id="043e1-134">4</span></span>  <br/> |<span data-ttu-id="043e1-135">每年一定期模式。</span><span class="sxs-lookup"><span data-stu-id="043e1-135">A yearly recurrence pattern.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="043e1-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="043e1-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="043e1-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="043e1-137">Protocol specifications</span></span>

<span data-ttu-id="043e1-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="043e1-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="043e1-139">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="043e1-139">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="043e1-140">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="043e1-140">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="043e1-141">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="043e1-141">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="043e1-142">头文件</span><span class="sxs-lookup"><span data-stu-id="043e1-142">Header files</span></span>

<span data-ttu-id="043e1-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="043e1-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="043e1-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="043e1-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="043e1-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="043e1-145">See also</span></span>



[<span data-ttu-id="043e1-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="043e1-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="043e1-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="043e1-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="043e1-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="043e1-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="043e1-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="043e1-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

