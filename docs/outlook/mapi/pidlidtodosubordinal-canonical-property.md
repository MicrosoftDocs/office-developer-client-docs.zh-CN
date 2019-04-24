---
title: PidLidToDoSubOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoSubOrdinal
api_type:
- COM
ms.assetid: e3bc15ef-155e-49fd-88e5-64713df9b939
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c4ea125a5bde89e0885be4c04e3f106f202b1e18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344917"
---
# <a name="pidlidtodosubordinal-canonical-property"></a><span data-ttu-id="e6cf3-103">PidLidToDoSubOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6cf3-103">PidLidToDoSubOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="e6cf3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6cf3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6cf3-105">当**dispidToDoOrdinalDate** ([PidLidToDoOrdinalDate](pidlidtodoordinaldate-canonical-property.md)) 属性对对象进行排序, 并对其产生的关联时, 充当关联断开项。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-105">Acts as a tie breaker when the **dispidToDoOrdinalDate** ([PidLidToDoOrdinalDate](pidlidtodoordinaldate-canonical-property.md)) property sorts objects and the result in a tie.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e6cf3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6cf3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6cf3-107">dispidToDoSubOrdinal</span><span class="sxs-lookup"><span data-stu-id="e6cf3-107">dispidToDoSubOrdinal</span></span>  <br/> |
|<span data-ttu-id="e6cf3-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="e6cf3-108">Property set:</span></span>  <br/> |<span data-ttu-id="e6cf3-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="e6cf3-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="e6cf3-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="e6cf3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e6cf3-111">0x000085A1</span><span class="sxs-lookup"><span data-stu-id="e6cf3-111">0x000085A1</span></span>  <br/> |
|<span data-ttu-id="e6cf3-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6cf3-112">Data type:</span></span>  <br/> |<span data-ttu-id="e6cf3-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e6cf3-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e6cf3-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e6cf3-114">Area:</span></span>  <br/> |<span data-ttu-id="e6cf3-115">任务</span><span class="sxs-lookup"><span data-stu-id="e6cf3-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6cf3-116">注解</span><span class="sxs-lookup"><span data-stu-id="e6cf3-116">Remarks</span></span>

<span data-ttu-id="e6cf3-117">如果使用此属性, 则必须对 lexicographically 进行排序。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-117">If used, this property must be sorted lexicographically.</span></span> <span data-ttu-id="e6cf3-118">字符串的组件字符必须仅包含从0到9的数字。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-118">The component characters of the string must consist of only the numerals zero through nine.</span></span> <span data-ttu-id="e6cf3-119">此属性最初应设置为 "5555555"。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-119">This property should be initially set to "5555555".</span></span> <span data-ttu-id="e6cf3-120">此属性的长度不得超过254个字符 (终止的 NULL 字符除外)。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-120">The length of this property must not exceed 254 characters (excluding the terminating NULL character).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e6cf3-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6cf3-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6cf3-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6cf3-122">Protocol specifications</span></span>

<span data-ttu-id="e6cf3-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6cf3-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6cf3-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6cf3-125">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6cf3-125">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6cf3-126">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6cf3-127">头文件</span><span class="sxs-lookup"><span data-stu-id="e6cf3-127">Header files</span></span>

<span data-ttu-id="e6cf3-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e6cf3-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6cf3-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6cf3-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6cf3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6cf3-130">See also</span></span>



[<span data-ttu-id="e6cf3-131">PidLidToDoOrdinalDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6cf3-131">PidLidToDoOrdinalDate Canonical Property</span></span>](pidlidtodoordinaldate-canonical-property.md)


[<span data-ttu-id="e6cf3-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6cf3-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6cf3-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6cf3-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6cf3-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6cf3-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6cf3-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6cf3-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

