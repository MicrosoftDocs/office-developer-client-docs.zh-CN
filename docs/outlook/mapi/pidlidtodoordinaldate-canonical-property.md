---
title: PidLidToDoOrdinalDate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoOrdinalDate
api_type:
- COM
ms.assetid: b6a500fc-07f4-4788-ae46-d179a96a48e2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d708424ccb15be15746fe8a33eea73a8e0f99323
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777122"
---
# <a name="pidlidtodoordinaldate-canonical-property"></a><span data-ttu-id="879c7-103">PidLidToDoOrdinalDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="879c7-103">PidLidToDoOrdinalDate Canonical Property</span></span>

  
  
<span data-ttu-id="879c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="879c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="879c7-105">确定合并待办事项列表中的对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="879c7-105">Determines the sort order of objects in a consolidated to-do list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="879c7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="879c7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="879c7-107">dispidToDoOrdinalDate</span><span class="sxs-lookup"><span data-stu-id="879c7-107">dispidToDoOrdinalDate</span></span>  <br/> |
|<span data-ttu-id="879c7-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="879c7-108">Property set:</span></span>  <br/> |<span data-ttu-id="879c7-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="879c7-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="879c7-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="879c7-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="879c7-111">0x000085A0</span><span class="sxs-lookup"><span data-stu-id="879c7-111">0x000085A0</span></span>  <br/> |
|<span data-ttu-id="879c7-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="879c7-112">Data type:</span></span>  <br/> |<span data-ttu-id="879c7-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="879c7-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="879c7-114">区域：</span><span class="sxs-lookup"><span data-stu-id="879c7-114">Area:</span></span>  <br/> |<span data-ttu-id="879c7-115">Task</span><span class="sxs-lookup"><span data-stu-id="879c7-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="879c7-116">说明</span><span class="sxs-lookup"><span data-stu-id="879c7-116">Remarks</span></span>

<span data-ttu-id="879c7-117">标记对象后，此属性应设置为当前时间以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="879c7-117">When an object is flagged, this property should be set to the current time in Coordinated Universal Time (UTC).</span></span> 
  
<span data-ttu-id="879c7-118">如果客户端允许用户重新排序通过拖动合并的任务列表或其他机制中的任务，这些用户可以使用任何合适的算法，以便此属性用作 sor 在正确的位置显示任务确定此属性的新值做到的一字段。</span><span class="sxs-lookup"><span data-stu-id="879c7-118">If the client allows a user to reorder tasks within the consolidated task list via dragging or other mechanisms, they can use any suitable algorithm to determine the new value of this property so that the task appears in the correct place when this property is used as a sorting field.</span></span>
  
<span data-ttu-id="879c7-119">当此属性用于对对象和领结排序结果进行排序时， **dispidToDoSubOrdinal** ([PidLidToDoSubOrdinal](pidlidtodosubordinal-canonical-property.md)) 属性用作领结分词系统。</span><span class="sxs-lookup"><span data-stu-id="879c7-119">When this property is used to sort objects and the sort results in a tie, the **dispidToDoSubOrdinal** ([PidLidToDoSubOrdinal](pidlidtodosubordinal-canonical-property.md)) property is used as a tie breaker.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="879c7-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="879c7-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="879c7-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="879c7-121">Protocol specifications</span></span>

<span data-ttu-id="879c7-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="879c7-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="879c7-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="879c7-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="879c7-124">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="879c7-124">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="879c7-125">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="879c7-125">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="879c7-126">头文件</span><span class="sxs-lookup"><span data-stu-id="879c7-126">Header files</span></span>

<span data-ttu-id="879c7-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="879c7-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="879c7-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="879c7-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="879c7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="879c7-129">See also</span></span>



[<span data-ttu-id="879c7-130">PidLidToDoSubOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="879c7-130">PidLidToDoSubOrdinal Canonical Property</span></span>](pidlidtodosubordinal-canonical-property.md)


[<span data-ttu-id="879c7-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="879c7-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="879c7-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="879c7-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="879c7-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="879c7-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="879c7-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="879c7-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

