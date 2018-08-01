---
title: PidLidTaskOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOrdinal
api_type:
- COM
ms.assetid: 1021860e-4c40-4c22-aa68-b568d046aaf7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 033bc038988373b11f3eac863a256717624999f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777094"
---
# <a name="pidlidtaskordinal-canonical-property"></a><span data-ttu-id="03e62-103">PidLidTaskOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="03e62-103">PidLidTaskOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="03e62-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="03e62-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="03e62-105">提供的辅助手段自定义排序的任务。</span><span class="sxs-lookup"><span data-stu-id="03e62-105">Provides an aid to custom sorting tasks.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="03e62-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="03e62-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="03e62-107">dispidTaskOrdinal</span><span class="sxs-lookup"><span data-stu-id="03e62-107">dispidTaskOrdinal</span></span>  <br/> |
|<span data-ttu-id="03e62-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="03e62-108">Property set:</span></span>  <br/> |<span data-ttu-id="03e62-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="03e62-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="03e62-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="03e62-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="03e62-111">0x00008123</span><span class="sxs-lookup"><span data-stu-id="03e62-111">0x00008123</span></span>  <br/> |
|<span data-ttu-id="03e62-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="03e62-112">Data type:</span></span>  <br/> |<span data-ttu-id="03e62-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="03e62-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="03e62-114">区域：</span><span class="sxs-lookup"><span data-stu-id="03e62-114">Area:</span></span>  <br/> |<span data-ttu-id="03e62-115">Task</span><span class="sxs-lookup"><span data-stu-id="03e62-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03e62-116">说明</span><span class="sxs-lookup"><span data-stu-id="03e62-116">Remarks</span></span>

<span data-ttu-id="03e62-117">此属性可能仍未设置。</span><span class="sxs-lookup"><span data-stu-id="03e62-117">This property may be left unset.</span></span> <span data-ttu-id="03e62-118">如果设置，其值必须大于"0x800186A0"(-2,147,383,648) 和少于"0x7FFE7960"(2,147,383,648)，并且必须唯一同一文件夹中的任务。</span><span class="sxs-lookup"><span data-stu-id="03e62-118">If set, its value must be greater than "0x800186A0" (-2,147,383,648) and less than "0x7FFE7960" (2,147,383,648) and must be unique among tasks in the same folder.</span></span>
  
<span data-ttu-id="03e62-119">只要客户端将该属性设置为数小于负**PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) 的文件夹的属性的当前值，客户端还必须更新**PR_ORDINAL_MOST**的文件夹。</span><span class="sxs-lookup"><span data-stu-id="03e62-119">Whenever the client sets this property to a number less than the negative of the current value of the **PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) property of the folder, the client must also update **PR_ORDINAL_MOST** on the folder.</span></span> 
  
<span data-ttu-id="03e62-120">文件夹的**PR_ORDINAL_MOST**属性提供高效的方法来确定在同一文件夹中的任务之间的唯一值。</span><span class="sxs-lookup"><span data-stu-id="03e62-120">The **PR_ORDINAL_MOST** property of the folder provides an efficient way to determine a unique value among tasks in the same folder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="03e62-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="03e62-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="03e62-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="03e62-122">Protocol specifications</span></span>

<span data-ttu-id="03e62-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03e62-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03e62-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="03e62-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="03e62-125">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03e62-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03e62-126">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="03e62-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="03e62-127">头文件</span><span class="sxs-lookup"><span data-stu-id="03e62-127">Header files</span></span>

<span data-ttu-id="03e62-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="03e62-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="03e62-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="03e62-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03e62-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03e62-130">See also</span></span>



[<span data-ttu-id="03e62-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="03e62-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="03e62-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="03e62-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="03e62-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="03e62-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="03e62-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="03e62-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

