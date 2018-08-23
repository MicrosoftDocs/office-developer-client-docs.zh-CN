---
title: PidLidTaskDateCompleted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskDateCompleted
api_type:
- COM
ms.assetid: ae384529-55e2-4da1-9a41-acc292591a7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97d541279f052099498cdf7bfd374a95238a376d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584217"
---
# <a name="pidlidtaskdatecompleted-canonical-property"></a><span data-ttu-id="fb72e-103">PidLidTaskDateCompleted 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb72e-103">PidLidTaskDateCompleted Canonical Property</span></span>

  
  
<span data-ttu-id="fb72e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb72e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb72e-105">指定当用户完成任务的日期。</span><span class="sxs-lookup"><span data-stu-id="fb72e-105">Specifies the date when the user completes the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fb72e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fb72e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fb72e-107">dispidTaskDateCompleted</span><span class="sxs-lookup"><span data-stu-id="fb72e-107">dispidTaskDateCompleted</span></span>  <br/> |
|<span data-ttu-id="fb72e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="fb72e-108">Property set:</span></span>  <br/> |<span data-ttu-id="fb72e-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="fb72e-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="fb72e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="fb72e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="fb72e-111">0x0000810F</span><span class="sxs-lookup"><span data-stu-id="fb72e-111">0x0000810F</span></span>  <br/> |
|<span data-ttu-id="fb72e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fb72e-112">Data type:</span></span>  <br/> |<span data-ttu-id="fb72e-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="fb72e-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="fb72e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="fb72e-114">Area:</span></span>  <br/> |<span data-ttu-id="fb72e-115">Task</span><span class="sxs-lookup"><span data-stu-id="fb72e-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fb72e-116">注解</span><span class="sxs-lookup"><span data-stu-id="fb72e-116">Remarks</span></span>

<span data-ttu-id="fb72e-117">如果设置，此属性必须具有午夜时间组件的本地时区转换为协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="fb72e-117">If set, this property must have a time component of midnight in the local time zone, converted to Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fb72e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="fb72e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fb72e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="fb72e-119">Protocol specifications</span></span>

<span data-ttu-id="fb72e-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb72e-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fb72e-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="fb72e-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fb72e-122">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb72e-122">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fb72e-123">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="fb72e-123">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="fb72e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="fb72e-124">Header files</span></span>

<span data-ttu-id="fb72e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fb72e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="fb72e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fb72e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fb72e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb72e-127">See also</span></span>



[<span data-ttu-id="fb72e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fb72e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fb72e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb72e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fb72e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fb72e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fb72e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fb72e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

