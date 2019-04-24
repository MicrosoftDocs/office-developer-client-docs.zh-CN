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
ms.openlocfilehash: 9a438fb2b1862d44905a63fda3e5f68b7878cd99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316616"
---
# <a name="pidlidtaskresetreminder-canonical-property"></a><span data-ttu-id="d7e6f-103">PidLidTaskResetReminder 规范属性</span><span class="sxs-lookup"><span data-stu-id="d7e6f-103">PidLidTaskResetReminder Canonical Property</span></span>

  
  
<span data-ttu-id="d7e6f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7e6f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7e6f-105">指示未来的周期性任务实例是否需要提醒, 即使**dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) 为 FALSE 也是如此。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-105">Indicates whether future instances of recurring tasks need reminders, even though **dispidReminderSet** ([PidLidReminderSet](pidlidreminderset-canonical-property.md)) is FALSE.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d7e6f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d7e6f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d7e6f-107">dispidTaskResetReminder</span><span class="sxs-lookup"><span data-stu-id="d7e6f-107">dispidTaskResetReminder</span></span>  <br/> |
|<span data-ttu-id="d7e6f-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="d7e6f-108">Property set:</span></span>  <br/> |<span data-ttu-id="d7e6f-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="d7e6f-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="d7e6f-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="d7e6f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d7e6f-111">0x00008107</span><span class="sxs-lookup"><span data-stu-id="d7e6f-111">0x00008107</span></span>  <br/> |
|<span data-ttu-id="d7e6f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d7e6f-112">Data type:</span></span>  <br/> |<span data-ttu-id="d7e6f-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d7e6f-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="d7e6f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d7e6f-114">Area:</span></span>  <br/> |<span data-ttu-id="d7e6f-115">任务</span><span class="sxs-lookup"><span data-stu-id="d7e6f-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d7e6f-116">注解</span><span class="sxs-lookup"><span data-stu-id="d7e6f-116">Remarks</span></span>

<span data-ttu-id="d7e6f-117">当任务的提醒被消除时, 此值设置为 TRUE, 否则设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-117">This value is set to TRUE when the task's reminder is dismissed, and set to FALSE otherwise.</span></span> <span data-ttu-id="d7e6f-118">如果未设置, 则假定默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-118">If left unset, a default of FALSE is assumed.</span></span>
  
<span data-ttu-id="d7e6f-119">如[[OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)中所指定的那样, **dispidReminderSet**属性指示是否在任务上设置提醒。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-119">As specified in [[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx), the **dispidReminderSet** property indicates whether a reminder is set on the task.</span></span> <span data-ttu-id="d7e6f-120">但是, 此属性仅指示是否存在针对单个任务的提醒。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-120">However, this property only indicates the presence of a reminder on a single task.</span></span> <span data-ttu-id="d7e6f-121">不能单独使用它来确定未来的定期任务实例是否需要提醒。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-121">It cannot be used alone to determine whether a future instance of a recurring task needs a reminder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d7e6f-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="d7e6f-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d7e6f-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="d7e6f-123">Protocol specifications</span></span>

<span data-ttu-id="d7e6f-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d7e6f-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d7e6f-125">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-125">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d7e6f-126">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d7e6f-126">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d7e6f-127">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-127">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="d7e6f-128">[[毫秒-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d7e6f-128">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d7e6f-129">指定用于电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-129">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d7e6f-130">头文件</span><span class="sxs-lookup"><span data-stu-id="d7e6f-130">Header files</span></span>

<span data-ttu-id="d7e6f-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d7e6f-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="d7e6f-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d7e6f-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d7e6f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e6f-133">See also</span></span>



[<span data-ttu-id="d7e6f-134">PidLidReminderSet 规范属性</span><span class="sxs-lookup"><span data-stu-id="d7e6f-134">PidLidReminderSet Canonical Property</span></span>](pidlidreminderset-canonical-property.md)


[<span data-ttu-id="d7e6f-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d7e6f-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d7e6f-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d7e6f-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d7e6f-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d7e6f-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d7e6f-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d7e6f-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

