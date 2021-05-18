---
title: PidLidTaskEstimatedEffort 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskEstimatedEffort
api_type:
- COM
ms.assetid: c84167d8-f726-45c6-9b21-bcde64473148
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5700ab6baaab2a5e73448582a855e6f243d5361d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303043"
---
# <a name="pidlidtaskestimatedeffort-canonical-property"></a><span data-ttu-id="466fc-103">PidLidTaskEstimatedEffort 规范属性</span><span class="sxs-lookup"><span data-stu-id="466fc-103">PidLidTaskEstimatedEffort Canonical Property</span></span>

  
  
<span data-ttu-id="466fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="466fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="466fc-105">指示用户希望执行任务的时间量（以分钟表示）。</span><span class="sxs-lookup"><span data-stu-id="466fc-105">Indicates the amount of time, in minutes, that the user expects to perform a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="466fc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="466fc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="466fc-107">dispidTaskEstimatedEffort</span><span class="sxs-lookup"><span data-stu-id="466fc-107">dispidTaskEstimatedEffort</span></span>  <br/> |
|<span data-ttu-id="466fc-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="466fc-108">Property set:</span></span>  <br/> |<span data-ttu-id="466fc-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="466fc-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="466fc-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="466fc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="466fc-111">0x00008111</span><span class="sxs-lookup"><span data-stu-id="466fc-111">0x00008111</span></span>  <br/> |
|<span data-ttu-id="466fc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="466fc-112">Data type:</span></span>  <br/> |<span data-ttu-id="466fc-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="466fc-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="466fc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="466fc-114">Area:</span></span>  <br/> |<span data-ttu-id="466fc-115">任务</span><span class="sxs-lookup"><span data-stu-id="466fc-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="466fc-116">备注</span><span class="sxs-lookup"><span data-stu-id="466fc-116">Remarks</span></span>

<span data-ttu-id="466fc-117">该值必须大于或等于 0 且小于 0x5AE980DF (1，525，252，319) ，其中 480 分钟等于一天，2400 分钟等于一周 (8 小时，工作周) 中的五天。</span><span class="sxs-lookup"><span data-stu-id="466fc-117">The value must be greater than or equal to 0 and less than 0x5AE980DF (1,525,252,319), where 480 minutes equal one day and 2400 minutes equal one week (eight hours in a work day and five days in a work week).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="466fc-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="466fc-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="466fc-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="466fc-119">Protocol specifications</span></span>

<span data-ttu-id="466fc-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="466fc-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="466fc-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="466fc-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="466fc-122">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="466fc-122">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="466fc-123">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="466fc-123">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="466fc-124">头文件</span><span class="sxs-lookup"><span data-stu-id="466fc-124">Header files</span></span>

<span data-ttu-id="466fc-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="466fc-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="466fc-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="466fc-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="466fc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="466fc-127">See also</span></span>



[<span data-ttu-id="466fc-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="466fc-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="466fc-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="466fc-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="466fc-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="466fc-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="466fc-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="466fc-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

