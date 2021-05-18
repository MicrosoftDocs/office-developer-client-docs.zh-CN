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
# <a name="pidlidtaskassigners-canonical-property"></a><span data-ttu-id="a7da0-103">PidLidTaskAssigners 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7da0-103">PidLidTaskAssigners Canonical Property</span></span>

  
  
<span data-ttu-id="a7da0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a7da0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a7da0-105">包含表示任务分配者条目堆栈。</span><span class="sxs-lookup"><span data-stu-id="a7da0-105">Contains a stack of entries that represent task assigners.</span></span> <span data-ttu-id="a7da0-106">最新的任务分配者显示在堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="a7da0-106">The most recent task assigner appears at the top of the stack.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a7da0-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a7da0-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="a7da0-108">dispidTaskMyDelegators</span><span class="sxs-lookup"><span data-stu-id="a7da0-108">dispidTaskMyDelegators</span></span>  <br/> |
|<span data-ttu-id="a7da0-109">属性集：</span><span class="sxs-lookup"><span data-stu-id="a7da0-109">Property set:</span></span>  <br/> |<span data-ttu-id="a7da0-110">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="a7da0-110">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="a7da0-111">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="a7da0-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a7da0-112">0x00008117</span><span class="sxs-lookup"><span data-stu-id="a7da0-112">0x00008117</span></span>  <br/> |
|<span data-ttu-id="a7da0-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a7da0-113">Data type:</span></span>  <br/> |<span data-ttu-id="a7da0-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a7da0-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a7da0-115">区域：</span><span class="sxs-lookup"><span data-stu-id="a7da0-115">Area:</span></span>  <br/> |<span data-ttu-id="a7da0-116">任务</span><span class="sxs-lookup"><span data-stu-id="a7da0-116">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a7da0-117">备注</span><span class="sxs-lookup"><span data-stu-id="a7da0-117">Remarks</span></span>

<span data-ttu-id="a7da0-118">当客户端收到任务请求时，它将追加到此属性，该属性的结构在 [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)中定义，这是一个表示任务发件人的条目。</span><span class="sxs-lookup"><span data-stu-id="a7da0-118">When the client receives a task request, it appends to this property, which structure is defined in [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx), an entry that represents the task's sender.</span></span> <span data-ttu-id="a7da0-119">当客户端收到任务拒绝时，客户端会从此属性中删除最后一个任务分配者条目。</span><span class="sxs-lookup"><span data-stu-id="a7da0-119">When the client receives a task rejection, the client removes the last task assigner entry from this property.</span></span> <span data-ttu-id="a7da0-120">当客户端发送任务响应时，客户端会将其发送给此属性的值中列出的最后一个任务分配者。</span><span class="sxs-lookup"><span data-stu-id="a7da0-120">When the client sends a task response, the client sends it to the last task assigner listed in the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a7da0-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="a7da0-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a7da0-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="a7da0-122">Protocol specifications</span></span>

<span data-ttu-id="a7da0-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7da0-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7da0-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="a7da0-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a7da0-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7da0-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a7da0-126">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模</span><span class="sxs-lookup"><span data-stu-id="a7da0-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="a7da0-127">头文件</span><span class="sxs-lookup"><span data-stu-id="a7da0-127">Header files</span></span>

<span data-ttu-id="a7da0-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a7da0-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="a7da0-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a7da0-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a7da0-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7da0-130">See also</span></span>



[<span data-ttu-id="a7da0-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a7da0-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a7da0-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a7da0-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a7da0-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a7da0-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a7da0-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a7da0-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

