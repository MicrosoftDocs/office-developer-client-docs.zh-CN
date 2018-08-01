---
title: PidLidTaskOwnership 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOwnership
api_type:
- COM
ms.assetid: 805dcb6c-f405-4c4d-8bca-af4bd9cd44fa
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 17f3ac0c5cd6005329212d0dcb458b37bb75f41d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777111"
---
# <a name="pidlidtaskownership-canonical-property"></a><span data-ttu-id="b3fb1-103">PidLidTaskOwnership 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3fb1-103">PidLidTaskOwnership Canonical Property</span></span>

  
  
<span data-ttu-id="b3fb1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b3fb1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b3fb1-105">指示相对于任务的当前用户的角色。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-105">Indicates the role of the current user relative to the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b3fb1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b3fb1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b3fb1-107">dispidTaskOwnership</span><span class="sxs-lookup"><span data-stu-id="b3fb1-107">dispidTaskOwnership</span></span>  <br/> |
|<span data-ttu-id="b3fb1-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b3fb1-108">Property set:</span></span>  <br/> |<span data-ttu-id="b3fb1-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="b3fb1-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="b3fb1-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b3fb1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b3fb1-111">0x00008129</span><span class="sxs-lookup"><span data-stu-id="b3fb1-111">0x00008129</span></span>  <br/> |
|<span data-ttu-id="b3fb1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b3fb1-112">Data type:</span></span>  <br/> |<span data-ttu-id="b3fb1-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b3fb1-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b3fb1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b3fb1-114">Area:</span></span>  <br/> |<span data-ttu-id="b3fb1-115">任务</span><span class="sxs-lookup"><span data-stu-id="b3fb1-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b3fb1-116">备注</span><span class="sxs-lookup"><span data-stu-id="b3fb1-116">Remarks</span></span>

<span data-ttu-id="b3fb1-117">此属性必须为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-117">This property must be one of the following values.</span></span>
  
|<span data-ttu-id="b3fb1-118">**值**</span><span class="sxs-lookup"><span data-stu-id="b3fb1-118">**Value**</span></span>|<span data-ttu-id="b3fb1-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b3fb1-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3fb1-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b3fb1-120">0x00000000</span></span>  <br/> |<span data-ttu-id="b3fb1-121">未分配的任务。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="b3fb1-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b3fb1-122">0x00000001</span></span>  <br/> |<span data-ttu-id="b3fb1-123">此任务是任务的任务分配人的副本。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-123">The task is the task assigner's copy of the task.</span></span>  <br/> |
|<span data-ttu-id="b3fb1-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b3fb1-124">0x00000002</span></span>  <br/> |<span data-ttu-id="b3fb1-125">此任务是任务的任务代理人的副本。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-125">The task is the task assignee's copy of the task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b3fb1-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="b3fb1-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b3fb1-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="b3fb1-127">Protocol specifications</span></span>

<span data-ttu-id="b3fb1-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3fb1-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3fb1-129">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b3fb1-130">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3fb1-130">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3fb1-131">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-131">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b3fb1-132">头文件</span><span class="sxs-lookup"><span data-stu-id="b3fb1-132">Header files</span></span>

<span data-ttu-id="b3fb1-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b3fb1-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="b3fb1-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b3fb1-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3fb1-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3fb1-135">See also</span></span>



[<span data-ttu-id="b3fb1-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b3fb1-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b3fb1-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3fb1-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b3fb1-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3fb1-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b3fb1-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3fb1-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
