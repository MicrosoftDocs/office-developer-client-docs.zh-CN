---
title: PidLidTaskAcceptanceState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAcceptanceState
api_type:
- COM
ms.assetid: 7012f524-bc66-48ea-85b5-163e05029d35
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 970fc57a3fd129f0ac50af3f71e0d5e15ff22371
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777059"
---
# <a name="pidlidtaskacceptancestate-canonical-property"></a><span data-ttu-id="ff6e3-103">PidLidTaskAcceptanceState 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff6e3-103">PidLidTaskAcceptanceState Canonical Property</span></span>

  
  
<span data-ttu-id="ff6e3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff6e3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff6e3-105">指示任务的接受状态。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-105">Indicates the acceptance state of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff6e3-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ff6e3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff6e3-107">dispidTaskDelegValue</span><span class="sxs-lookup"><span data-stu-id="ff6e3-107">dispidTaskDelegValue</span></span>  <br/> |
|<span data-ttu-id="ff6e3-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ff6e3-108">Property set:</span></span>  <br/> |<span data-ttu-id="ff6e3-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="ff6e3-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="ff6e3-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ff6e3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ff6e3-111">0x0000812A</span><span class="sxs-lookup"><span data-stu-id="ff6e3-111">0x0000812A</span></span>  <br/> |
|<span data-ttu-id="ff6e3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff6e3-112">Data type:</span></span>  <br/> |<span data-ttu-id="ff6e3-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ff6e3-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ff6e3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ff6e3-114">Area:</span></span>  <br/> |<span data-ttu-id="ff6e3-115">任务</span><span class="sxs-lookup"><span data-stu-id="ff6e3-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff6e3-116">备注</span><span class="sxs-lookup"><span data-stu-id="ff6e3-116">Remarks</span></span>

<span data-ttu-id="ff6e3-117">下表显示了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-117">The following table shows the possible values for this property.</span></span>
  
|<span data-ttu-id="ff6e3-118">**值**</span><span class="sxs-lookup"><span data-stu-id="ff6e3-118">**Value**</span></span>|<span data-ttu-id="ff6e3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff6e3-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff6e3-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ff6e3-120">0x00000000</span></span>  <br/> |<span data-ttu-id="ff6e3-121">未分配的任务。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="ff6e3-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ff6e3-122">0x00000001</span></span>  <br/> |<span data-ttu-id="ff6e3-123">任务的接受状态为未知。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-123">The task's acceptance status is unknown.</span></span>  <br/> |
|<span data-ttu-id="ff6e3-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ff6e3-124">0x00000002</span></span>  <br/> |<span data-ttu-id="ff6e3-125">任务受理人接受任务。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-125">The task assignee accepted the task.</span></span> <span data-ttu-id="ff6e3-126">此值是客户端处理接受任务时设置的。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-126">This value is set when the client processes a task acceptance.</span></span>  <br/> |
|<span data-ttu-id="ff6e3-127">0x00000003</span><span class="sxs-lookup"><span data-stu-id="ff6e3-127">0x00000003</span></span>  <br/> |<span data-ttu-id="ff6e3-128">任务受理人拒绝任务。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-128">The task assignee rejected the task.</span></span> <span data-ttu-id="ff6e3-129">此值是客户端处理任务拒绝时设置的。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-129">This value is set when the client processes a task rejection.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ff6e3-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff6e3-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff6e3-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff6e3-131">Protocol specifications</span></span>

<span data-ttu-id="ff6e3-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff6e3-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff6e3-133">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff6e3-134">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff6e3-134">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff6e3-135">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff6e3-136">头文件</span><span class="sxs-lookup"><span data-stu-id="ff6e3-136">Header files</span></span>

<span data-ttu-id="ff6e3-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff6e3-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff6e3-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff6e3-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff6e3-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff6e3-139">See also</span></span>



[<span data-ttu-id="ff6e3-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff6e3-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff6e3-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff6e3-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff6e3-142">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff6e3-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff6e3-143">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff6e3-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

