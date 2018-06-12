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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b4bab1948bc563b92dafa16922da3b9760cf1a1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777110"
---
# <a name="pidlidtaskstate-canonical-property"></a><span data-ttu-id="cee64-103">PidLidTaskState 规范属性</span><span class="sxs-lookup"><span data-stu-id="cee64-103">PidLidTaskState Canonical Property</span></span>

  
  
<span data-ttu-id="cee64-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cee64-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cee64-105">指示任务的当前工作分配状态。</span><span class="sxs-lookup"><span data-stu-id="cee64-105">Indicates the current assignment state of the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cee64-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="cee64-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cee64-107">dispidTaskState</span><span class="sxs-lookup"><span data-stu-id="cee64-107">dispidTaskState</span></span>  <br/> |
|<span data-ttu-id="cee64-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cee64-108">Property set:</span></span>  <br/> |<span data-ttu-id="cee64-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="cee64-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="cee64-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cee64-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cee64-111">0x00008113</span><span class="sxs-lookup"><span data-stu-id="cee64-111">0x00008113</span></span>  <br/> |
|<span data-ttu-id="cee64-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cee64-112">Data type:</span></span>  <br/> |<span data-ttu-id="cee64-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cee64-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cee64-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cee64-114">Area:</span></span>  <br/> |<span data-ttu-id="cee64-115">任务</span><span class="sxs-lookup"><span data-stu-id="cee64-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cee64-116">备注</span><span class="sxs-lookup"><span data-stu-id="cee64-116">Remarks</span></span>

<span data-ttu-id="cee64-117">此属性的值必须是下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="cee64-117">The value of this property must be one of the following.</span></span>
  
|<span data-ttu-id="cee64-118">**值**</span><span class="sxs-lookup"><span data-stu-id="cee64-118">**Value**</span></span>|<span data-ttu-id="cee64-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="cee64-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cee64-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="cee64-120">0x00000000</span></span>  <br/> |<span data-ttu-id="cee64-121">创建此任务是为了与一个任务嵌入在任务拒绝，但找不到本地对应。</span><span class="sxs-lookup"><span data-stu-id="cee64-121">This task was created to correspond to a task that was embedded in a task rejection but could not be found locally.</span></span>  <br/> |
|<span data-ttu-id="cee64-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="cee64-122">0x00000001</span></span>  <br/> |<span data-ttu-id="cee64-123">未分配的任务。</span><span class="sxs-lookup"><span data-stu-id="cee64-123">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="cee64-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="cee64-124">0x00000002</span></span>  <br/> |<span data-ttu-id="cee64-125">此任务是任务的分配的任务代理人的副本。</span><span class="sxs-lookup"><span data-stu-id="cee64-125">The task is the task assignee's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="cee64-126">0x00000003</span><span class="sxs-lookup"><span data-stu-id="cee64-126">0x00000003</span></span>  <br/> |<span data-ttu-id="cee64-127">此任务是任务的分配的任务分配人的副本。</span><span class="sxs-lookup"><span data-stu-id="cee64-127">The task is the task assigner's copy of an assigned task.</span></span>  <br/> |
|<span data-ttu-id="cee64-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="cee64-128">0x00000004</span></span>  <br/> |<span data-ttu-id="cee64-129">此任务是拒绝任务的任务分配人的副本。</span><span class="sxs-lookup"><span data-stu-id="cee64-129">The task is the task assigner's copy of a rejected task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="cee64-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="cee64-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cee64-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="cee64-131">Protocol specifications</span></span>

<span data-ttu-id="cee64-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cee64-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cee64-133">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cee64-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cee64-134">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cee64-134">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cee64-135">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="cee64-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="cee64-136">[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cee64-136">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cee64-137">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="cee64-137">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="cee64-138">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cee64-138">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cee64-139">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="cee64-139">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="cee64-140">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cee64-140">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cee64-141">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="cee64-141">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cee64-142">头文件</span><span class="sxs-lookup"><span data-stu-id="cee64-142">Header files</span></span>

<span data-ttu-id="cee64-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cee64-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="cee64-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cee64-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cee64-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cee64-145">See also</span></span>



[<span data-ttu-id="cee64-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cee64-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cee64-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cee64-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cee64-148">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cee64-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cee64-149">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cee64-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

