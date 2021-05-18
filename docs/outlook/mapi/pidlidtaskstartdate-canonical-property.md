---
title: PidLidTaskStartDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStartDate
api_type:
- COM
ms.assetid: fe87eb3d-21d1-45bb-b848-e141ce1be6a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3bc475292e47a9ad8dd9565e17640ef95e7b3c76
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316679"
---
# <a name="pidlidtaskstartdate-canonical-property"></a><span data-ttu-id="6d042-103">PidLidTaskStartDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d042-103">PidLidTaskStartDate Canonical Property</span></span>

  
  
<span data-ttu-id="6d042-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6d042-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6d042-105">用户期望开始任务的日期。</span><span class="sxs-lookup"><span data-stu-id="6d042-105">The date when the user expects to begin the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6d042-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6d042-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6d042-107">dispidTaskStartDate</span><span class="sxs-lookup"><span data-stu-id="6d042-107">dispidTaskStartDate</span></span>  <br/> |
|<span data-ttu-id="6d042-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="6d042-108">Property set:</span></span>  <br/> |<span data-ttu-id="6d042-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="6d042-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="6d042-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="6d042-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6d042-111">0x00008104</span><span class="sxs-lookup"><span data-stu-id="6d042-111">0x00008104</span></span>  <br/> |
|<span data-ttu-id="6d042-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6d042-112">Data type:</span></span>  <br/> |<span data-ttu-id="6d042-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="6d042-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="6d042-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6d042-114">Area:</span></span>  <br/> |<span data-ttu-id="6d042-115">任务</span><span class="sxs-lookup"><span data-stu-id="6d042-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6d042-116">备注</span><span class="sxs-lookup"><span data-stu-id="6d042-116">Remarks</span></span>

<span data-ttu-id="6d042-117">如果此属性值未设置，则任务没有开始日期。</span><span class="sxs-lookup"><span data-stu-id="6d042-117">If this property value is left unset, the task does not have a start date.</span></span> <span data-ttu-id="6d042-118">值"0x5AE980E0" (1，525，252，320) 还意味着任务没有开始日期。</span><span class="sxs-lookup"><span data-stu-id="6d042-118">A value of "0x5AE980E0" (1,525,252,320) also means that the task does not have a start date.</span></span> <span data-ttu-id="6d042-119">如果任务具有开始日期，则值必须具有午夜的时间部分，并且还必须设置 **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) 和 **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="6d042-119">If the task has a start date, the value must have a time component of midnight, and the **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) and **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) properties must also be set.</span></span>
  
<span data-ttu-id="6d042-120">此属性由信息标记协议规范以及位于 [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)Task-Related对象协议规范共享。</span><span class="sxs-lookup"><span data-stu-id="6d042-120">This property is shared by the Informational Flagging Protocol Specification and Task-Related Object Protocol Specification located in [[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6d042-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="6d042-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6d042-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="6d042-122">Protocol specifications</span></span>

<span data-ttu-id="6d042-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d042-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6d042-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="6d042-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6d042-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d042-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6d042-126">指定对联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6d042-126">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6d042-127">头文件</span><span class="sxs-lookup"><span data-stu-id="6d042-127">Header files</span></span>

<span data-ttu-id="6d042-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6d042-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="6d042-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6d042-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6d042-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d042-130">See also</span></span>



[<span data-ttu-id="6d042-131">PidLidTaskDueDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d042-131">PidLidTaskDueDate Canonical Property</span></span>](pidlidtaskduedate-canonical-property.md)
  
[<span data-ttu-id="6d042-132">PidLidCommonStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d042-132">PidLidCommonStart Canonical Property</span></span>](pidlidcommonstart-canonical-property.md)


[<span data-ttu-id="6d042-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6d042-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6d042-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d042-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6d042-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6d042-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6d042-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6d042-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

