---
title: PidLidTaskDeadOccurrence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskDeadOccurrence
api_type:
- COM
ms.assetid: e78287ff-f8cc-45ea-8da8-e7a7359e651c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0b740368aae43549e81cf3f4f6de40526c505b6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303428"
---
# <a name="pidlidtaskdeadoccurrence-canonical-property"></a><span data-ttu-id="88ed5-103">PidLidTaskDeadOccurrence 规范属性</span><span class="sxs-lookup"><span data-stu-id="88ed5-103">PidLidTaskDeadOccurrence Canonical Property</span></span>

  
  
<span data-ttu-id="88ed5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88ed5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88ed5-105">指示是否必须生成新的事件。</span><span class="sxs-lookup"><span data-stu-id="88ed5-105">Indicates whether new occurrences must be generated.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88ed5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88ed5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88ed5-107">dispidTaskDeadOccur</span><span class="sxs-lookup"><span data-stu-id="88ed5-107">dispidTaskDeadOccur</span></span>  <br/> |
|<span data-ttu-id="88ed5-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="88ed5-108">Property set:</span></span>  <br/> |<span data-ttu-id="88ed5-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="88ed5-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="88ed5-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="88ed5-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="88ed5-111">0x00008109</span><span class="sxs-lookup"><span data-stu-id="88ed5-111">0x00008109</span></span>  <br/> |
|<span data-ttu-id="88ed5-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88ed5-112">Data type:</span></span>  <br/> |<span data-ttu-id="88ed5-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="88ed5-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="88ed5-114">区域：</span><span class="sxs-lookup"><span data-stu-id="88ed5-114">Area:</span></span>  <br/> |<span data-ttu-id="88ed5-115">任务</span><span class="sxs-lookup"><span data-stu-id="88ed5-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88ed5-116">注解</span><span class="sxs-lookup"><span data-stu-id="88ed5-116">Remarks</span></span>

<span data-ttu-id="88ed5-117">定期模式在其最终实例过期或其指定的实例数已生成时不再有效。</span><span class="sxs-lookup"><span data-stu-id="88ed5-117">A recurrence pattern is no longer in effect when its final instance is in the past or its specified number of instances has been generated.</span></span> <span data-ttu-id="88ed5-118">客户端将新任务的该属性设置为 FALSE, 或者在生成定期任务的最后一个实例时将该属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="88ed5-118">The client sets this property to FALSE for a new task or to TRUE when it generates the last instance of a recurring task.</span></span> <span data-ttu-id="88ed5-119">复制任务以生成新实例时, 副本上的此属性设置为 TRUE, 即已完成的实例。</span><span class="sxs-lookup"><span data-stu-id="88ed5-119">When you copy a task to generate a new instance, this property is set to TRUE on the copy, which is the completed instance.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="88ed5-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="88ed5-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="88ed5-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="88ed5-121">Protocol specifications</span></span>

<span data-ttu-id="88ed5-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88ed5-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88ed5-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="88ed5-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="88ed5-124">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88ed5-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88ed5-125">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="88ed5-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="88ed5-126">头文件</span><span class="sxs-lookup"><span data-stu-id="88ed5-126">Header files</span></span>

<span data-ttu-id="88ed5-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="88ed5-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="88ed5-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88ed5-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88ed5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88ed5-129">See also</span></span>



[<span data-ttu-id="88ed5-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88ed5-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88ed5-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88ed5-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88ed5-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88ed5-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88ed5-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88ed5-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

