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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357937"
---
# <a name="pidlidtaskmode-canonical-property"></a><span data-ttu-id="6f018-103">PidLidTaskMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f018-103">PidLidTaskMode Canonical Property</span></span>

  
  
<span data-ttu-id="6f018-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f018-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f018-105">指定任务的分配状态。</span><span class="sxs-lookup"><span data-stu-id="6f018-105">Specifies the assignment status of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6f018-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6f018-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6f018-107">dispidTaskMode</span><span class="sxs-lookup"><span data-stu-id="6f018-107">dispidTaskMode</span></span>  <br/> |
|<span data-ttu-id="6f018-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="6f018-108">Property set:</span></span>  <br/> |<span data-ttu-id="6f018-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="6f018-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="6f018-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="6f018-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6f018-111">0x00008518</span><span class="sxs-lookup"><span data-stu-id="6f018-111">0x00008518</span></span>  <br/> |
|<span data-ttu-id="6f018-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6f018-112">Data type:</span></span>  <br/> |<span data-ttu-id="6f018-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6f018-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6f018-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6f018-114">Area:</span></span>  <br/> |<span data-ttu-id="6f018-115">任务</span><span class="sxs-lookup"><span data-stu-id="6f018-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6f018-116">备注</span><span class="sxs-lookup"><span data-stu-id="6f018-116">Remarks</span></span>

<span data-ttu-id="6f018-117">该值必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="6f018-117">The value must be one of the following.</span></span>
  
|<span data-ttu-id="6f018-118">**值**</span><span class="sxs-lookup"><span data-stu-id="6f018-118">**Value**</span></span>|<span data-ttu-id="6f018-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6f018-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f018-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="6f018-120">0x00000000</span></span>  <br/> |<span data-ttu-id="6f018-121">任务未分配。</span><span class="sxs-lookup"><span data-stu-id="6f018-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="6f018-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="6f018-122">0x00000001</span></span>  <br/> |<span data-ttu-id="6f018-123">任务嵌入在任务请求中。</span><span class="sxs-lookup"><span data-stu-id="6f018-123">The task is embedded in a task request.</span></span>  <br/> |
|<span data-ttu-id="6f018-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="6f018-124">0x00000002</span></span>  <br/> |<span data-ttu-id="6f018-125">任务受理人已接受该任务。</span><span class="sxs-lookup"><span data-stu-id="6f018-125">The task was accepted by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="6f018-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="6f018-126">0x00000003</span></span>  <br/> |<span data-ttu-id="6f018-127">任务被任务接受者拒绝。</span><span class="sxs-lookup"><span data-stu-id="6f018-127">The task was rejected by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="6f018-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="6f018-128">0x00000004</span></span>  <br/> |<span data-ttu-id="6f018-129">任务嵌入在任务更新中。</span><span class="sxs-lookup"><span data-stu-id="6f018-129">The task is embedded in a task update.</span></span>  <br/> |
|<span data-ttu-id="6f018-130">0x00000005</span><span class="sxs-lookup"><span data-stu-id="6f018-130">0x00000005</span></span>  <br/> |<span data-ttu-id="6f018-131">任务已分配给任务分配者。</span><span class="sxs-lookup"><span data-stu-id="6f018-131">The task was assigned to the task assigner.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="6f018-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="6f018-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6f018-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="6f018-133">Protocol specifications</span></span>

<span data-ttu-id="6f018-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f018-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f018-135">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="6f018-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6f018-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f018-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f018-137">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="6f018-137">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6f018-138">头文件</span><span class="sxs-lookup"><span data-stu-id="6f018-138">Header files</span></span>

<span data-ttu-id="6f018-139">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6f018-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="6f018-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6f018-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6f018-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f018-141">See also</span></span>



[<span data-ttu-id="6f018-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6f018-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6f018-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f018-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6f018-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6f018-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6f018-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6f018-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

