---
title: PidLidReminderDelta 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderDelta
api_type:
- COM
ms.assetid: 011d73d0-8b38-4a4e-a56f-92dec451946a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 91cad169157b2dd0ff279e88b69db149c4c7df89
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590748"
---
# <a name="pidlidreminderdelta-canonical-property"></a><span data-ttu-id="afb5b-103">PidLidReminderDelta 规范属性</span><span class="sxs-lookup"><span data-stu-id="afb5b-103">PidLidReminderDelta Canonical Property</span></span>

  
  
<span data-ttu-id="afb5b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="afb5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="afb5b-105">指定以分钟为单位，当提醒前变为过期的时间和开始时间的日历对象之间的间隔。</span><span class="sxs-lookup"><span data-stu-id="afb5b-105">Specifies the interval, in minutes, between the time when the reminder first becomes overdue and the start time of the calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="afb5b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="afb5b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="afb5b-107">dispidReminderDelta</span><span class="sxs-lookup"><span data-stu-id="afb5b-107">dispidReminderDelta</span></span>  <br/> |
|<span data-ttu-id="afb5b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="afb5b-108">Property set:</span></span>  <br/> |<span data-ttu-id="afb5b-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="afb5b-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="afb5b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="afb5b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="afb5b-111">0x00008501</span><span class="sxs-lookup"><span data-stu-id="afb5b-111">0x00008501</span></span>  <br/> |
|<span data-ttu-id="afb5b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="afb5b-112">Data type:</span></span>  <br/> |<span data-ttu-id="afb5b-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="afb5b-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="afb5b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="afb5b-114">Area:</span></span>  <br/> |<span data-ttu-id="afb5b-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="afb5b-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="afb5b-116">注解</span><span class="sxs-lookup"><span data-stu-id="afb5b-116">Remarks</span></span>

<span data-ttu-id="afb5b-117">此属性必须设置对日历对象。</span><span class="sxs-lookup"><span data-stu-id="afb5b-117">This property must be set on calendar objects.</span></span> <span data-ttu-id="afb5b-118">对于所有非日历对象，此属性应设置为"0x00000000"，并将被忽略。</span><span class="sxs-lookup"><span data-stu-id="afb5b-118">For all non-calendar objects, this property should be set to "0x00000000" and is ignored.</span></span> <span data-ttu-id="afb5b-119">时的定期 calendar 对象的一个实例消除提醒下, 一实例的信号时间的计算中使用此属性的值。</span><span class="sxs-lookup"><span data-stu-id="afb5b-119">When a reminder is dismissed for one instance of a recurring calendar object, the value of this property is used in the calculation of the signal time for the next instance.</span></span> <span data-ttu-id="afb5b-120">有关创建日历对象的详细信息，请参阅[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="afb5b-120">See [[MS- OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) for details about calendar object creation.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="afb5b-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="afb5b-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="afb5b-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="afb5b-122">Protocol specifications</span></span>

<span data-ttu-id="afb5b-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="afb5b-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="afb5b-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="afb5b-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="afb5b-125">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="afb5b-125">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="afb5b-126">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="afb5b-126">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="afb5b-127">头文件</span><span class="sxs-lookup"><span data-stu-id="afb5b-127">Header files</span></span>

<span data-ttu-id="afb5b-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="afb5b-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="afb5b-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="afb5b-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="afb5b-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afb5b-130">See also</span></span>



[<span data-ttu-id="afb5b-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="afb5b-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="afb5b-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="afb5b-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="afb5b-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="afb5b-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="afb5b-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="afb5b-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

