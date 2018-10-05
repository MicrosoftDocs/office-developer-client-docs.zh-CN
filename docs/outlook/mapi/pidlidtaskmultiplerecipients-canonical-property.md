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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391169"
---
# <a name="pidlidtaskmultiplerecipients-canonical-property"></a><span data-ttu-id="94721-103">PidLidTaskMultipleRecipients 规范属性</span><span class="sxs-lookup"><span data-stu-id="94721-103">PidLidTaskMultipleRecipients Canonical Property</span></span>

  
  
<span data-ttu-id="94721-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="94721-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="94721-105">提供有关收件人的任务的优化提示。</span><span class="sxs-lookup"><span data-stu-id="94721-105">Provides optimization hints about the recipients of a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="94721-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="94721-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="94721-107">dispidTaskMultRecips</span><span class="sxs-lookup"><span data-stu-id="94721-107">dispidTaskMultRecips</span></span>  <br/> |
|<span data-ttu-id="94721-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="94721-108">Property set:</span></span>  <br/> |<span data-ttu-id="94721-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="94721-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="94721-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="94721-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="94721-111">0x00008120</span><span class="sxs-lookup"><span data-stu-id="94721-111">0x00008120</span></span>  <br/> |
|<span data-ttu-id="94721-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="94721-112">Data type:</span></span>  <br/> |<span data-ttu-id="94721-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="94721-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="94721-114">区域：</span><span class="sxs-lookup"><span data-stu-id="94721-114">Area:</span></span>  <br/> |<span data-ttu-id="94721-115">Task</span><span class="sxs-lookup"><span data-stu-id="94721-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="94721-116">说明</span><span class="sxs-lookup"><span data-stu-id="94721-116">Remarks</span></span>

<span data-ttu-id="94721-117">如果设置，此属性必须设置为零个或多个下列值的按位**OR**运算。</span><span class="sxs-lookup"><span data-stu-id="94721-117">If set, this property must be set to a bitwise **OR** operation of zero or more of the following values.</span></span> 
  
|<span data-ttu-id="94721-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="94721-118">**Name**</span></span>|<span data-ttu-id="94721-119">**值**</span><span class="sxs-lookup"><span data-stu-id="94721-119">**Value**</span></span>|<span data-ttu-id="94721-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="94721-120">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94721-121">发送时间</span><span class="sxs-lookup"><span data-stu-id="94721-121">Sent</span></span>  <br/> |<span data-ttu-id="94721-122">0x00000001</span><span class="sxs-lookup"><span data-stu-id="94721-122">0x00000001</span></span>  <br/> |<span data-ttu-id="94721-123">该任务具有多个主收件人。</span><span class="sxs-lookup"><span data-stu-id="94721-123">The task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="94721-124">接收时间</span><span class="sxs-lookup"><span data-stu-id="94721-124">Received</span></span>  <br/> |<span data-ttu-id="94721-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="94721-125">0x00000002</span></span>  <br/> |<span data-ttu-id="94721-126">尽管 Sent 提示不存在，客户端检测到任务具有多个主收件人。</span><span class="sxs-lookup"><span data-stu-id="94721-126">Although the Sent hint was not present, the client detected that the task has multiple primary recipients.</span></span>  <br/> |
|<span data-ttu-id="94721-127">保留</span><span class="sxs-lookup"><span data-stu-id="94721-127">Reserved</span></span>  <br/> |<span data-ttu-id="94721-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="94721-128">0x00000004</span></span>  <br/> |<span data-ttu-id="94721-129">保留此值。</span><span class="sxs-lookup"><span data-stu-id="94721-129">This value is reserved.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="94721-130">相关资源</span><span class="sxs-lookup"><span data-stu-id="94721-130">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="94721-131">协议规范</span><span class="sxs-lookup"><span data-stu-id="94721-131">Protocol specifications</span></span>

<span data-ttu-id="94721-132">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="94721-132">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="94721-133">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="94721-133">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="94721-134">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="94721-134">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="94721-135">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="94721-135">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="94721-136">头文件</span><span class="sxs-lookup"><span data-stu-id="94721-136">Header files</span></span>

<span data-ttu-id="94721-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="94721-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="94721-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="94721-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="94721-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94721-139">See also</span></span>



[<span data-ttu-id="94721-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="94721-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="94721-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="94721-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="94721-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="94721-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="94721-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="94721-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

