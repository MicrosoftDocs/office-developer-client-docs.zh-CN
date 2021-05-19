---
title: PidLidTaskAssigner 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAssigner
api_type:
- COM
ms.assetid: f7047e4e-0fb3-476b-9568-8f1135e6d970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ef5f78fa36632227311d037ee61085c677920fb1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340087"
---
# <a name="pidlidtaskassigner-canonical-property"></a><span data-ttu-id="24de0-103">PidLidTaskAssigner 规范属性</span><span class="sxs-lookup"><span data-stu-id="24de0-103">PidLidTaskAssigner Canonical Property</span></span>

  
  
<span data-ttu-id="24de0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24de0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="24de0-105">命名上次分配了该任务的用户。</span><span class="sxs-lookup"><span data-stu-id="24de0-105">Names the user who was last assigned the task.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="24de0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24de0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24de0-107">dispidTaskDelegator</span><span class="sxs-lookup"><span data-stu-id="24de0-107">dispidTaskDelegator</span></span>  <br/> |
|<span data-ttu-id="24de0-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="24de0-108">Property set:</span></span>  <br/> |<span data-ttu-id="24de0-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="24de0-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="24de0-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="24de0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="24de0-111">0x00008121</span><span class="sxs-lookup"><span data-stu-id="24de0-111">0x00008121</span></span>  <br/> |
|<span data-ttu-id="24de0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24de0-112">Data type:</span></span>  <br/> |<span data-ttu-id="24de0-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="24de0-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="24de0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="24de0-114">Area:</span></span>  <br/> |<span data-ttu-id="24de0-115">任务</span><span class="sxs-lookup"><span data-stu-id="24de0-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24de0-116">备注</span><span class="sxs-lookup"><span data-stu-id="24de0-116">Remarks</span></span>

<span data-ttu-id="24de0-117">如果尚未分配该任务，则此属性将取消设置。</span><span class="sxs-lookup"><span data-stu-id="24de0-117">If the task has not been assigned, this property is left unset.</span></span> <span data-ttu-id="24de0-118">由于客户端在任务接受者收到任务请求后设置此属性，因此不会在任务分配者的任务副本上设置该属性。</span><span class="sxs-lookup"><span data-stu-id="24de0-118">Because the client sets this property after the task assignee receives a task request, the property will not be set on the task assigner's copy of the task.</span></span> <span data-ttu-id="24de0-119">当客户端在 **dispidTaskMyDelegators** ([PidLidTaskAssigners](pidlidtaskassigners-canonical-property.md)) 属性中的任务分配者列表中添加或删除任务分配者时 **，dispidTaskDelegator** ([PidLidTaskAssigner](pidlidtaskassigner-canonical-property.md)) 属性必须设置为已添加或删除的任务分配者。</span><span class="sxs-lookup"><span data-stu-id="24de0-119">When the client adds or removes a task assigner from the task assigner list in the **dispidTaskMyDelegators** ([PidLidTaskAssigners](pidlidtaskassigners-canonical-property.md)) property, the **dispidTaskDelegator** ([PidLidTaskAssigner](pidlidtaskassigner-canonical-property.md)) property must be set to the added or removed task assigner.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="24de0-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="24de0-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24de0-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="24de0-121">Protocol specifications</span></span>

<span data-ttu-id="24de0-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24de0-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24de0-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="24de0-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="24de0-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24de0-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24de0-125">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="24de0-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24de0-126">头文件</span><span class="sxs-lookup"><span data-stu-id="24de0-126">Header files</span></span>

<span data-ttu-id="24de0-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="24de0-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="24de0-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24de0-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24de0-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24de0-129">See also</span></span>



[<span data-ttu-id="24de0-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24de0-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24de0-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24de0-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24de0-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24de0-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24de0-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24de0-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

