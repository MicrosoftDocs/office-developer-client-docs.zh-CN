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
# <a name="pidlidtaskstate-canonical-property"></a><span data-ttu-id="1850c-103">PidLidTaskState 规范属性</span><span class="sxs-lookup"><span data-stu-id="1850c-103">PidLidTaskState Canonical Property</span></span>

  
  
<span data-ttu-id="1850c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1850c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1850c-105">指示任务的当前工作分配状态。</span><span class="sxs-lookup"><span data-stu-id="1850c-105">Indicates the current assignment state of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1850c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1850c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1850c-107">dispidTaskState</span><span class="sxs-lookup"><span data-stu-id="1850c-107">dispidTaskState</span></span>  <br/> |
|<span data-ttu-id="1850c-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="1850c-108">Property set:</span></span>  <br/> |<span data-ttu-id="1850c-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="1850c-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="1850c-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="1850c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1850c-111">0x00008113</span><span class="sxs-lookup"><span data-stu-id="1850c-111">0x00008113</span></span>  <br/> |
|<span data-ttu-id="1850c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1850c-112">Data type:</span></span>  <br/> |<span data-ttu-id="1850c-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1850c-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1850c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1850c-114">Area:</span></span>  <br/> |<span data-ttu-id="1850c-115">任务</span><span class="sxs-lookup"><span data-stu-id="1850c-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1850c-116">备注</span><span class="sxs-lookup"><span data-stu-id="1850c-116">Remarks</span></span>

<span data-ttu-id="1850c-117">此属性的值必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="1850c-117">The value of this property must be one of the following.</span></span>
  
|<span data-ttu-id="1850c-118">**值**</span><span class="sxs-lookup"><span data-stu-id="1850c-118">**Value**</span></span>|<span data-ttu-id="1850c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1850c-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1850c-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="1850c-120">0x00000000</span></span>  <br/> |<span data-ttu-id="1850c-121">创建此任务与嵌入任务拒绝中但在本地找不到的任务相对应。</span><span class="sxs-lookup"><span data-stu-id="1850c-121">This task was created to correspond to a task that was embedded in a task rejection but could not be found locally.</span></span>  <br/> |
|<span data-ttu-id="1850c-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="1850c-122">0x00000001</span></span>  <br/> |<span data-ttu-id="1850c-123">任务未分配。</span><span class="sxs-lookup"><span data-stu-id="1850c-123">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="1850c-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="1850c-124">0x00000002</span></span>  <br/> |<span data-ttu-id="1850c-125">任务是任务被分配者所分配任务的副本。</span><span class="sxs-lookup"><span data-stu-id="1850c-125">The task is the task assignee's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="1850c-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="1850c-126">0x00000003</span></span>  <br/> |<span data-ttu-id="1850c-127">任务是任务分配者所分配任务的副本。</span><span class="sxs-lookup"><span data-stu-id="1850c-127">The task is the task assigner's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="1850c-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="1850c-128">0x00000004</span></span>  <br/> |<span data-ttu-id="1850c-129">该任务是任务分配者拒绝的任务的副本。</span><span class="sxs-lookup"><span data-stu-id="1850c-129">The task is the task assigner's copy of a rejected task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1850c-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="1850c-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1850c-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="1850c-131">Protocol specifications</span></span>

<span data-ttu-id="1850c-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1850c-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1850c-133">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="1850c-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1850c-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1850c-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1850c-135">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="1850c-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="1850c-136">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1850c-136">[[MS-OXOSFLD]](https://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1850c-137">指定用于创建和定位邮箱中特殊文件夹的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="1850c-137">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="1850c-138">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1850c-138">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1850c-139">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="1850c-139">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="1850c-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1850c-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1850c-141">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="1850c-141">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1850c-142">头文件</span><span class="sxs-lookup"><span data-stu-id="1850c-142">Header files</span></span>

<span data-ttu-id="1850c-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1850c-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="1850c-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1850c-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1850c-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1850c-145">See also</span></span>



[<span data-ttu-id="1850c-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1850c-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1850c-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1850c-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1850c-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1850c-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1850c-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1850c-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

