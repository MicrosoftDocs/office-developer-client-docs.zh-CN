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
ms.openlocfilehash: b0c5e3019efeeb0b9788d81e8730e976bfcc9d75
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401585"
---
# <a name="pidlidtodoordinaldate-canonical-property"></a><span data-ttu-id="0111c-103">PidLidToDoOrdinalDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="0111c-103">PidLidToDoOrdinalDate Canonical Property</span></span>

  
  
<span data-ttu-id="0111c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0111c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0111c-105">确定合并待办事项列表中的对象的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="0111c-105">Determines the sort order of objects in a consolidated to-do list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0111c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0111c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0111c-107">dispidToDoOrdinalDate</span><span class="sxs-lookup"><span data-stu-id="0111c-107">dispidToDoOrdinalDate</span></span>  <br/> |
|<span data-ttu-id="0111c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="0111c-108">Property set:</span></span>  <br/> |<span data-ttu-id="0111c-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="0111c-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="0111c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="0111c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0111c-111">0x000085A0</span><span class="sxs-lookup"><span data-stu-id="0111c-111">0x000085A0</span></span>  <br/> |
|<span data-ttu-id="0111c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0111c-112">Data type:</span></span>  <br/> |<span data-ttu-id="0111c-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="0111c-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="0111c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0111c-114">Area:</span></span>  <br/> |<span data-ttu-id="0111c-115">Task</span><span class="sxs-lookup"><span data-stu-id="0111c-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0111c-116">说明</span><span class="sxs-lookup"><span data-stu-id="0111c-116">Remarks</span></span>

<span data-ttu-id="0111c-117">标记对象后，此属性应设置为当前时间以协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="0111c-117">When an object is flagged, this property should be set to the current time in Coordinated Universal Time (UTC).</span></span> 
  
<span data-ttu-id="0111c-118">如果客户端允许用户重新排序通过拖动合并的任务列表或其他机制中的任务，这些用户可以使用任何合适的算法，以便此属性用作 sor 在正确的位置显示任务确定此属性的新值做到的一字段。</span><span class="sxs-lookup"><span data-stu-id="0111c-118">If the client allows a user to reorder tasks within the consolidated task list via dragging or other mechanisms, they can use any suitable algorithm to determine the new value of this property so that the task appears in the correct place when this property is used as a sorting field.</span></span>
  
<span data-ttu-id="0111c-119">当此属性用于对对象和领结排序结果进行排序时， **dispidToDoSubOrdinal** ([PidLidToDoSubOrdinal](pidlidtodosubordinal-canonical-property.md)) 属性用作领结分词系统。</span><span class="sxs-lookup"><span data-stu-id="0111c-119">When this property is used to sort objects and the sort results in a tie, the **dispidToDoSubOrdinal** ([PidLidToDoSubOrdinal](pidlidtodosubordinal-canonical-property.md)) property is used as a tie breaker.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0111c-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="0111c-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0111c-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="0111c-121">Protocol specifications</span></span>

<span data-ttu-id="0111c-122">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0111c-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0111c-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0111c-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0111c-124">[[MS OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0111c-124">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0111c-125">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="0111c-125">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0111c-126">头文件</span><span class="sxs-lookup"><span data-stu-id="0111c-126">Header files</span></span>

<span data-ttu-id="0111c-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0111c-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="0111c-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0111c-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0111c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0111c-129">See also</span></span>



[<span data-ttu-id="0111c-130">PidLidToDoSubOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="0111c-130">PidLidToDoSubOrdinal Canonical Property</span></span>](pidlidtodosubordinal-canonical-property.md)


[<span data-ttu-id="0111c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0111c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0111c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0111c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0111c-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0111c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0111c-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0111c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

