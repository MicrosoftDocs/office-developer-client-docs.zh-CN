---
title: PidLidTaskState 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskState
api_type:
- COM
ms.assetid: 06d1f8a3-53e1-4c9a-9703-75de7a11a772
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 149f238ea53e0669f4d95c8e6c2b17a2b5a1c209
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316532"
---
# <a name="pidlidtaskstate-canonical-property"></a><span data-ttu-id="856a2-103">PidLidTaskState 规范属性</span><span class="sxs-lookup"><span data-stu-id="856a2-103">PidLidTaskState Canonical Property</span></span>

  
  
<span data-ttu-id="856a2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="856a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="856a2-105">指示任务的当前分配状态。</span><span class="sxs-lookup"><span data-stu-id="856a2-105">Indicates the current assignment state of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="856a2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="856a2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="856a2-107">dispidTaskState</span><span class="sxs-lookup"><span data-stu-id="856a2-107">dispidTaskState</span></span>  <br/> |
|<span data-ttu-id="856a2-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="856a2-108">Property set:</span></span>  <br/> |<span data-ttu-id="856a2-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="856a2-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="856a2-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="856a2-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="856a2-111">0x00008113</span><span class="sxs-lookup"><span data-stu-id="856a2-111">0x00008113</span></span>  <br/> |
|<span data-ttu-id="856a2-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="856a2-112">Data type:</span></span>  <br/> |<span data-ttu-id="856a2-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="856a2-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="856a2-114">区域：</span><span class="sxs-lookup"><span data-stu-id="856a2-114">Area:</span></span>  <br/> |<span data-ttu-id="856a2-115">任务</span><span class="sxs-lookup"><span data-stu-id="856a2-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="856a2-116">注解</span><span class="sxs-lookup"><span data-stu-id="856a2-116">Remarks</span></span>

<span data-ttu-id="856a2-117">此属性的值必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="856a2-117">The value of this property must be one of the following.</span></span>
  
|<span data-ttu-id="856a2-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="856a2-118">**Value**</span></span>|<span data-ttu-id="856a2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="856a2-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="856a2-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="856a2-120">0x00000000</span></span>  <br/> |<span data-ttu-id="856a2-121">此任务已创建为对应于嵌入在任务拒绝中但未能在本地找到的任务。</span><span class="sxs-lookup"><span data-stu-id="856a2-121">This task was created to correspond to a task that was embedded in a task rejection but could not be found locally.</span></span>  <br/> |
|<span data-ttu-id="856a2-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="856a2-122">0x00000001</span></span>  <br/> |<span data-ttu-id="856a2-123">未分配任务。</span><span class="sxs-lookup"><span data-stu-id="856a2-123">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="856a2-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="856a2-124">0x00000002</span></span>  <br/> |<span data-ttu-id="856a2-125">任务是分配的任务的任务受理人的副本。</span><span class="sxs-lookup"><span data-stu-id="856a2-125">The task is the task assignee's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="856a2-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="856a2-126">0x00000003</span></span>  <br/> |<span data-ttu-id="856a2-127">任务是任务 assigner 的已分配任务的副本。</span><span class="sxs-lookup"><span data-stu-id="856a2-127">The task is the task assigner's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="856a2-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="856a2-128">0x00000004</span></span>  <br/> |<span data-ttu-id="856a2-129">任务是任务 assigner 的已拒绝任务的副本。</span><span class="sxs-lookup"><span data-stu-id="856a2-129">The task is the task assigner's copy of a rejected task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="856a2-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="856a2-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="856a2-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="856a2-131">Protocol specifications</span></span>

<span data-ttu-id="856a2-132">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="856a2-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="856a2-133">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="856a2-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="856a2-134">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="856a2-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="856a2-135">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="856a2-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="856a2-136">[[毫秒-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="856a2-136">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="856a2-137">指定用于创建和定位邮箱中的特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="856a2-137">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="856a2-138">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="856a2-138">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="856a2-139">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="856a2-139">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="856a2-140">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="856a2-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="856a2-141">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="856a2-141">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="856a2-142">头文件</span><span class="sxs-lookup"><span data-stu-id="856a2-142">Header files</span></span>

<span data-ttu-id="856a2-143">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="856a2-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="856a2-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="856a2-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="856a2-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="856a2-145">See also</span></span>



[<span data-ttu-id="856a2-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="856a2-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="856a2-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="856a2-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="856a2-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="856a2-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="856a2-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="856a2-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

