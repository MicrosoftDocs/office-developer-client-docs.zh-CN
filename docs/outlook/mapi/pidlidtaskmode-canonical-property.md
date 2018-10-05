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
ms.openlocfilehash: d0ae319a6b5fa4c901ec7d318c7ebdd216a2adeb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398967"
---
# <a name="pidlidtaskmode-canonical-property"></a><span data-ttu-id="b6129-103">PidLidTaskMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6129-103">PidLidTaskMode Canonical Property</span></span>

  
  
<span data-ttu-id="b6129-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6129-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6129-105">指定任务的工作分配状态。</span><span class="sxs-lookup"><span data-stu-id="b6129-105">Specifies the assignment status of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b6129-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b6129-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b6129-107">dispidTaskMode</span><span class="sxs-lookup"><span data-stu-id="b6129-107">dispidTaskMode</span></span>  <br/> |
|<span data-ttu-id="b6129-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b6129-108">Property set:</span></span>  <br/> |<span data-ttu-id="b6129-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b6129-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b6129-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b6129-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b6129-111">0x00008518</span><span class="sxs-lookup"><span data-stu-id="b6129-111">0x00008518</span></span>  <br/> |
|<span data-ttu-id="b6129-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b6129-112">Data type:</span></span>  <br/> |<span data-ttu-id="b6129-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b6129-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b6129-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b6129-114">Area:</span></span>  <br/> |<span data-ttu-id="b6129-115">Task</span><span class="sxs-lookup"><span data-stu-id="b6129-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b6129-116">说明</span><span class="sxs-lookup"><span data-stu-id="b6129-116">Remarks</span></span>

<span data-ttu-id="b6129-117">值必须是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="b6129-117">The value must be one of the following.</span></span>
  
|<span data-ttu-id="b6129-118">**值**</span><span class="sxs-lookup"><span data-stu-id="b6129-118">**Value**</span></span>|<span data-ttu-id="b6129-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b6129-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6129-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b6129-120">0x00000000</span></span>  <br/> |<span data-ttu-id="b6129-121">未分配的任务。</span><span class="sxs-lookup"><span data-stu-id="b6129-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="b6129-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b6129-122">0x00000001</span></span>  <br/> |<span data-ttu-id="b6129-123">任务请求中嵌入任务。</span><span class="sxs-lookup"><span data-stu-id="b6129-123">The task is embedded in a task request.</span></span>  <br/> |
|<span data-ttu-id="b6129-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b6129-124">0x00000002</span></span>  <br/> |<span data-ttu-id="b6129-125">任务已接受任务受理人。</span><span class="sxs-lookup"><span data-stu-id="b6129-125">The task was accepted by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="b6129-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="b6129-126">0x00000003</span></span>  <br/> |<span data-ttu-id="b6129-127">任务工作负责人被拒绝任务。</span><span class="sxs-lookup"><span data-stu-id="b6129-127">The task was rejected by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="b6129-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b6129-128">0x00000004</span></span>  <br/> |<span data-ttu-id="b6129-129">任务更新中嵌入任务。</span><span class="sxs-lookup"><span data-stu-id="b6129-129">The task is embedded in a task update.</span></span>  <br/> |
|<span data-ttu-id="b6129-130">0x00000005</span><span class="sxs-lookup"><span data-stu-id="b6129-130">0x00000005</span></span>  <br/> |<span data-ttu-id="b6129-131">任务已分配给任务分配人。</span><span class="sxs-lookup"><span data-stu-id="b6129-131">The task was assigned to the task assigner.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b6129-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="b6129-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b6129-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="b6129-133">Protocol specifications</span></span>

<span data-ttu-id="b6129-134">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6129-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6129-135">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b6129-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b6129-136">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6129-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6129-137">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="b6129-137">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b6129-138">头文件</span><span class="sxs-lookup"><span data-stu-id="b6129-138">Header files</span></span>

<span data-ttu-id="b6129-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b6129-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="b6129-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b6129-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6129-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6129-141">See also</span></span>



[<span data-ttu-id="b6129-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b6129-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b6129-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6129-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b6129-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b6129-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b6129-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b6129-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

