---
title: PidLidTaskFRecurring 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskFRecurring
api_type:
- COM
ms.assetid: 47c9ccbb-161c-4829-8ffb-201f3b54cd45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 94ec76d3247421f163775245c43ee68e6f9b560b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569083"
---
# <a name="pidlidtaskfrecurring-canonical-property"></a><span data-ttu-id="bb1ac-103">PidLidTaskFRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb1ac-103">PidLidTaskFRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="bb1ac-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb1ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb1ac-105">指示任务是否包含的定期模式。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-105">Indicates whether the task includes a recurrence pattern.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bb1ac-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bb1ac-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb1ac-107">dispidTaskFRecur</span><span class="sxs-lookup"><span data-stu-id="bb1ac-107">dispidTaskFRecur</span></span>  <br/> |
|<span data-ttu-id="bb1ac-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="bb1ac-108">Property set:</span></span>  <br/> |<span data-ttu-id="bb1ac-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="bb1ac-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="bb1ac-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="bb1ac-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="bb1ac-111">0x00008126</span><span class="sxs-lookup"><span data-stu-id="bb1ac-111">0x00008126</span></span>  <br/> |
|<span data-ttu-id="bb1ac-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb1ac-112">Data type:</span></span>  <br/> |<span data-ttu-id="bb1ac-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="bb1ac-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="bb1ac-114">区域：</span><span class="sxs-lookup"><span data-stu-id="bb1ac-114">Area:</span></span>  <br/> |<span data-ttu-id="bb1ac-115">Task</span><span class="sxs-lookup"><span data-stu-id="bb1ac-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb1ac-116">注解</span><span class="sxs-lookup"><span data-stu-id="bb1ac-116">Remarks</span></span>

<span data-ttu-id="bb1ac-117">如果不设置此属性，则假定的默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-117">If this property is left unset, a default value of FALSE is assumed.</span></span> <span data-ttu-id="bb1ac-118">如果其设置为 true，则**dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 和**dispidTaskDeadOccur** ([PidLidTaskDeadOccurrence](pidlidtaskdeadoccurrence-canonical-property.md)) 属性还必须设置为[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)中指定。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-118">If it is set to TRUE, the **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) and **dispidTaskDeadOccur** ([PidLidTaskDeadOccurrence](pidlidtaskdeadoccurrence-canonical-property.md)) properties must also be set as specified in [[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bb1ac-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb1ac-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb1ac-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb1ac-120">Protocol specifications</span></span>

<span data-ttu-id="bb1ac-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb1ac-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb1ac-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bb1ac-123">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb1ac-123">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb1ac-124">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bb1ac-125">头文件</span><span class="sxs-lookup"><span data-stu-id="bb1ac-125">Header files</span></span>

<span data-ttu-id="bb1ac-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb1ac-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb1ac-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb1ac-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb1ac-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb1ac-128">See also</span></span>



[<span data-ttu-id="bb1ac-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb1ac-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb1ac-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb1ac-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb1ac-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bb1ac-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb1ac-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb1ac-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

