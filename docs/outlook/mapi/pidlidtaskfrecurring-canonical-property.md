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
ms.openlocfilehash: aec9dd328e802e185c870d3ecd94cbd1d10ac67d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303050"
---
# <a name="pidlidtaskfrecurring-canonical-property"></a><span data-ttu-id="54b6b-103">PidLidTaskFRecurring 规范属性</span><span class="sxs-lookup"><span data-stu-id="54b6b-103">PidLidTaskFRecurring Canonical Property</span></span>

  
  
<span data-ttu-id="54b6b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54b6b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54b6b-105">指示任务是否包含定期模式。</span><span class="sxs-lookup"><span data-stu-id="54b6b-105">Indicates whether the task includes a recurrence pattern.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="54b6b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="54b6b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="54b6b-107">dispidTaskFRecur</span><span class="sxs-lookup"><span data-stu-id="54b6b-107">dispidTaskFRecur</span></span>  <br/> |
|<span data-ttu-id="54b6b-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="54b6b-108">Property set:</span></span>  <br/> |<span data-ttu-id="54b6b-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="54b6b-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="54b6b-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="54b6b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="54b6b-111">0x00008126</span><span class="sxs-lookup"><span data-stu-id="54b6b-111">0x00008126</span></span>  <br/> |
|<span data-ttu-id="54b6b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="54b6b-112">Data type:</span></span>  <br/> |<span data-ttu-id="54b6b-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="54b6b-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="54b6b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="54b6b-114">Area:</span></span>  <br/> |<span data-ttu-id="54b6b-115">任务</span><span class="sxs-lookup"><span data-stu-id="54b6b-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="54b6b-116">备注</span><span class="sxs-lookup"><span data-stu-id="54b6b-116">Remarks</span></span>

<span data-ttu-id="54b6b-117">如果此属性未设置，则假定默认值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="54b6b-117">If this property is left unset, a default value of FALSE is assumed.</span></span> <span data-ttu-id="54b6b-118">如果设置为 TRUE， **则 dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) 和 **dispidTaskDeadOccur** ([PidLidTaskDeadOccurrence](pidlidtaskdeadoccurrence-canonical-property.md)) 属性也必须设置为 [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)中指定的。</span><span class="sxs-lookup"><span data-stu-id="54b6b-118">If it is set to TRUE, the **dispidTaskRecur** ([PidLidTaskRecurrence](pidlidtaskrecurrence-canonical-property.md)) and **dispidTaskDeadOccur** ([PidLidTaskDeadOccurrence](pidlidtaskdeadoccurrence-canonical-property.md)) properties must also be set as specified in [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="54b6b-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="54b6b-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="54b6b-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="54b6b-120">Protocol specifications</span></span>

<span data-ttu-id="54b6b-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54b6b-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54b6b-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="54b6b-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="54b6b-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="54b6b-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="54b6b-124">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="54b6b-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="54b6b-125">头文件</span><span class="sxs-lookup"><span data-stu-id="54b6b-125">Header files</span></span>

<span data-ttu-id="54b6b-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="54b6b-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="54b6b-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="54b6b-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="54b6b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54b6b-128">See also</span></span>



[<span data-ttu-id="54b6b-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="54b6b-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="54b6b-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="54b6b-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="54b6b-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="54b6b-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="54b6b-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="54b6b-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

