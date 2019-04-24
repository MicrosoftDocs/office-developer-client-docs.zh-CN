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
# <a name="pidlidtaskmode-canonical-property"></a><span data-ttu-id="749ee-103">PidLidTaskMode 规范属性</span><span class="sxs-lookup"><span data-stu-id="749ee-103">PidLidTaskMode Canonical Property</span></span>

  
  
<span data-ttu-id="749ee-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="749ee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="749ee-105">指定任务的分配状态。</span><span class="sxs-lookup"><span data-stu-id="749ee-105">Specifies the assignment status of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="749ee-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="749ee-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="749ee-107">dispidTaskMode</span><span class="sxs-lookup"><span data-stu-id="749ee-107">dispidTaskMode</span></span>  <br/> |
|<span data-ttu-id="749ee-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="749ee-108">Property set:</span></span>  <br/> |<span data-ttu-id="749ee-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="749ee-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="749ee-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="749ee-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="749ee-111">0x00008518</span><span class="sxs-lookup"><span data-stu-id="749ee-111">0x00008518</span></span>  <br/> |
|<span data-ttu-id="749ee-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="749ee-112">Data type:</span></span>  <br/> |<span data-ttu-id="749ee-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="749ee-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="749ee-114">区域：</span><span class="sxs-lookup"><span data-stu-id="749ee-114">Area:</span></span>  <br/> |<span data-ttu-id="749ee-115">任务</span><span class="sxs-lookup"><span data-stu-id="749ee-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="749ee-116">注解</span><span class="sxs-lookup"><span data-stu-id="749ee-116">Remarks</span></span>

<span data-ttu-id="749ee-117">值必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="749ee-117">The value must be one of the following.</span></span>
  
|<span data-ttu-id="749ee-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="749ee-118">**Value**</span></span>|<span data-ttu-id="749ee-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="749ee-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="749ee-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="749ee-120">0x00000000</span></span>  <br/> |<span data-ttu-id="749ee-121">未分配任务。</span><span class="sxs-lookup"><span data-stu-id="749ee-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="749ee-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="749ee-122">0x00000001</span></span>  <br/> |<span data-ttu-id="749ee-123">任务嵌入在任务请求中。</span><span class="sxs-lookup"><span data-stu-id="749ee-123">The task is embedded in a task request.</span></span>  <br/> |
|<span data-ttu-id="749ee-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="749ee-124">0x00000002</span></span>  <br/> |<span data-ttu-id="749ee-125">任务受托人接受了该任务。</span><span class="sxs-lookup"><span data-stu-id="749ee-125">The task was accepted by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="749ee-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="749ee-126">0x00000003</span></span>  <br/> |<span data-ttu-id="749ee-127">任务受托人拒绝了该任务。</span><span class="sxs-lookup"><span data-stu-id="749ee-127">The task was rejected by the task assignee.</span></span>  <br/> |
|<span data-ttu-id="749ee-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="749ee-128">0x00000004</span></span>  <br/> |<span data-ttu-id="749ee-129">任务已嵌入任务更新中。</span><span class="sxs-lookup"><span data-stu-id="749ee-129">The task is embedded in a task update.</span></span>  <br/> |
|<span data-ttu-id="749ee-130">0x00000005</span><span class="sxs-lookup"><span data-stu-id="749ee-130">0x00000005</span></span>  <br/> |<span data-ttu-id="749ee-131">任务已分配给任务 assigner。</span><span class="sxs-lookup"><span data-stu-id="749ee-131">The task was assigned to the task assigner.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="749ee-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="749ee-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="749ee-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="749ee-133">Protocol specifications</span></span>

<span data-ttu-id="749ee-134">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="749ee-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="749ee-135">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="749ee-135">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="749ee-136">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="749ee-136">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="749ee-137">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="749ee-137">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="749ee-138">头文件</span><span class="sxs-lookup"><span data-stu-id="749ee-138">Header files</span></span>

<span data-ttu-id="749ee-139">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="749ee-139">Mapidefs.h</span></span>
  
> <span data-ttu-id="749ee-140">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="749ee-140">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="749ee-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="749ee-141">See also</span></span>



[<span data-ttu-id="749ee-142">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="749ee-142">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="749ee-143">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="749ee-143">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="749ee-144">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="749ee-144">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="749ee-145">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="749ee-145">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

