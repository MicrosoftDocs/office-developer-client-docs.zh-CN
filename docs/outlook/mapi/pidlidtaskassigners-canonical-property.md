---
title: PidLidTaskAssigners 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAssigners
api_type:
- COM
ms.assetid: 07500bd0-bcff-4b03-8ed3-80508875e253
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 97a4915d5422f6c5463ed399835172725b83407f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303063"
---
# <a name="pidlidtaskassigners-canonical-property"></a><span data-ttu-id="38377-103">PidLidTaskAssigners 规范属性</span><span class="sxs-lookup"><span data-stu-id="38377-103">PidLidTaskAssigners Canonical Property</span></span>

  
  
<span data-ttu-id="38377-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38377-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38377-105">包含表示任务 assigners 的条目的堆栈。</span><span class="sxs-lookup"><span data-stu-id="38377-105">Contains a stack of entries that represent task assigners.</span></span> <span data-ttu-id="38377-106">最近的任务 assigner 显示在堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="38377-106">The most recent task assigner appears at the top of the stack.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="38377-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="38377-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="38377-108">dispidTaskMyDelegators</span><span class="sxs-lookup"><span data-stu-id="38377-108">dispidTaskMyDelegators</span></span>  <br/> |
|<span data-ttu-id="38377-109">属性集:</span><span class="sxs-lookup"><span data-stu-id="38377-109">Property set:</span></span>  <br/> |<span data-ttu-id="38377-110">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="38377-110">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="38377-111">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="38377-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="38377-112">0x00008117</span><span class="sxs-lookup"><span data-stu-id="38377-112">0x00008117</span></span>  <br/> |
|<span data-ttu-id="38377-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="38377-113">Data type:</span></span>  <br/> |<span data-ttu-id="38377-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="38377-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="38377-115">区域：</span><span class="sxs-lookup"><span data-stu-id="38377-115">Area:</span></span>  <br/> |<span data-ttu-id="38377-116">任务</span><span class="sxs-lookup"><span data-stu-id="38377-116">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38377-117">注解</span><span class="sxs-lookup"><span data-stu-id="38377-117">Remarks</span></span>

<span data-ttu-id="38377-118">当客户端收到任务请求时, 它会追加到此属性, 这是在[[OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)中定义的结构, 表示任务的发件人的条目。</span><span class="sxs-lookup"><span data-stu-id="38377-118">When the client receives a task request, it appends to this property, which structure is defined in [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx), an entry that represents the task's sender.</span></span> <span data-ttu-id="38377-119">当客户端收到任务拒绝时, 客户端将从此属性中删除最后一个任务 assigner 条目。</span><span class="sxs-lookup"><span data-stu-id="38377-119">When the client receives a task rejection, the client removes the last task assigner entry from this property.</span></span> <span data-ttu-id="38377-120">当客户端发送任务响应时, 客户端会将其发送到该属性的值中列出的最后一个任务 assigner。</span><span class="sxs-lookup"><span data-stu-id="38377-120">When the client sends a task response, the client sends it to the last task assigner listed in the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="38377-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="38377-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="38377-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="38377-122">Protocol specifications</span></span>

<span data-ttu-id="38377-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38377-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38377-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="38377-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="38377-125">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38377-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38377-126">定义为任务、任务分配和任务更新的电子等效项建模的多个对象</span><span class="sxs-lookup"><span data-stu-id="38377-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="38377-127">头文件</span><span class="sxs-lookup"><span data-stu-id="38377-127">Header files</span></span>

<span data-ttu-id="38377-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="38377-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="38377-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="38377-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38377-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38377-130">See also</span></span>



[<span data-ttu-id="38377-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="38377-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="38377-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="38377-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="38377-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="38377-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="38377-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="38377-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

