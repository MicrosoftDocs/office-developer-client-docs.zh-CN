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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1e1cba3d927072cb03dbd34eee518c9b0a9e0383
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777093"
---
# <a name="pidlidtaskmultiplerecipients-canonical-property"></a><span data-ttu-id="cabe2-103">PidLidTaskMultipleRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="cabe2-103">PidLidTaskMultipleRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="cabe2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cabe2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cabe2-105">提供有关收件人的任务的优化提示。</span><span class="sxs-lookup"><span data-stu-id="cabe2-105">Provides optimization hints about the recipients of a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cabe2-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="cabe2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cabe2-107">dispidTaskMultRecips</span><span class="sxs-lookup"><span data-stu-id="cabe2-107">dispidTaskMultRecips</span></span>  <br/> |
|<span data-ttu-id="cabe2-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cabe2-108">Property set:</span></span>  <br/> |<span data-ttu-id="cabe2-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="cabe2-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="cabe2-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cabe2-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cabe2-111">0x00008120</span><span class="sxs-lookup"><span data-stu-id="cabe2-111">0x00008120</span></span>  <br/> |
|<span data-ttu-id="cabe2-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cabe2-112">Data type:</span></span>  <br/> |<span data-ttu-id="cabe2-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cabe2-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cabe2-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cabe2-114">Area:</span></span>  <br/> |<span data-ttu-id="cabe2-115">任务</span><span class="sxs-lookup"><span data-stu-id="cabe2-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cabe2-116">备注</span><span class="sxs-lookup"><span data-stu-id="cabe2-116">Remarks</span></span>

<span data-ttu-id="cabe2-117">如果设置，此属性必须设置为零个或多个下列值的按位**OR**运算。</span><span class="sxs-lookup"><span data-stu-id="cabe2-117">If set, this property must be set to a bitwise **OR** operation of zero or more of the following values.</span></span> 
  
|<span data-ttu-id="cabe2-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="cabe2-118">**Name**</span></span>|<span data-ttu-id="cabe2-119">**值**</span><span class="sxs-lookup"><span data-stu-id="cabe2-119">**Value**</span></span>|<span data-ttu-id="cabe2-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="cabe2-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cabe2-121">发送时间</span><span class="sxs-lookup"><span data-stu-id="cabe2-121">Sent</span></span>  <br/> |<span data-ttu-id="cabe2-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="cabe2-122">0x00000001</span></span>  <br/> |<span data-ttu-id="cabe2-123">该任务具有多个主收件人。</span><span class="sxs-lookup"><span data-stu-id="cabe2-123">The task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="cabe2-124">接收时间</span><span class="sxs-lookup"><span data-stu-id="cabe2-124">Received</span></span>  <br/> |<span data-ttu-id="cabe2-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="cabe2-125">0x00000002</span></span>  <br/> |<span data-ttu-id="cabe2-126">尽管 Sent 提示不存在，客户端检测到任务具有多个主收件人。</span><span class="sxs-lookup"><span data-stu-id="cabe2-126">Although the Sent hint was not present, the client detected that the task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="cabe2-127">保留</span><span class="sxs-lookup"><span data-stu-id="cabe2-127">Reserved</span></span>  <br/> |<span data-ttu-id="cabe2-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="cabe2-128">0x00000004</span></span>  <br/> |<span data-ttu-id="cabe2-129">保留此值。</span><span class="sxs-lookup"><span data-stu-id="cabe2-129">This value is reserved.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="cabe2-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="cabe2-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cabe2-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="cabe2-131">Protocol specifications</span></span>

<span data-ttu-id="cabe2-132">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cabe2-132">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cabe2-133">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cabe2-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cabe2-134">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cabe2-134">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cabe2-135">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="cabe2-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cabe2-136">头文件</span><span class="sxs-lookup"><span data-stu-id="cabe2-136">Header files</span></span>

<span data-ttu-id="cabe2-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cabe2-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="cabe2-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cabe2-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cabe2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cabe2-139">See also</span></span>



[<span data-ttu-id="cabe2-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cabe2-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cabe2-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cabe2-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cabe2-142">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cabe2-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cabe2-143">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cabe2-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

