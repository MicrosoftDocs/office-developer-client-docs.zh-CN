---
title: PidLidTaskLastUser 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastUser
api_type:
- COM
ms.assetid: 914c55e9-cb36-46a4-b5ee-382413fa25f9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6dc2bcf2003ee16fa4a6c66689b6af79653e2d04
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777088"
---
# <a name="pidlidtasklastuser-canonical-property"></a><span data-ttu-id="68e8b-103">PidLidTaskLastUser 规范属性</span><span class="sxs-lookup"><span data-stu-id="68e8b-103">PidLidTaskLastUser Canonical Property</span></span>

  
  
<span data-ttu-id="68e8b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="68e8b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="68e8b-105">名称最新用户的任务所有者。</span><span class="sxs-lookup"><span data-stu-id="68e8b-105">Names the most recent user who was the task owner.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="68e8b-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="68e8b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="68e8b-107">dispidTaskLastUser</span><span class="sxs-lookup"><span data-stu-id="68e8b-107">dispidTaskLastUser</span></span>  <br/> |
|<span data-ttu-id="68e8b-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="68e8b-108">Property set:</span></span>  <br/> |<span data-ttu-id="68e8b-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="68e8b-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="68e8b-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="68e8b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="68e8b-111">0x00008122</span><span class="sxs-lookup"><span data-stu-id="68e8b-111">0x00008122</span></span>  <br/> |
|<span data-ttu-id="68e8b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="68e8b-112">Data type:</span></span>  <br/> |<span data-ttu-id="68e8b-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="68e8b-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="68e8b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="68e8b-114">Area:</span></span>  <br/> |<span data-ttu-id="68e8b-115">任务</span><span class="sxs-lookup"><span data-stu-id="68e8b-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68e8b-116">备注</span><span class="sxs-lookup"><span data-stu-id="68e8b-116">Remarks</span></span>

<span data-ttu-id="68e8b-117">客户端发送任务请求之前，请将该属性设置为任务分配人的名称。</span><span class="sxs-lookup"><span data-stu-id="68e8b-117">Before a client sends a task request, it sets this property to the name of the task assigner.</span></span> <span data-ttu-id="68e8b-118">客户端发送接受任务之前，请将该属性设置为任务受理人的名称。</span><span class="sxs-lookup"><span data-stu-id="68e8b-118">Before a client sends a task acceptance, it sets this property to the name of the task assignee.</span></span> <span data-ttu-id="68e8b-119">客户端发送任务拒绝之前，请将该属性设置为任务分配人的名称。</span><span class="sxs-lookup"><span data-stu-id="68e8b-119">Before a client sends a task rejection, it sets this property to the name of the task assigner.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="68e8b-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="68e8b-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="68e8b-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="68e8b-121">Protocol specifications</span></span>

<span data-ttu-id="68e8b-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68e8b-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68e8b-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="68e8b-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="68e8b-124">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68e8b-124">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68e8b-125">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="68e8b-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="68e8b-126">头文件</span><span class="sxs-lookup"><span data-stu-id="68e8b-126">Header files</span></span>

<span data-ttu-id="68e8b-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="68e8b-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="68e8b-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="68e8b-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="68e8b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68e8b-129">See also</span></span>



[<span data-ttu-id="68e8b-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="68e8b-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="68e8b-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="68e8b-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="68e8b-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68e8b-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="68e8b-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68e8b-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

