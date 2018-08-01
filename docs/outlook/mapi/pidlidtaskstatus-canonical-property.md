---
title: PidLidTaskStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStatus
api_type:
- COM
ms.assetid: 809776b7-ff00-4a52-84b9-8b5fb5f5c3e3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e8ca8d7a82360c1f96448b08c9eda18be502b9f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777127"
---
# <a name="pidlidtaskstatus-canonical-property"></a><span data-ttu-id="99b82-103">PidLidTaskStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="99b82-103">PidLidTaskStatus Canonical Property</span></span>

  
  
<span data-ttu-id="99b82-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="99b82-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="99b82-105">指定任务的用户的进度的状态。</span><span class="sxs-lookup"><span data-stu-id="99b82-105">Specifies the status of the user's progress on the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="99b82-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="99b82-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="99b82-107">dispidTaskStatus</span><span class="sxs-lookup"><span data-stu-id="99b82-107">dispidTaskStatus</span></span>  <br/> |
|<span data-ttu-id="99b82-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="99b82-108">Property set:</span></span>  <br/> |<span data-ttu-id="99b82-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="99b82-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="99b82-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="99b82-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="99b82-111">0x00008101</span><span class="sxs-lookup"><span data-stu-id="99b82-111">0x00008101</span></span>  <br/> |
|<span data-ttu-id="99b82-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="99b82-112">Data type:</span></span>  <br/> |<span data-ttu-id="99b82-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="99b82-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="99b82-114">区域：</span><span class="sxs-lookup"><span data-stu-id="99b82-114">Area:</span></span>  <br/> |<span data-ttu-id="99b82-115">Task</span><span class="sxs-lookup"><span data-stu-id="99b82-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="99b82-116">说明</span><span class="sxs-lookup"><span data-stu-id="99b82-116">Remarks</span></span>

<span data-ttu-id="99b82-117">此属性的值必须设置为下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="99b82-117">The value of this property must be set to one of the following.</span></span>
  
|<span data-ttu-id="99b82-118">**值**</span><span class="sxs-lookup"><span data-stu-id="99b82-118">**Value**</span></span>|<span data-ttu-id="99b82-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="99b82-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99b82-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="99b82-120">0x00000000</span></span>  <br/> |<span data-ttu-id="99b82-121">用户任务尚未开始工作。</span><span class="sxs-lookup"><span data-stu-id="99b82-121">The user has not started work on the task.</span></span> <span data-ttu-id="99b82-122">如果设置此值，则**dispidPercentComplete** ([PidLidPercentComplete](pidlidpercentcomplete-canonical-property.md)) 必须是 0.0。</span><span class="sxs-lookup"><span data-stu-id="99b82-122">If this value is set, **dispidPercentComplete** ([PidLidPercentComplete](pidlidpercentcomplete-canonical-property.md)) must be 0.0.</span></span>  <br/> |
|<span data-ttu-id="99b82-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="99b82-123">0x00000001</span></span>  <br/> |<span data-ttu-id="99b82-124">正在执行此任务的用户的工作。</span><span class="sxs-lookup"><span data-stu-id="99b82-124">The user's work on this task is in progress.</span></span> <span data-ttu-id="99b82-125">如果设置此值，则**dispidPercentComplete**必须大于 0.0 且小于 1.0。</span><span class="sxs-lookup"><span data-stu-id="99b82-125">If this value is set, **dispidPercentComplete** must be greater than 0.0 and less than 1.0.</span></span>  <br/> |
|<span data-ttu-id="99b82-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="99b82-126">0x00000002</span></span>  <br/> |<span data-ttu-id="99b82-127">完成此任务的用户的工作。</span><span class="sxs-lookup"><span data-stu-id="99b82-127">The user's work on this task is complete.</span></span> <span data-ttu-id="99b82-128">如果设置此值， **dispidPercentComplete**必须是 1.0、 **dispidTaskDateCompleted** ([PidLidTaskDateCompleted](pidlidtaskdatecompleted-canonical-property.md)) 必须是当前日期，和**dispidTaskComplete** ([PidLidTaskComplete](pidlidtaskcomplete-canonical-property.md)) 必须为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="99b82-128">If this value is set, **dispidPercentComplete** must be 1.0, **dispidTaskDateCompleted** ([PidLidTaskDateCompleted](pidlidtaskdatecompleted-canonical-property.md)) must be the current date, and **dispidTaskComplete** ([PidLidTaskComplete](pidlidtaskcomplete-canonical-property.md)) must be TRUE.</span></span>  <br/> |
|<span data-ttu-id="99b82-129">0x00000003</span><span class="sxs-lookup"><span data-stu-id="99b82-129">0x00000003</span></span>  <br/> |<span data-ttu-id="99b82-130">用户正在等待其他人。</span><span class="sxs-lookup"><span data-stu-id="99b82-130">The user is waiting on somebody else.</span></span>  <br/> |
|<span data-ttu-id="99b82-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="99b82-131">0x00000004</span></span>  <br/> |<span data-ttu-id="99b82-132">用户具有延迟任务的工时。</span><span class="sxs-lookup"><span data-stu-id="99b82-132">The user has deferred work on the task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="99b82-133">相关资源</span><span class="sxs-lookup"><span data-stu-id="99b82-133">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="99b82-134">协议规范</span><span class="sxs-lookup"><span data-stu-id="99b82-134">Protocol specifications</span></span>

<span data-ttu-id="99b82-135">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-135">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-136">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="99b82-136">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="99b82-137">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-137">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-138">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="99b82-138">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="99b82-139">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-139">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-140">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="99b82-140">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="99b82-141">[[MS OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-141">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-142">指定的属性和用于创建和邮箱中查找的特殊文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="99b82-142">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
<span data-ttu-id="99b82-143">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-143">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-144">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="99b82-144">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="99b82-145">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-145">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-146">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="99b82-146">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="99b82-147">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99b82-147">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99b82-148">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="99b82-148">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="99b82-149">头文件</span><span class="sxs-lookup"><span data-stu-id="99b82-149">Header files</span></span>

<span data-ttu-id="99b82-150">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="99b82-150">Mapidefs.h</span></span>
  
> <span data-ttu-id="99b82-151">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="99b82-151">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="99b82-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99b82-152">See also</span></span>



[<span data-ttu-id="99b82-153">PidLidPercentComplete 规范属性</span><span class="sxs-lookup"><span data-stu-id="99b82-153">PidLidPercentComplete Canonical Property</span></span>](pidlidpercentcomplete-canonical-property.md)
  
[<span data-ttu-id="99b82-154">PidLidTaskDateCompleted 规范属性</span><span class="sxs-lookup"><span data-stu-id="99b82-154">PidLidTaskDateCompleted Canonical Property</span></span>](pidlidtaskdatecompleted-canonical-property.md)
  
[<span data-ttu-id="99b82-155">PidLidTaskComplete 规范属性</span><span class="sxs-lookup"><span data-stu-id="99b82-155">PidLidTaskComplete Canonical Property</span></span>](pidlidtaskcomplete-canonical-property.md)


[<span data-ttu-id="99b82-156">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="99b82-156">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="99b82-157">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="99b82-157">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="99b82-158">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="99b82-158">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="99b82-159">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="99b82-159">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

