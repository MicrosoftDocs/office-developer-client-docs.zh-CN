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
ms.openlocfilehash: 98dfdab24d2c4170609d9db1c3104a3f17436736
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578064"
---
# <a name="pidlidtodosubordinal-canonical-property"></a><span data-ttu-id="0d0fc-103">PidLidToDoSubOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d0fc-103">PidLidToDoSubOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="0d0fc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d0fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d0fc-105">**DispidToDoOrdinalDate** ([PidLidToDoOrdinalDate](pidlidtodoordinaldate-canonical-property.md)) 属性排序对象和领结结果时，作为领结分词系统。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-105">Acts as a tie breaker when the **dispidToDoOrdinalDate** ([PidLidToDoOrdinalDate](pidlidtodoordinaldate-canonical-property.md)) property sorts objects and the result in a tie.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d0fc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0d0fc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0d0fc-107">dispidToDoSubOrdinal</span><span class="sxs-lookup"><span data-stu-id="0d0fc-107">dispidToDoSubOrdinal</span></span>  <br/> |
|<span data-ttu-id="0d0fc-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="0d0fc-108">Property set:</span></span>  <br/> |<span data-ttu-id="0d0fc-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="0d0fc-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="0d0fc-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="0d0fc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0d0fc-111">0x000085A1</span><span class="sxs-lookup"><span data-stu-id="0d0fc-111">0x000085A1</span></span>  <br/> |
|<span data-ttu-id="0d0fc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0d0fc-112">Data type:</span></span>  <br/> |<span data-ttu-id="0d0fc-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0d0fc-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0d0fc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0d0fc-114">Area:</span></span>  <br/> |<span data-ttu-id="0d0fc-115">Task</span><span class="sxs-lookup"><span data-stu-id="0d0fc-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d0fc-116">注解</span><span class="sxs-lookup"><span data-stu-id="0d0fc-116">Remarks</span></span>

<span data-ttu-id="0d0fc-117">如果使用，必须按字典序按此属性。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-117">If used, this property must be sorted lexicographically.</span></span> <span data-ttu-id="0d0fc-118">字符串的组件字符必须包含仅数字 0 到 9。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-118">The component characters of the string must consist of only the numerals zero through nine.</span></span> <span data-ttu-id="0d0fc-119">此属性应最初设置为"5555555"。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-119">This property should be initially set to "5555555".</span></span> <span data-ttu-id="0d0fc-120">此属性的长度不得超过 254 个字符 （不包括 NULL 终止符）。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-120">The length of this property must not exceed 254 characters (excluding the terminating NULL character).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0d0fc-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="0d0fc-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0d0fc-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="0d0fc-122">Protocol specifications</span></span>

<span data-ttu-id="0d0fc-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d0fc-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d0fc-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0d0fc-125">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0d0fc-125">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0d0fc-126">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-126">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0d0fc-127">头文件</span><span class="sxs-lookup"><span data-stu-id="0d0fc-127">Header files</span></span>

<span data-ttu-id="0d0fc-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0d0fc-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="0d0fc-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0d0fc-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0d0fc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d0fc-130">See also</span></span>



[<span data-ttu-id="0d0fc-131">PidLidToDoOrdinalDate 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d0fc-131">PidLidToDoOrdinalDate Canonical Property</span></span>](pidlidtodoordinaldate-canonical-property.md)


[<span data-ttu-id="0d0fc-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0d0fc-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0d0fc-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0d0fc-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0d0fc-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0d0fc-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0d0fc-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0d0fc-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

