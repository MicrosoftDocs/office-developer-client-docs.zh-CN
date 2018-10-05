---
title: PidLidTaskRecurrence 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskRecurrence
api_type:
- COM
ms.assetid: e675bfdd-7598-45f3-a5aa-23b4734670dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7406bdac6df511ee546f9bf8aa4e5232586a31ee
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393787"
---
# <a name="pidlidtaskrecurrence-canonical-property"></a><span data-ttu-id="99000-103">PidLidTaskRecurrence 规范属性</span><span class="sxs-lookup"><span data-stu-id="99000-103">PidLidTaskRecurrence Canonical Property</span></span>

  
  
<span data-ttu-id="99000-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="99000-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="99000-105">包含提供有关周期性任务信息的 RecurrencePattern 结构。</span><span class="sxs-lookup"><span data-stu-id="99000-105">Contains a RecurrencePattern structure that provides information about recurring tasks.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="99000-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="99000-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="99000-107">dispidTaskRecur</span><span class="sxs-lookup"><span data-stu-id="99000-107">dispidTaskRecur</span></span>  <br/> |
|<span data-ttu-id="99000-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="99000-108">Property set:</span></span>  <br/> |<span data-ttu-id="99000-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="99000-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="99000-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="99000-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="99000-111">0x00008116</span><span class="sxs-lookup"><span data-stu-id="99000-111">0x00008116</span></span>  <br/> |
|<span data-ttu-id="99000-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="99000-112">Data type:</span></span>  <br/> |<span data-ttu-id="99000-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="99000-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="99000-114">区域：</span><span class="sxs-lookup"><span data-stu-id="99000-114">Area:</span></span>  <br/> |<span data-ttu-id="99000-115">Task</span><span class="sxs-lookup"><span data-stu-id="99000-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="99000-116">说明</span><span class="sxs-lookup"><span data-stu-id="99000-116">Remarks</span></span>

<span data-ttu-id="99000-117">有关如何创建并指定一个 RecurrencePattern 结构的信息，请参阅[创建简单的定期任务项](how-to-create-a-simple-recurrent-task-item.md)。</span><span class="sxs-lookup"><span data-stu-id="99000-117">For information about how to create and specify a RecurrencePattern structure, see [Create a Simple Recurrent Task Item](how-to-create-a-simple-recurrent-task-item.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="99000-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="99000-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="99000-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="99000-119">Protocol specifications</span></span>

<span data-ttu-id="99000-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99000-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99000-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="99000-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="99000-122">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99000-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99000-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="99000-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="99000-124">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99000-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99000-125">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="99000-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="99000-126">[[MS OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="99000-126">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="99000-127">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="99000-127">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="99000-128">头文件</span><span class="sxs-lookup"><span data-stu-id="99000-128">Header files</span></span>

<span data-ttu-id="99000-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="99000-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="99000-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="99000-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="99000-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99000-131">See also</span></span>



[<span data-ttu-id="99000-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="99000-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="99000-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="99000-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="99000-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="99000-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="99000-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="99000-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

