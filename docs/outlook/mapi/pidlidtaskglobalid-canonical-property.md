---
title: PidLidTaskGlobalId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskGlobalId
api_type:
- COM
ms.assetid: 369d8c78-3cf6-4a55-ba14-9da0377d6ccf
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 33f3b8e7d3d0e0d4461c947aa8e9b3ee66373d2e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777072"
---
# <a name="pidlidtaskglobalid-canonical-property"></a><span data-ttu-id="b91da-103">PidLidTaskGlobalId 规范属性</span><span class="sxs-lookup"><span data-stu-id="b91da-103">PidLidTaskGlobalId Canonical Property</span></span>

  
  
<span data-ttu-id="b91da-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b91da-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b91da-105">查找现有任务，使用在收到任务响应或任务更新后的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b91da-105">Locates an existing task, by using a GUID, upon receipt of a task response or task update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b91da-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b91da-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b91da-107">dispidTaskGlobalObjId</span><span class="sxs-lookup"><span data-stu-id="b91da-107">dispidTaskGlobalObjId</span></span>  <br/> |
|<span data-ttu-id="b91da-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b91da-108">Property set:</span></span>  <br/> |<span data-ttu-id="b91da-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="b91da-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="b91da-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b91da-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b91da-111">0x00008519</span><span class="sxs-lookup"><span data-stu-id="b91da-111">0x00008519</span></span>  <br/> |
|<span data-ttu-id="b91da-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b91da-112">Data type:</span></span>  <br/> |<span data-ttu-id="b91da-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b91da-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b91da-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b91da-114">Area:</span></span>  <br/> |<span data-ttu-id="b91da-115">任务</span><span class="sxs-lookup"><span data-stu-id="b91da-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b91da-116">备注</span><span class="sxs-lookup"><span data-stu-id="b91da-116">Remarks</span></span>

<span data-ttu-id="b91da-117">此属性保留未分配的任务未设置。</span><span class="sxs-lookup"><span data-stu-id="b91da-117">This property is left unset for unassigned tasks.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b91da-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b91da-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b91da-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b91da-119">Protocol specifications</span></span>

<span data-ttu-id="b91da-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b91da-120">[[MS-OXPROPS] ](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b91da-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b91da-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b91da-122">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b91da-122">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b91da-123">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="b91da-123">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b91da-124">头文件</span><span class="sxs-lookup"><span data-stu-id="b91da-124">Header files</span></span>

<span data-ttu-id="b91da-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b91da-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="b91da-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b91da-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b91da-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b91da-127">See also</span></span>



[<span data-ttu-id="b91da-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b91da-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b91da-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b91da-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b91da-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b91da-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b91da-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b91da-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
