---
title: PidLidTaskDateCompleted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskDateCompleted
api_type:
- COM
ms.assetid: ae384529-55e2-4da1-9a41-acc292591a7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3096e7ab2133d2984be0534cb091d61d2c7157bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303211"
---
# <a name="pidlidtaskdatecompleted-canonical-property"></a><span data-ttu-id="105e0-103">PidLidTaskDateCompleted 规范属性</span><span class="sxs-lookup"><span data-stu-id="105e0-103">PidLidTaskDateCompleted Canonical Property</span></span>

  
  
<span data-ttu-id="105e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="105e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="105e0-105">指定用户完成任务的日期。</span><span class="sxs-lookup"><span data-stu-id="105e0-105">Specifies the date when the user completes the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="105e0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="105e0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="105e0-107">dispidTaskDateCompleted</span><span class="sxs-lookup"><span data-stu-id="105e0-107">dispidTaskDateCompleted</span></span>  <br/> |
|<span data-ttu-id="105e0-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="105e0-108">Property set:</span></span>  <br/> |<span data-ttu-id="105e0-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="105e0-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="105e0-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="105e0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="105e0-111">0x0000810F</span><span class="sxs-lookup"><span data-stu-id="105e0-111">0x0000810F</span></span>  <br/> |
|<span data-ttu-id="105e0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="105e0-112">Data type:</span></span>  <br/> |<span data-ttu-id="105e0-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="105e0-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="105e0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="105e0-114">Area:</span></span>  <br/> |<span data-ttu-id="105e0-115">任务</span><span class="sxs-lookup"><span data-stu-id="105e0-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="105e0-116">备注</span><span class="sxs-lookup"><span data-stu-id="105e0-116">Remarks</span></span>

<span data-ttu-id="105e0-117">如果设置此属性，则此属性必须具有本地时区午夜的时间部分，以 UTC 格式转换为协调世界时 (时间) 。</span><span class="sxs-lookup"><span data-stu-id="105e0-117">If set, this property must have a time component of midnight in the local time zone, converted to Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="105e0-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="105e0-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="105e0-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="105e0-119">Protocol specifications</span></span>

<span data-ttu-id="105e0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="105e0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="105e0-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="105e0-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="105e0-122">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="105e0-122">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="105e0-123">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="105e0-123">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="105e0-124">头文件</span><span class="sxs-lookup"><span data-stu-id="105e0-124">Header files</span></span>

<span data-ttu-id="105e0-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="105e0-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="105e0-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="105e0-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="105e0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="105e0-127">See also</span></span>



[<span data-ttu-id="105e0-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="105e0-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="105e0-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="105e0-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="105e0-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="105e0-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="105e0-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="105e0-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

