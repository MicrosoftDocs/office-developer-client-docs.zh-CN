---
title: PidTagScheduleInfoResourceType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoResourceType
api_type:
- COM
ms.assetid: 9f253378-0a2d-47e3-82d3-8055b5f776dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fbcc149d6c5b5806a6514da4a3fb8e5615c9bc98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359764"
---
# <a name="pidtagscheduleinforesourcetype-canonical-property"></a><span data-ttu-id="6af16-103">PidTagScheduleInfoResourceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="6af16-103">PidTagScheduleInfoResourceType Canonical Property</span></span>

  
  
<span data-ttu-id="6af16-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6af16-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6af16-105">包含的值必须设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="6af16-105">Contains a value that must be set to zero (0).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6af16-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6af16-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6af16-107">PR_SCHDINFO_RESOURCE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6af16-107">PR_SCHDINFO_RESOURCE_TYPE</span></span>  <br/> |
|<span data-ttu-id="6af16-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6af16-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6af16-109">0x6841</span><span class="sxs-lookup"><span data-stu-id="6af16-109">0x6841</span></span>  <br/> |
|<span data-ttu-id="6af16-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6af16-110">Data type:</span></span>  <br/> |<span data-ttu-id="6af16-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6af16-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6af16-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6af16-112">Area:</span></span>  <br/> |<span data-ttu-id="6af16-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="6af16-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6af16-114">注解</span><span class="sxs-lookup"><span data-stu-id="6af16-114">Remarks</span></span>

<span data-ttu-id="6af16-115">发送时, 必须将此属性设置为零 (0), 并在收到时忽略。</span><span class="sxs-lookup"><span data-stu-id="6af16-115">This property must be set to zero (0) when sent and ignored upon receipt.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6af16-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6af16-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6af16-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6af16-117">Protocol specifications</span></span>

<span data-ttu-id="6af16-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6af16-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6af16-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6af16-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6af16-120">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6af16-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6af16-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="6af16-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6af16-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6af16-122">Header files</span></span>

<span data-ttu-id="6af16-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6af16-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6af16-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6af16-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6af16-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6af16-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6af16-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6af16-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6af16-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6af16-127">See also</span></span>



[<span data-ttu-id="6af16-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6af16-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6af16-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6af16-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6af16-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6af16-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6af16-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6af16-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

