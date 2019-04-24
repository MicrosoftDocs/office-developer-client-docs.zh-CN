---
title: PidLidPercentComplete 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidLidPercentComplete
api_type:
- COM
ms.assetid: e63792b1-9580-4702-a6d7-dd3ae5007a4a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 870b4e0edb360ac36525f94b0605af930eee8fa3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357972"
---
# <a name="pidlidpercentcomplete-canonical-property"></a><span data-ttu-id="d75cb-103">PidLidPercentComplete 规范属性</span><span class="sxs-lookup"><span data-stu-id="d75cb-103">PidLidPercentComplete Canonical Property</span></span>

  
  
<span data-ttu-id="d75cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d75cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d75cb-105">指示用户对任务所做的进度。</span><span class="sxs-lookup"><span data-stu-id="d75cb-105">Indicates the progress the user has made on a task.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d75cb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d75cb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d75cb-107">dispidPercentComplete</span><span class="sxs-lookup"><span data-stu-id="d75cb-107">dispidPercentComplete</span></span>  <br/> |
|<span data-ttu-id="d75cb-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="d75cb-108">Property set:</span></span>  <br/> |<span data-ttu-id="d75cb-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="d75cb-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="d75cb-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="d75cb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d75cb-111">0x00008102</span><span class="sxs-lookup"><span data-stu-id="d75cb-111">0x00008102</span></span>  <br/> |
|<span data-ttu-id="d75cb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d75cb-112">Data type:</span></span>  <br/> |<span data-ttu-id="d75cb-113">PT_R8</span><span class="sxs-lookup"><span data-stu-id="d75cb-113">PT_R8</span></span>  <br/> |
|<span data-ttu-id="d75cb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d75cb-114">Area:</span></span>  <br/> |<span data-ttu-id="d75cb-115">任务</span><span class="sxs-lookup"><span data-stu-id="d75cb-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d75cb-116">注解</span><span class="sxs-lookup"><span data-stu-id="d75cb-116">Remarks</span></span>

<span data-ttu-id="d75cb-117">此属性的值必须是大于或等于0.0 且小于或等于1.0 的数字, 其中1.0 表示工作已完成, 而0.0 指示工作尚未开始。</span><span class="sxs-lookup"><span data-stu-id="d75cb-117">The value of this property must be a number greater than or equal to 0.0 and less than or equal to 1.0, where 1.0 indicates that work is completed and 0.0 indicates that work has not begun.</span></span>
  
<span data-ttu-id="d75cb-118">对于时间标记的邮件对象, 如果对象已被标记为 "已完成", 则必须将此属性的值设置为 1.0, 否则应设置为0.0。</span><span class="sxs-lookup"><span data-stu-id="d75cb-118">For a time-flagged message object, the value of this property must be set to 1.0 if the object is flagged completed, and should be set to 0.0 otherwise.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d75cb-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="d75cb-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d75cb-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="d75cb-120">Protocol specifications</span></span>

<span data-ttu-id="d75cb-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d75cb-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d75cb-123">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-124">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="d75cb-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="d75cb-125">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-126">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d75cb-126">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="d75cb-127">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-127">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-128">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="d75cb-128">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="d75cb-129">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-129">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-130">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="d75cb-130">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="d75cb-131">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d75cb-131">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d75cb-132">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="d75cb-132">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d75cb-133">头文件</span><span class="sxs-lookup"><span data-stu-id="d75cb-133">Header files</span></span>

<span data-ttu-id="d75cb-134">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d75cb-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="d75cb-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d75cb-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d75cb-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d75cb-136">See also</span></span>



[<span data-ttu-id="d75cb-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d75cb-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d75cb-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d75cb-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d75cb-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d75cb-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d75cb-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d75cb-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

