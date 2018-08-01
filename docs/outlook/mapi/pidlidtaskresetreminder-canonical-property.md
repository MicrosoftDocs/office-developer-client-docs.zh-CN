---
title: PidLidTaskResetReminder 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskResetReminder
api_type:
- COM
ms.assetid: f6da69ff-a913-4a65-bb07-8ad3c5685e5e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a95fc30de7511672cb27c9dd6fbc37b96e822e77
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777109"
---
# <a name="pidlidtaskresetreminder-canonical-property"></a><span data-ttu-id="0b2d6-103">PidLidTaskResetReminder 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b2d6-103">PidLidTaskResetReminder Canonical Property</span></span>

  
  
<span data-ttu-id="0b2d6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0b2d6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0b2d6-105">指示以后的定期任务实例是否需要提醒，即使**dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) 为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-105">Indicates whether future instances of recurring tasks need reminders, even though **dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) is FALSE.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b2d6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b2d6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b2d6-107">dispidTaskResetReminder</span><span class="sxs-lookup"><span data-stu-id="0b2d6-107">dispidTaskResetReminder</span></span>  <br/> |
|<span data-ttu-id="0b2d6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="0b2d6-108">Property set:</span></span>  <br/> |<span data-ttu-id="0b2d6-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="0b2d6-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="0b2d6-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="0b2d6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0b2d6-111">0x00008107</span><span class="sxs-lookup"><span data-stu-id="0b2d6-111">0x00008107</span></span>  <br/> |
|<span data-ttu-id="0b2d6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b2d6-112">Data type:</span></span>  <br/> |<span data-ttu-id="0b2d6-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="0b2d6-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="0b2d6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0b2d6-114">Area:</span></span>  <br/> |<span data-ttu-id="0b2d6-115">Task</span><span class="sxs-lookup"><span data-stu-id="0b2d6-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b2d6-116">说明</span><span class="sxs-lookup"><span data-stu-id="0b2d6-116">Remarks</span></span>

<span data-ttu-id="0b2d6-117">任务的提醒消除，并且否则设置为 FALSE 时，此值设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-117">This value is set to TRUE when the task's reminder is dismissed, and set to FALSE otherwise.</span></span> <span data-ttu-id="0b2d6-118">如果保留未设置，则假定默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-118">If left unset, a default of FALSE is assumed.</span></span>
  
<span data-ttu-id="0b2d6-119">如指定[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)， **dispidReminderSet**属性指示是否将提醒设置任务。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-119">As specified in [[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx), the **dispidReminderSet** property indicates whether a reminder is set on the task.</span></span> <span data-ttu-id="0b2d6-120">但是，此属性仅指示一项任务的提醒的状态。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-120">However, this property only indicates the presence of a reminder on a single task.</span></span> <span data-ttu-id="0b2d6-121">不能使用它来确定定期任务的未来实例是否需要提醒。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-121">It cannot be used alone to determine whether a future instance of a recurring task needs a reminder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b2d6-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b2d6-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0b2d6-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="0b2d6-123">Protocol specifications</span></span>

<span data-ttu-id="0b2d6-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b2d6-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b2d6-125">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-125">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0b2d6-126">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b2d6-126">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b2d6-127">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-127">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="0b2d6-128">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b2d6-128">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b2d6-129">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-129">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0b2d6-130">头文件</span><span class="sxs-lookup"><span data-stu-id="0b2d6-130">Header files</span></span>

<span data-ttu-id="0b2d6-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0b2d6-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b2d6-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b2d6-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b2d6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b2d6-133">See also</span></span>



[<span data-ttu-id="0b2d6-134">PidLidReminderSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b2d6-134">PidLidReminderSet Canonical Property</span></span>](pidlidreminderset-canonical-property.md)


[<span data-ttu-id="0b2d6-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b2d6-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b2d6-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b2d6-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b2d6-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b2d6-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b2d6-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b2d6-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

