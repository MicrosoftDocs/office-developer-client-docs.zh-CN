---
title: PidLidTaskDueDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskDueDate
api_type:
- COM
ms.assetid: 69ed3d48-3741-4a9a-8f98-51382b850c27
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: d26a686573a9dc178a46b7dfdc5c18485303b7ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777086"
---
# <a name="pidlidtaskduedate-canonical-property"></a><span data-ttu-id="43e43-103">PidLidTaskDueDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="43e43-103">PidLidTaskDueDate Canonical Property</span></span>

  
  
<span data-ttu-id="43e43-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="43e43-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="43e43-105">表示用户希望完成任务的日期。</span><span class="sxs-lookup"><span data-stu-id="43e43-105">Represents the date when the user expects to complete the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="43e43-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="43e43-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43e43-107">dispidTaskDueDate</span><span class="sxs-lookup"><span data-stu-id="43e43-107">dispidTaskDueDate</span></span>  <br/> |
|<span data-ttu-id="43e43-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="43e43-108">Property set:</span></span>  <br/> |<span data-ttu-id="43e43-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="43e43-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="43e43-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="43e43-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="43e43-111">0x00008105</span><span class="sxs-lookup"><span data-stu-id="43e43-111">0x00008105</span></span>  <br/> |
|<span data-ttu-id="43e43-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43e43-112">Data type:</span></span>  <br/> |<span data-ttu-id="43e43-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="43e43-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="43e43-114">区域：</span><span class="sxs-lookup"><span data-stu-id="43e43-114">Area:</span></span>  <br/> |<span data-ttu-id="43e43-115">任务</span><span class="sxs-lookup"><span data-stu-id="43e43-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43e43-116">备注</span><span class="sxs-lookup"><span data-stu-id="43e43-116">Remarks</span></span>

<span data-ttu-id="43e43-117">如果此属性未设置或设置为 0x5AE980E0 (1,525,252,320)，该任务具有没有截止日期。</span><span class="sxs-lookup"><span data-stu-id="43e43-117">The task has no due date if this property is unset or set to 0x5AE980E0 (1,525,252,320).</span></span> <span data-ttu-id="43e43-118">但是，截止日期是可选的仅当没有开始日期指示**dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="43e43-118">However, a due date is optional only if no start date is indicated in the **dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) property.</span></span> <span data-ttu-id="43e43-119">如果任务的截止日期，值必须具有时间组件的午夜，并且还必须设置**dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="43e43-119">If the task has a due date, the value must have a time component of midnight, and the **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) property must also be set.</span></span> <span data-ttu-id="43e43-120">如果**dispidTaskStartDate**开始日期， **dispidTaskDueDate**属性的值必须大于或等于**dispidTaskStartDate**的值。</span><span class="sxs-lookup"><span data-stu-id="43e43-120">If **dispidTaskStartDate** has a start date, then the value of the **dispidTaskDueDate** property must be greater than or equal to the value of **dispidTaskStartDate**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="43e43-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="43e43-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="43e43-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="43e43-122">Protocol specifications</span></span>

<span data-ttu-id="43e43-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43e43-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43e43-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="43e43-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="43e43-125">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43e43-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43e43-126">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="43e43-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="43e43-127">[[MS OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="43e43-127">[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="43e43-128">指定属性和电子邮件和其他对象提醒的交互模型。</span><span class="sxs-lookup"><span data-stu-id="43e43-128">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="43e43-129">头文件</span><span class="sxs-lookup"><span data-stu-id="43e43-129">Header files</span></span>

<span data-ttu-id="43e43-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43e43-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="43e43-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43e43-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43e43-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43e43-132">See also</span></span>



[<span data-ttu-id="43e43-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43e43-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43e43-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43e43-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43e43-135">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43e43-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43e43-136">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43e43-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

