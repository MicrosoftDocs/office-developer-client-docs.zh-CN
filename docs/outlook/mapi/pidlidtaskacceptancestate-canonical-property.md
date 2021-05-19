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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b42be4b42d085aba8999a8c3f1a780ed972fa136
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331288"
---
# <a name="pidlidtaskacceptancestate-canonical-property"></a><span data-ttu-id="85de7-103">PidLidTaskAcceptanceState 规范属性</span><span class="sxs-lookup"><span data-stu-id="85de7-103">PidLidTaskAcceptanceState Canonical Property</span></span>

  
  
<span data-ttu-id="85de7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85de7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85de7-105">指示任务的接受状态。</span><span class="sxs-lookup"><span data-stu-id="85de7-105">Indicates the acceptance state of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="85de7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="85de7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="85de7-107">dispidTaskDelegValue</span><span class="sxs-lookup"><span data-stu-id="85de7-107">dispidTaskDelegValue</span></span>  <br/> |
|<span data-ttu-id="85de7-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="85de7-108">Property set:</span></span>  <br/> |<span data-ttu-id="85de7-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="85de7-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="85de7-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="85de7-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="85de7-111">0x0000812A</span><span class="sxs-lookup"><span data-stu-id="85de7-111">0x0000812A</span></span>  <br/> |
|<span data-ttu-id="85de7-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="85de7-112">Data type:</span></span>  <br/> |<span data-ttu-id="85de7-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="85de7-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="85de7-114">区域：</span><span class="sxs-lookup"><span data-stu-id="85de7-114">Area:</span></span>  <br/> |<span data-ttu-id="85de7-115">任务</span><span class="sxs-lookup"><span data-stu-id="85de7-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="85de7-116">备注</span><span class="sxs-lookup"><span data-stu-id="85de7-116">Remarks</span></span>

<span data-ttu-id="85de7-117">下表显示了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="85de7-117">The following table shows the possible values for this property.</span></span>
  
|<span data-ttu-id="85de7-118">**值**</span><span class="sxs-lookup"><span data-stu-id="85de7-118">**Value**</span></span>|<span data-ttu-id="85de7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="85de7-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85de7-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="85de7-120">0x00000000</span></span>  <br/> |<span data-ttu-id="85de7-121">任务未分配。</span><span class="sxs-lookup"><span data-stu-id="85de7-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="85de7-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="85de7-122">0x00000001</span></span>  <br/> |<span data-ttu-id="85de7-123">任务的接受状态未知。</span><span class="sxs-lookup"><span data-stu-id="85de7-123">The task's acceptance status is unknown.</span></span>  <br/> |
|<span data-ttu-id="85de7-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="85de7-124">0x00000002</span></span>  <br/> |<span data-ttu-id="85de7-125">任务受理人接受该任务。</span><span class="sxs-lookup"><span data-stu-id="85de7-125">The task assignee accepted the task.</span></span> <span data-ttu-id="85de7-126">此值在客户端处理任务接受时设置。</span><span class="sxs-lookup"><span data-stu-id="85de7-126">This value is set when the client processes a task acceptance.</span></span>  <br/> |
|<span data-ttu-id="85de7-127">0x00000003</span><span class="sxs-lookup"><span data-stu-id="85de7-127">0x00000003</span></span>  <br/> |<span data-ttu-id="85de7-128">任务接受者拒绝了该任务。</span><span class="sxs-lookup"><span data-stu-id="85de7-128">The task assignee rejected the task.</span></span> <span data-ttu-id="85de7-129">此值在客户端处理任务拒绝时设置。</span><span class="sxs-lookup"><span data-stu-id="85de7-129">This value is set when the client processes a task rejection.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="85de7-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="85de7-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="85de7-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="85de7-131">Protocol specifications</span></span>

<span data-ttu-id="85de7-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="85de7-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="85de7-133">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="85de7-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="85de7-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="85de7-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="85de7-135">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="85de7-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="85de7-136">头文件</span><span class="sxs-lookup"><span data-stu-id="85de7-136">Header files</span></span>

<span data-ttu-id="85de7-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="85de7-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="85de7-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="85de7-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="85de7-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85de7-139">See also</span></span>



[<span data-ttu-id="85de7-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="85de7-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="85de7-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="85de7-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="85de7-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="85de7-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="85de7-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="85de7-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

