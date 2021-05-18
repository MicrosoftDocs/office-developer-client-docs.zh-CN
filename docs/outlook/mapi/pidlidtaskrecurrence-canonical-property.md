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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316623"
---
# <a name="pidlidtaskrecurrence-canonical-property"></a><span data-ttu-id="34688-103">PidLidTaskRecurrence 规范属性</span><span class="sxs-lookup"><span data-stu-id="34688-103">PidLidTaskRecurrence Canonical Property</span></span>

  
  
<span data-ttu-id="34688-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34688-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34688-105">包含一个 RecurrencePattern 结构，该结构提供有关定期任务的信息。</span><span class="sxs-lookup"><span data-stu-id="34688-105">Contains a RecurrencePattern structure that provides information about recurring tasks.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="34688-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="34688-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="34688-107">dispidTaskRecur</span><span class="sxs-lookup"><span data-stu-id="34688-107">dispidTaskRecur</span></span>  <br/> |
|<span data-ttu-id="34688-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="34688-108">Property set:</span></span>  <br/> |<span data-ttu-id="34688-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="34688-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="34688-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="34688-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="34688-111">0x00008116</span><span class="sxs-lookup"><span data-stu-id="34688-111">0x00008116</span></span>  <br/> |
|<span data-ttu-id="34688-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="34688-112">Data type:</span></span>  <br/> |<span data-ttu-id="34688-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="34688-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="34688-114">区域：</span><span class="sxs-lookup"><span data-stu-id="34688-114">Area:</span></span>  <br/> |<span data-ttu-id="34688-115">任务</span><span class="sxs-lookup"><span data-stu-id="34688-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34688-116">备注</span><span class="sxs-lookup"><span data-stu-id="34688-116">Remarks</span></span>

<span data-ttu-id="34688-117">若要了解如何创建和指定 RecurrencePattern 结构，请参阅创建 [简单重复性任务项](how-to-create-a-simple-recurrent-task-item.md)。</span><span class="sxs-lookup"><span data-stu-id="34688-117">For information about how to create and specify a RecurrencePattern structure, see [Create a Simple Recurrent Task Item](how-to-create-a-simple-recurrent-task-item.md).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="34688-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="34688-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="34688-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="34688-119">Protocol specifications</span></span>

<span data-ttu-id="34688-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34688-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34688-121">提供属性集定义和对相关协议Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="34688-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="34688-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34688-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34688-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="34688-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="34688-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34688-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34688-125">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="34688-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="34688-126">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34688-126">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34688-127">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="34688-127">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="34688-128">头文件</span><span class="sxs-lookup"><span data-stu-id="34688-128">Header files</span></span>

<span data-ttu-id="34688-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="34688-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="34688-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="34688-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34688-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34688-131">See also</span></span>



[<span data-ttu-id="34688-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="34688-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="34688-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="34688-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="34688-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="34688-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="34688-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="34688-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

