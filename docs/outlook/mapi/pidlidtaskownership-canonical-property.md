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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45fcba3f18aeb9092b71e28a6b68e42ad1abe77d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332107"
---
# <a name="pidlidtaskownership-canonical-property"></a><span data-ttu-id="ce54e-103">PidLidTaskOwnership 规范属性</span><span class="sxs-lookup"><span data-stu-id="ce54e-103">PidLidTaskOwnership Canonical Property</span></span>

  
  
<span data-ttu-id="ce54e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce54e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce54e-105">指示当前用户相对于任务的角色。</span><span class="sxs-lookup"><span data-stu-id="ce54e-105">Indicates the role of the current user relative to the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ce54e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ce54e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ce54e-107">dispidTaskOwnership</span><span class="sxs-lookup"><span data-stu-id="ce54e-107">dispidTaskOwnership</span></span>  <br/> |
|<span data-ttu-id="ce54e-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="ce54e-108">Property set:</span></span>  <br/> |<span data-ttu-id="ce54e-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="ce54e-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="ce54e-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="ce54e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ce54e-111">0x00008129</span><span class="sxs-lookup"><span data-stu-id="ce54e-111">0x00008129</span></span>  <br/> |
|<span data-ttu-id="ce54e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ce54e-112">Data type:</span></span>  <br/> |<span data-ttu-id="ce54e-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ce54e-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ce54e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ce54e-114">Area:</span></span>  <br/> |<span data-ttu-id="ce54e-115">任务</span><span class="sxs-lookup"><span data-stu-id="ce54e-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ce54e-116">注解</span><span class="sxs-lookup"><span data-stu-id="ce54e-116">Remarks</span></span>

<span data-ttu-id="ce54e-117">此属性必须为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="ce54e-117">This property must be one of the following values.</span></span>
  
|<span data-ttu-id="ce54e-118">**Value**</span><span class="sxs-lookup"><span data-stu-id="ce54e-118">**Value**</span></span>|<span data-ttu-id="ce54e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce54e-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce54e-120">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ce54e-120">0x00000000</span></span>  <br/> |<span data-ttu-id="ce54e-121">未分配任务。</span><span class="sxs-lookup"><span data-stu-id="ce54e-121">The task is not assigned.</span></span>  <br/> |
|<span data-ttu-id="ce54e-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ce54e-122">0x00000001</span></span>  <br/> |<span data-ttu-id="ce54e-123">任务是任务 assigner 的任务副本。</span><span class="sxs-lookup"><span data-stu-id="ce54e-123">The task is the task assigner's copy of the task.</span></span>  <br/> |
|<span data-ttu-id="ce54e-124">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ce54e-124">0x00000002</span></span>  <br/> |<span data-ttu-id="ce54e-125">任务是任务受理人的任务副本。</span><span class="sxs-lookup"><span data-stu-id="ce54e-125">The task is the task assignee's copy of the task.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ce54e-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="ce54e-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ce54e-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="ce54e-127">Protocol specifications</span></span>

<span data-ttu-id="ce54e-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce54e-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ce54e-129">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ce54e-129">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ce54e-130">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce54e-130">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ce54e-131">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="ce54e-131">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ce54e-132">头文件</span><span class="sxs-lookup"><span data-stu-id="ce54e-132">Header files</span></span>

<span data-ttu-id="ce54e-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ce54e-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="ce54e-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ce54e-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ce54e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce54e-135">See also</span></span>



[<span data-ttu-id="ce54e-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ce54e-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ce54e-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ce54e-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ce54e-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ce54e-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ce54e-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ce54e-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

