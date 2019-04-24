---
title: PidLidTaskMultipleRecipients 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskMultipleRecipients
api_type:
- COM
ms.assetid: 28ba9997-72dd-465f-94a7-35a317a361ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3b260917e107086dee6176f73b6c82c3a1825327
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360065"
---
# <a name="pidlidtaskmultiplerecipients-canonical-property"></a><span data-ttu-id="b03c9-103">PidLidTaskMultipleRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="b03c9-103">PidLidTaskMultipleRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="b03c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b03c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b03c9-105">提供有关任务收件人的优化提示。</span><span class="sxs-lookup"><span data-stu-id="b03c9-105">Provides optimization hints about the recipients of a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b03c9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b03c9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b03c9-107">dispidTaskMultRecips</span><span class="sxs-lookup"><span data-stu-id="b03c9-107">dispidTaskMultRecips</span></span>  <br/> |
|<span data-ttu-id="b03c9-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="b03c9-108">Property set:</span></span>  <br/> |<span data-ttu-id="b03c9-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="b03c9-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="b03c9-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="b03c9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b03c9-111">0x00008120</span><span class="sxs-lookup"><span data-stu-id="b03c9-111">0x00008120</span></span>  <br/> |
|<span data-ttu-id="b03c9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b03c9-112">Data type:</span></span>  <br/> |<span data-ttu-id="b03c9-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b03c9-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b03c9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b03c9-114">Area:</span></span>  <br/> |<span data-ttu-id="b03c9-115">任务</span><span class="sxs-lookup"><span data-stu-id="b03c9-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b03c9-116">注解</span><span class="sxs-lookup"><span data-stu-id="b03c9-116">Remarks</span></span>

<span data-ttu-id="b03c9-117">如果设置此属性, 则必须将此属性设置为零个或多个下列值的按位**或**运算。</span><span class="sxs-lookup"><span data-stu-id="b03c9-117">If set, this property must be set to a bitwise **OR** operation of zero or more of the following values.</span></span> 
  
|<span data-ttu-id="b03c9-118">**Name**</span><span class="sxs-lookup"><span data-stu-id="b03c9-118">**Name**</span></span>|<span data-ttu-id="b03c9-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="b03c9-119">**Value**</span></span>|<span data-ttu-id="b03c9-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="b03c9-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b03c9-121">发件箱</span><span class="sxs-lookup"><span data-stu-id="b03c9-121">Sent</span></span>  <br/> |<span data-ttu-id="b03c9-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b03c9-122">0x00000001</span></span>  <br/> |<span data-ttu-id="b03c9-123">任务包含多个主要收件人。</span><span class="sxs-lookup"><span data-stu-id="b03c9-123">The task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="b03c9-124">接收时间</span><span class="sxs-lookup"><span data-stu-id="b03c9-124">Received</span></span>  <br/> |<span data-ttu-id="b03c9-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b03c9-125">0x00000002</span></span>  <br/> |<span data-ttu-id="b03c9-126">尽管发送的提示不存在, 但客户端检测到该任务有多个主收件人。</span><span class="sxs-lookup"><span data-stu-id="b03c9-126">Although the Sent hint was not present, the client detected that the task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="b03c9-127">Reserved</span><span class="sxs-lookup"><span data-stu-id="b03c9-127">Reserved</span></span>  <br/> |<span data-ttu-id="b03c9-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b03c9-128">0x00000004</span></span>  <br/> |<span data-ttu-id="b03c9-129">此值为保留值。</span><span class="sxs-lookup"><span data-stu-id="b03c9-129">This value is reserved.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b03c9-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="b03c9-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b03c9-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="b03c9-131">Protocol specifications</span></span>

<span data-ttu-id="b03c9-132">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b03c9-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b03c9-133">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b03c9-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b03c9-134">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b03c9-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b03c9-135">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="b03c9-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b03c9-136">头文件</span><span class="sxs-lookup"><span data-stu-id="b03c9-136">Header files</span></span>

<span data-ttu-id="b03c9-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b03c9-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="b03c9-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b03c9-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b03c9-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b03c9-139">See also</span></span>



[<span data-ttu-id="b03c9-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b03c9-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b03c9-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b03c9-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b03c9-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b03c9-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b03c9-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b03c9-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

