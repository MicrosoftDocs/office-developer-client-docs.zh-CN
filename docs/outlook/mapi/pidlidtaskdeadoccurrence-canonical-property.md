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
ms.openlocfilehash: 14207e513e935a296ff9b953b92ab1ab9ab41fd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777060"
---
# <a name="pidlidtaskdeadoccurrence-canonical-property"></a><span data-ttu-id="2a283-103">PidLidTaskDeadOccurrence 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a283-103">PidLidTaskDeadOccurrence Canonical Property</span></span>

  
  
<span data-ttu-id="2a283-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2a283-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2a283-105">指示是否必须生成新的匹配项。</span><span class="sxs-lookup"><span data-stu-id="2a283-105">Indicates whether new occurrences must be generated.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2a283-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2a283-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2a283-107">dispidTaskDeadOccur</span><span class="sxs-lookup"><span data-stu-id="2a283-107">dispidTaskDeadOccur</span></span>  <br/> |
|<span data-ttu-id="2a283-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2a283-108">Property set:</span></span>  <br/> |<span data-ttu-id="2a283-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="2a283-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="2a283-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2a283-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2a283-111">0x00008109</span><span class="sxs-lookup"><span data-stu-id="2a283-111">0x00008109</span></span>  <br/> |
|<span data-ttu-id="2a283-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2a283-112">Data type:</span></span>  <br/> |<span data-ttu-id="2a283-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2a283-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="2a283-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2a283-114">Area:</span></span>  <br/> |<span data-ttu-id="2a283-115">Task</span><span class="sxs-lookup"><span data-stu-id="2a283-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a283-116">说明</span><span class="sxs-lookup"><span data-stu-id="2a283-116">Remarks</span></span>

<span data-ttu-id="2a283-117">定期模式时不再有效其最后一个实例是在过去或其指定的实例数已生成。</span><span class="sxs-lookup"><span data-stu-id="2a283-117">A recurrence pattern is no longer in effect when its final instance is in the past or its specified number of instances has been generated.</span></span> <span data-ttu-id="2a283-118">客户端将该属性设置为 false，则新任务或为 TRUE 时，它将生成一个周期性任务的最后一个实例。</span><span class="sxs-lookup"><span data-stu-id="2a283-118">The client sets this property to FALSE for a new task or to TRUE when it generates the last instance of a recurring task.</span></span> <span data-ttu-id="2a283-119">复制要生成的新实例的任务时，此属性设置为 TRUE 的副本，即已完成的实例上。</span><span class="sxs-lookup"><span data-stu-id="2a283-119">When you copy a task to generate a new instance, this property is set to TRUE on the copy, which is the completed instance.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2a283-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="2a283-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2a283-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="2a283-121">Protocol specifications</span></span>

<span data-ttu-id="2a283-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a283-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a283-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2a283-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2a283-124">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a283-124">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2a283-125">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="2a283-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="2a283-126">头文件</span><span class="sxs-lookup"><span data-stu-id="2a283-126">Header files</span></span>

<span data-ttu-id="2a283-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2a283-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="2a283-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2a283-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2a283-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a283-129">See also</span></span>



[<span data-ttu-id="2a283-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2a283-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2a283-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a283-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2a283-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2a283-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2a283-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2a283-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

