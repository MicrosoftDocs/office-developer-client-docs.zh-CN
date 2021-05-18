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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2e21d164cbb9403d3fa1dc05cf474359a517d64b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303323"
---
# <a name="pidlidtaskduedate-canonical-property"></a><span data-ttu-id="60005-103">PidLidTaskDueDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="60005-103">PidLidTaskDueDate Canonical Property</span></span>

  
  
<span data-ttu-id="60005-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60005-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="60005-105">表示用户预期完成任务的日期。</span><span class="sxs-lookup"><span data-stu-id="60005-105">Represents the date when the user expects to complete the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="60005-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="60005-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="60005-107">dispidTaskDueDate</span><span class="sxs-lookup"><span data-stu-id="60005-107">dispidTaskDueDate</span></span>  <br/> |
|<span data-ttu-id="60005-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="60005-108">Property set:</span></span>  <br/> |<span data-ttu-id="60005-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="60005-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="60005-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="60005-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="60005-111">0x00008105</span><span class="sxs-lookup"><span data-stu-id="60005-111">0x00008105</span></span>  <br/> |
|<span data-ttu-id="60005-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="60005-112">Data type:</span></span>  <br/> |<span data-ttu-id="60005-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="60005-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="60005-114">区域：</span><span class="sxs-lookup"><span data-stu-id="60005-114">Area:</span></span>  <br/> |<span data-ttu-id="60005-115">任务</span><span class="sxs-lookup"><span data-stu-id="60005-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="60005-116">备注</span><span class="sxs-lookup"><span data-stu-id="60005-116">Remarks</span></span>

<span data-ttu-id="60005-117">如果此属性未设置或设置为 1，525，252，320 0x5AE980E0 (，则任务没有截止日期) 。</span><span class="sxs-lookup"><span data-stu-id="60005-117">The task has no due date if this property is unset or set to 0x5AE980E0 (1,525,252,320).</span></span> <span data-ttu-id="60005-118">但是，仅在 **dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md) 属性中未指示开始日期) 截止日期。</span><span class="sxs-lookup"><span data-stu-id="60005-118">However, a due date is optional only if no start date is indicated in the **dispidTaskStartDate** ([PidLidTaskStartDate](pidlidtaskstartdate-canonical-property.md)) property.</span></span> <span data-ttu-id="60005-119">如果任务具有截止日期，则值必须具有午夜的时间部分，并且还必须设置 **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="60005-119">If the task has a due date, the value must have a time component of midnight, and the **dispidCommonEnd** ([PidLidCommonEnd](pidlidcommonend-canonical-property.md)) property must also be set.</span></span> <span data-ttu-id="60005-120">如果 **dispidTaskStartDate** 具有开始日期， **则 dispidTaskDueDate** 属性的值必须大于或等于 **dispidTaskStartDate 的值**。</span><span class="sxs-lookup"><span data-stu-id="60005-120">If **dispidTaskStartDate** has a start date, then the value of the **dispidTaskDueDate** property must be greater than or equal to the value of **dispidTaskStartDate**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="60005-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="60005-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="60005-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="60005-122">Protocol specifications</span></span>

<span data-ttu-id="60005-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60005-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="60005-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="60005-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="60005-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60005-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="60005-126">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="60005-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
<span data-ttu-id="60005-127">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="60005-127">[[MS-OXORMDR]](https://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="60005-128">指定电子邮件和其他对象提醒的属性和交互模型。</span><span class="sxs-lookup"><span data-stu-id="60005-128">Specifies the properties and the interaction model for email and other object reminders.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="60005-129">头文件</span><span class="sxs-lookup"><span data-stu-id="60005-129">Header files</span></span>

<span data-ttu-id="60005-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="60005-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="60005-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="60005-131">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="60005-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60005-132">See also</span></span>



[<span data-ttu-id="60005-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="60005-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="60005-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="60005-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="60005-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="60005-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="60005-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="60005-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

