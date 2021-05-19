---
title: PidLidReminderSet 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderSet
api_type:
- COM
ms.assetid: 06b7792c-1b43-4e20-9a3b-44f2664b2125
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 59379b0b1345684a491f2f7f896f2b8fc8fd54c2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335152"
---
# <a name="pidlidreminderset-canonical-property"></a><span data-ttu-id="481b6-103">PidLidReminderSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="481b6-103">PidLidReminderSet Canonical Property</span></span>

  
  
<span data-ttu-id="481b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="481b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="481b6-105">指定是否在对象上设置提醒。</span><span class="sxs-lookup"><span data-stu-id="481b6-105">Specifies whether a reminder is set on the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="481b6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="481b6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="481b6-107">dispidReminderSet</span><span class="sxs-lookup"><span data-stu-id="481b6-107">dispidReminderSet</span></span>  <br/> |
|<span data-ttu-id="481b6-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="481b6-108">Property set:</span></span>  <br/> |<span data-ttu-id="481b6-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="481b6-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="481b6-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="481b6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="481b6-111">0x00008503</span><span class="sxs-lookup"><span data-stu-id="481b6-111">0x00008503</span></span>  <br/> |
|<span data-ttu-id="481b6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="481b6-112">Data type:</span></span>  <br/> |<span data-ttu-id="481b6-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="481b6-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="481b6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="481b6-114">Area:</span></span>  <br/> |<span data-ttu-id="481b6-115">Reminder</span><span class="sxs-lookup"><span data-stu-id="481b6-115">Reminder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="481b6-116">备注</span><span class="sxs-lookup"><span data-stu-id="481b6-116">Remarks</span></span>

<span data-ttu-id="481b6-117">如果定期日历对象将此属性设置为 TRUE，则客户端可以替代此值作为例外。</span><span class="sxs-lookup"><span data-stu-id="481b6-117">If a recurring calendar object has this property set to TRUE, the client can override this value for exceptions.</span></span>
  
<span data-ttu-id="481b6-118">如果定期日历对象上的此属性为 FALSE，将禁用整个系列的提醒，包括例外。</span><span class="sxs-lookup"><span data-stu-id="481b6-118">If this property is FALSE on a recurring calendar object, reminders are disabled for the entire series, including exceptions.</span></span> <span data-ttu-id="481b6-119">对于定期任务对象，此属性不能由例外覆盖 ([请参阅 [MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) 和 [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx) 了解) 。</span><span class="sxs-lookup"><span data-stu-id="481b6-119">For recurring task objects, this property cannot be overridden by exceptions (see [[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) and [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx) for details).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="481b6-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="481b6-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="481b6-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="481b6-121">Protocol specifications</span></span>

<span data-ttu-id="481b6-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="481b6-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="481b6-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="481b6-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="481b6-124">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="481b6-124">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="481b6-125">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="481b6-125">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="481b6-126">头文件</span><span class="sxs-lookup"><span data-stu-id="481b6-126">Header files</span></span>

<span data-ttu-id="481b6-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="481b6-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="481b6-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="481b6-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="481b6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="481b6-129">See also</span></span>



[<span data-ttu-id="481b6-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="481b6-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="481b6-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="481b6-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="481b6-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="481b6-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="481b6-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="481b6-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

