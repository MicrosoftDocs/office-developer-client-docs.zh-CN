---
title: PidLidTaskHistory 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskHistory
api_type:
- COM
ms.assetid: 104ef21c-b607-48b7-9b06-bc53b7d9b68a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ba900ec4b8c8f1bcc2c85aae6c78ab59a43ee3cc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563623"
---
# <a name="pidlidtaskhistory-canonical-property"></a><span data-ttu-id="e18c0-103">PidLidTaskHistory 规范属性</span><span class="sxs-lookup"><span data-stu-id="e18c0-103">PidLidTaskHistory Canonical Property</span></span>

  
  
<span data-ttu-id="e18c0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e18c0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e18c0-105">指示上次已对任务进行的更改的类型。</span><span class="sxs-lookup"><span data-stu-id="e18c0-105">Indicates the type of change that was last made to the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e18c0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e18c0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e18c0-107">dispidTaskHistory</span><span class="sxs-lookup"><span data-stu-id="e18c0-107">dispidTaskHistory</span></span>  <br/> |
|<span data-ttu-id="e18c0-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e18c0-108">Property set:</span></span>  <br/> |<span data-ttu-id="e18c0-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="e18c0-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="e18c0-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e18c0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e18c0-111">0x0000811A</span><span class="sxs-lookup"><span data-stu-id="e18c0-111">0x0000811A</span></span>  <br/> |
|<span data-ttu-id="e18c0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e18c0-112">Data type:</span></span>  <br/> |<span data-ttu-id="e18c0-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e18c0-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e18c0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e18c0-114">Area:</span></span>  <br/> |<span data-ttu-id="e18c0-115">Task</span><span class="sxs-lookup"><span data-stu-id="e18c0-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e18c0-116">注解</span><span class="sxs-lookup"><span data-stu-id="e18c0-116">Remarks</span></span>

<span data-ttu-id="e18c0-117">设置此属性的值，当**dispidTaskLastUpdate** ([PidLidTaskLastUpdate](pidlidtasklastupdate-canonical-property.md)) 属性必须也可以设置为当前时间。</span><span class="sxs-lookup"><span data-stu-id="e18c0-117">When the value of this property is set, the **dispidTaskLastUpdate** ([PidLidTaskLastUpdate](pidlidtasklastupdate-canonical-property.md)) property must also be set to the current time.</span></span> <span data-ttu-id="e18c0-118">下表显示**dispidTaskHistory**递减优先级的顺序列出的属性值。</span><span class="sxs-lookup"><span data-stu-id="e18c0-118">The following table shows the **dispidTaskHistory** property values, listed in order of decreasing priority.</span></span> 
  
|<span data-ttu-id="e18c0-119">**值**</span><span class="sxs-lookup"><span data-stu-id="e18c0-119">**Value**</span></span>|<span data-ttu-id="e18c0-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="e18c0-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e18c0-121">0x00000004</span><span class="sxs-lookup"><span data-stu-id="e18c0-121">0x00000004</span></span>  <br/> |<span data-ttu-id="e18c0-122">更改的**dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e18c0-122">The **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) property changed.</span></span>  <br/> |
|<span data-ttu-id="e18c0-123">0x00000003</span><span class="sxs-lookup"><span data-stu-id="e18c0-123">0x00000003</span></span>  <br/> |<span data-ttu-id="e18c0-124">另一个属性被更改。</span><span class="sxs-lookup"><span data-stu-id="e18c0-124">Another property was changed.</span></span>  <br/> |
|<span data-ttu-id="e18c0-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="e18c0-125">0x00000001</span></span>  <br/> |<span data-ttu-id="e18c0-126">任务受理人接受此任务。</span><span class="sxs-lookup"><span data-stu-id="e18c0-126">The task assignee accepted this task.</span></span>  <br/> |
|<span data-ttu-id="e18c0-127">0x00000002</span><span class="sxs-lookup"><span data-stu-id="e18c0-127">0x00000002</span></span>  <br/> |<span data-ttu-id="e18c0-128">任务受理人拒绝此任务。</span><span class="sxs-lookup"><span data-stu-id="e18c0-128">The task assignee rejected this task.</span></span>  <br/> |
|<span data-ttu-id="e18c0-129">0x00000005</span><span class="sxs-lookup"><span data-stu-id="e18c0-129">0x00000005</span></span>  <br/> |<span data-ttu-id="e18c0-130">任务已分配给任务受理人。</span><span class="sxs-lookup"><span data-stu-id="e18c0-130">The task was assigned to a task assignee.</span></span>  <br/> |
|<span data-ttu-id="e18c0-131">0x00000000</span><span class="sxs-lookup"><span data-stu-id="e18c0-131">0x00000000</span></span>  <br/> |<span data-ttu-id="e18c0-132">未不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="e18c0-132">No changes were made.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="e18c0-133">相关资源</span><span class="sxs-lookup"><span data-stu-id="e18c0-133">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e18c0-134">协议规范</span><span class="sxs-lookup"><span data-stu-id="e18c0-134">Protocol specifications</span></span>

<span data-ttu-id="e18c0-135">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e18c0-135">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e18c0-136">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e18c0-136">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e18c0-137">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e18c0-137">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e18c0-138">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="e18c0-138">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e18c0-139">头文件</span><span class="sxs-lookup"><span data-stu-id="e18c0-139">Header files</span></span>

<span data-ttu-id="e18c0-140">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e18c0-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="e18c0-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e18c0-141">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e18c0-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e18c0-142">See also</span></span>



[<span data-ttu-id="e18c0-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e18c0-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e18c0-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e18c0-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e18c0-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e18c0-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e18c0-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e18c0-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

