---
title: PidTagFreeBusyRangeTimestamp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyRangeTimestamp
api_type:
- HeaderDef
ms.assetid: 142d955f-f92d-485a-80c9-9c72e82af0f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24c3369d1d6db4977d26e4d31678a4f2cc5808a2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316175"
---
# <a name="pidtagfreebusyrangetimestamp-canonical-property"></a><span data-ttu-id="1f55a-103">PidTagFreeBusyRangeTimestamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f55a-103">PidTagFreeBusyRangeTimestamp Canonical Property</span></span>

  
  
<span data-ttu-id="1f55a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f55a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f55a-105">包含数据发布的时间。</span><span class="sxs-lookup"><span data-stu-id="1f55a-105">Contains the time when the data was published.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f55a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f55a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f55a-107">PR_FREEBUSY_RANGE_TIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="1f55a-107">PR_FREEBUSY_RANGE_TIMESTAMP</span></span>  <br/> |
|<span data-ttu-id="1f55a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1f55a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f55a-109">0x6868</span><span class="sxs-lookup"><span data-stu-id="1f55a-109">0x6868</span></span>  <br/> |
|<span data-ttu-id="1f55a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f55a-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f55a-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="1f55a-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="1f55a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f55a-112">Area:</span></span>  <br/> |<span data-ttu-id="1f55a-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="1f55a-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f55a-114">备注</span><span class="sxs-lookup"><span data-stu-id="1f55a-114">Remarks</span></span>

<span data-ttu-id="1f55a-115">此属性是自协调世界时 utc 时间 1601 年 1 月 1 日午夜 (分钟) 。</span><span class="sxs-lookup"><span data-stu-id="1f55a-115">This property is the number of minutes since midnight, January 1, 1601 in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1f55a-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f55a-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1f55a-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="1f55a-117">Protocol specifications</span></span>

<span data-ttu-id="1f55a-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f55a-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f55a-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="1f55a-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1f55a-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f55a-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f55a-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="1f55a-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1f55a-122">头文件</span><span class="sxs-lookup"><span data-stu-id="1f55a-122">Header files</span></span>

<span data-ttu-id="1f55a-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f55a-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f55a-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f55a-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f55a-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f55a-125">Mapitags.h</span></span>
  
> <span data-ttu-id="1f55a-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f55a-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f55a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f55a-127">See also</span></span>



[<span data-ttu-id="1f55a-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f55a-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f55a-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f55a-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f55a-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f55a-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f55a-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f55a-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

