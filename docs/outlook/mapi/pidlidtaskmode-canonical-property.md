---
title: PidLidTaskMode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskMode
api_type:
- COM
ms.assetid: 185db683-301a-4d91-a583-6959853fa1ad
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f8eef7863cec565403d41dae26687b75f078e0d7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777102"
---
# <a name="pidlidtaskmode-canonical-property"></a><span data-ttu-id="7b5e0-103">PidLidTaskMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b5e0-103">PidLidTaskMode Canonical Property</span></span>

  
  
<span data-ttu-id="7b5e0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7b5e0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7b5e0-105">指定任务的工作分配状态。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-105">Specifies the assignment status of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7b5e0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7b5e0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7b5e0-107">dispidTaskMode</span><span class="sxs-lookup"><span data-stu-id="7b5e0-107">dispidTaskMode</span></span>  <br/> |
|<span data-ttu-id="7b5e0-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7b5e0-108">Property set:</span></span>  <br/> |<span data-ttu-id="7b5e0-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="7b5e0-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="7b5e0-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7b5e0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7b5e0-111">0x00008518</span><span class="sxs-lookup"><span data-stu-id="7b5e0-111">0x00008518</span></span>  <br/> |
|<span data-ttu-id="7b5e0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7b5e0-112">Data type:</span></span>  <br/> |<span data-ttu-id="7b5e0-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7b5e0-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7b5e0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7b5e0-114">Area:</span></span>  <br/> |<span data-ttu-id="7b5e0-115">Task</span><span class="sxs-lookup"><span data-stu-id="7b5e0-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7b5e0-116">说明</span><span class="sxs-lookup"><span data-stu-id="7b5e0-116">Remarks</span></span>

<span data-ttu-id="7b5e0-117">值必须是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-117">The value must be one of the following.</span></span>
  
|<span data-ttu-id="7b5e0-118">**值**</span><span class="sxs-lookup"><span data-stu-id="7b5e0-118">**Value**</span></span>|<span data-ttu-id="7b5e0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7b5e0-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7b5e0-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="7b5e0-120">0x00000000</span></span>  <br/> |<span data-ttu-id="7b5e0-121">未分配的任务。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="7b5e0-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="7b5e0-122">0x00000001</span></span>  <br/> |<span data-ttu-id="7b5e0-123">任务请求中嵌入任务。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-123">The task is embedded in a task request.</span></span>  <br/> |
|<span data-ttu-id="7b5e0-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="7b5e0-124">0x00000002</span></span>  <br/> |<span data-ttu-id="7b5e0-125">任务已接受任务受理人。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-125">The task was accepted by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="7b5e0-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="7b5e0-126">0x00000003</span></span>  <br/> |<span data-ttu-id="7b5e0-127">任务工作负责人被拒绝任务。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-127">The task was rejected by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="7b5e0-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="7b5e0-128">0x00000004</span></span>  <br/> |<span data-ttu-id="7b5e0-129">任务更新中嵌入任务。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-129">The task is embedded in a task update.</span></span>  <br/> |
|<span data-ttu-id="7b5e0-130">0x00000005</span><span class="sxs-lookup"><span data-stu-id="7b5e0-130">0x00000005</span></span>  <br/> |<span data-ttu-id="7b5e0-131">任务已分配给任务分配人。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-131">The task was assigned to the task assigner.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="7b5e0-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="7b5e0-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7b5e0-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="7b5e0-133">Protocol specifications</span></span>

<span data-ttu-id="7b5e0-134">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b5e0-134">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7b5e0-135">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7b5e0-136">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b5e0-136">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7b5e0-137">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-137">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7b5e0-138">头文件</span><span class="sxs-lookup"><span data-stu-id="7b5e0-138">Header files</span></span>

<span data-ttu-id="7b5e0-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7b5e0-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="7b5e0-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7b5e0-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b5e0-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b5e0-141">See also</span></span>



[<span data-ttu-id="7b5e0-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7b5e0-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7b5e0-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b5e0-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7b5e0-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7b5e0-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7b5e0-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7b5e0-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

