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
ms.openlocfilehash: 20a4cf4fc847bdb361fb73161adeb96afb49e57e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570749"
---
# <a name="pidlidtaskassigners-canonical-property"></a><span data-ttu-id="a6415-103">PidLidTaskAssigners 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6415-103">PidLidTaskAssigners Canonical Property</span></span>

  
  
<span data-ttu-id="a6415-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a6415-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a6415-105">包含条目，表示任务 assigners 的堆栈。</span><span class="sxs-lookup"><span data-stu-id="a6415-105">Contains a stack of entries that represent task assigners.</span></span> <span data-ttu-id="a6415-106">最新的任务分配人显示在堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="a6415-106">The most recent task assigner appears at the top of the stack.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a6415-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a6415-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="a6415-108">dispidTaskMyDelegators</span><span class="sxs-lookup"><span data-stu-id="a6415-108">dispidTaskMyDelegators</span></span>  <br/> |
|<span data-ttu-id="a6415-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="a6415-109">Property set:</span></span>  <br/> |<span data-ttu-id="a6415-110">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="a6415-110">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="a6415-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="a6415-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a6415-112">0x00008117</span><span class="sxs-lookup"><span data-stu-id="a6415-112">0x00008117</span></span>  <br/> |
|<span data-ttu-id="a6415-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a6415-113">Data type:</span></span>  <br/> |<span data-ttu-id="a6415-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a6415-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a6415-115">区域：</span><span class="sxs-lookup"><span data-stu-id="a6415-115">Area:</span></span>  <br/> |<span data-ttu-id="a6415-116">Task</span><span class="sxs-lookup"><span data-stu-id="a6415-116">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a6415-117">注解</span><span class="sxs-lookup"><span data-stu-id="a6415-117">Remarks</span></span>

<span data-ttu-id="a6415-118">客户端接收任务请求时，它将追加到此属性，在[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)，值，该值代表任务的发件人的条目中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="a6415-118">When the client receives a task request, it appends to this property, which structure is defined in [[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx), an entry that represents the task's sender.</span></span> <span data-ttu-id="a6415-119">当客户端收到任务拒绝时，客户端从此属性中删除最后一个任务分配人条目。</span><span class="sxs-lookup"><span data-stu-id="a6415-119">When the client receives a task rejection, the client removes the last task assigner entry from this property.</span></span> <span data-ttu-id="a6415-120">当客户端发送的任务响应时，客户端会将其发送到最后一个任务分配人列入此属性的值。</span><span class="sxs-lookup"><span data-stu-id="a6415-120">When the client sends a task response, the client sends it to the last task assigner listed in the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a6415-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="a6415-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a6415-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="a6415-122">Protocol specifications</span></span>

<span data-ttu-id="a6415-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6415-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6415-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a6415-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a6415-125">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a6415-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a6415-126">定义模型的任务、 任务分配和任务更新电子等效项的多个对象</span><span class="sxs-lookup"><span data-stu-id="a6415-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="a6415-127">头文件</span><span class="sxs-lookup"><span data-stu-id="a6415-127">Header files</span></span>

<span data-ttu-id="a6415-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a6415-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="a6415-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a6415-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6415-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6415-130">See also</span></span>



[<span data-ttu-id="a6415-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a6415-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a6415-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a6415-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a6415-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a6415-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a6415-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a6415-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

