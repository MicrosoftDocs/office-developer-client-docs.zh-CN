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
ms.openlocfilehash: 89e0b6eae35de9e40dba411afb82e19aa81fb635
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777052"
---
# <a name="pidlidtaskassigners-canonical-property"></a><span data-ttu-id="39151-103">PidLidTaskAssigners 规范属性</span><span class="sxs-lookup"><span data-stu-id="39151-103">PidLidTaskAssigners Canonical Property</span></span>

  
  
<span data-ttu-id="39151-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="39151-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="39151-105">包含条目，表示任务 assigners 的堆栈。</span><span class="sxs-lookup"><span data-stu-id="39151-105">Contains a stack of entries that represent task assigners.</span></span> <span data-ttu-id="39151-106">最新的任务分配人显示在堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="39151-106">The most recent task assigner appears at the top of the stack.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="39151-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="39151-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="39151-108">dispidTaskMyDelegators</span><span class="sxs-lookup"><span data-stu-id="39151-108">dispidTaskMyDelegators</span></span>  <br/> |
|<span data-ttu-id="39151-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="39151-109">Property set:</span></span>  <br/> |<span data-ttu-id="39151-110">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="39151-110">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="39151-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="39151-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="39151-112">0x00008117</span><span class="sxs-lookup"><span data-stu-id="39151-112">0x00008117</span></span>  <br/> |
|<span data-ttu-id="39151-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="39151-113">Data type:</span></span>  <br/> |<span data-ttu-id="39151-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="39151-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="39151-115">区域：</span><span class="sxs-lookup"><span data-stu-id="39151-115">Area:</span></span>  <br/> |<span data-ttu-id="39151-116">Task</span><span class="sxs-lookup"><span data-stu-id="39151-116">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="39151-117">说明</span><span class="sxs-lookup"><span data-stu-id="39151-117">Remarks</span></span>

<span data-ttu-id="39151-118">客户端接收任务请求时，它将追加到此属性，在[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)，值，该值代表任务的发件人的条目中定义的结构。</span><span class="sxs-lookup"><span data-stu-id="39151-118">When the client receives a task request, it appends to this property, which structure is defined in [[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx), an entry that represents the task's sender.</span></span> <span data-ttu-id="39151-119">当客户端收到任务拒绝时，客户端从此属性中删除最后一个任务分配人条目。</span><span class="sxs-lookup"><span data-stu-id="39151-119">When the client receives a task rejection, the client removes the last task assigner entry from this property.</span></span> <span data-ttu-id="39151-120">当客户端发送的任务响应时，客户端会将其发送到最后一个任务分配人列入此属性的值。</span><span class="sxs-lookup"><span data-stu-id="39151-120">When the client sends a task response, the client sends it to the last task assigner listed in the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="39151-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="39151-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="39151-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="39151-122">Protocol specifications</span></span>

<span data-ttu-id="39151-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39151-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39151-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="39151-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="39151-125">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39151-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39151-126">定义模型的任务、 任务分配和任务更新电子等效项的多个对象</span><span class="sxs-lookup"><span data-stu-id="39151-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="39151-127">头文件</span><span class="sxs-lookup"><span data-stu-id="39151-127">Header files</span></span>

<span data-ttu-id="39151-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="39151-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="39151-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="39151-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="39151-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39151-130">See also</span></span>



[<span data-ttu-id="39151-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="39151-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="39151-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="39151-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="39151-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="39151-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="39151-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="39151-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

