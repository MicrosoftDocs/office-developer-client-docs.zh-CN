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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 76311a76001b122bdfd984b9dedc37c2ff878fc7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360443"
---
# <a name="pidlidtasklastuser-canonical-property"></a><span data-ttu-id="88f4f-103">PidLidTaskLastUser 规范属性</span><span class="sxs-lookup"><span data-stu-id="88f4f-103">PidLidTaskLastUser Canonical Property</span></span>

  
  
<span data-ttu-id="88f4f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f4f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88f4f-105">将最近的用户命名为任务所有者。</span><span class="sxs-lookup"><span data-stu-id="88f4f-105">Names the most recent user who was the task owner.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88f4f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88f4f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88f4f-107">dispidTaskLastUser</span><span class="sxs-lookup"><span data-stu-id="88f4f-107">dispidTaskLastUser</span></span>  <br/> |
|<span data-ttu-id="88f4f-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="88f4f-108">Property set:</span></span>  <br/> |<span data-ttu-id="88f4f-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="88f4f-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="88f4f-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="88f4f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="88f4f-111">0x00008122</span><span class="sxs-lookup"><span data-stu-id="88f4f-111">0x00008122</span></span>  <br/> |
|<span data-ttu-id="88f4f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88f4f-112">Data type:</span></span>  <br/> |<span data-ttu-id="88f4f-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="88f4f-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="88f4f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="88f4f-114">Area:</span></span>  <br/> |<span data-ttu-id="88f4f-115">任务</span><span class="sxs-lookup"><span data-stu-id="88f4f-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88f4f-116">注解</span><span class="sxs-lookup"><span data-stu-id="88f4f-116">Remarks</span></span>

<span data-ttu-id="88f4f-117">在客户端发送任务请求之前, 它会将此属性设置为任务 assigner 的名称。</span><span class="sxs-lookup"><span data-stu-id="88f4f-117">Before a client sends a task request, it sets this property to the name of the task assigner.</span></span> <span data-ttu-id="88f4f-118">在客户端发送任务接受前, 它会将此属性设置为任务受理人的姓名。</span><span class="sxs-lookup"><span data-stu-id="88f4f-118">Before a client sends a task acceptance, it sets this property to the name of the task assignee.</span></span> <span data-ttu-id="88f4f-119">在客户端发送任务拒绝之前, 它会将此属性设置为任务 assigner 的名称。</span><span class="sxs-lookup"><span data-stu-id="88f4f-119">Before a client sends a task rejection, it sets this property to the name of the task assigner.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="88f4f-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="88f4f-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="88f4f-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="88f4f-121">Protocol specifications</span></span>

<span data-ttu-id="88f4f-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88f4f-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88f4f-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="88f4f-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="88f4f-124">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="88f4f-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="88f4f-125">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="88f4f-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="88f4f-126">头文件</span><span class="sxs-lookup"><span data-stu-id="88f4f-126">Header files</span></span>

<span data-ttu-id="88f4f-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="88f4f-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="88f4f-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88f4f-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88f4f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88f4f-129">See also</span></span>



[<span data-ttu-id="88f4f-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88f4f-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88f4f-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88f4f-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88f4f-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88f4f-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88f4f-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88f4f-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

