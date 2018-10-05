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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399394"
---
# <a name="pidtagscheduleinforesourcetype-canonical-property"></a><span data-ttu-id="b3e5b-103">PidTagScheduleInfoResourceType 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3e5b-103">PidTagScheduleInfoResourceType Canonical Property</span></span>

  
  
<span data-ttu-id="b3e5b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b3e5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b3e5b-105">包含一个值，必须设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-105">Contains a value that must be set to zero (0).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b3e5b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b3e5b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b3e5b-107">PR_SCHDINFO_RESOURCE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b3e5b-107">PR_SCHDINFO_RESOURCE_TYPE</span></span>  <br/> |
|<span data-ttu-id="b3e5b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b3e5b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b3e5b-109">0x6841</span><span class="sxs-lookup"><span data-stu-id="b3e5b-109">0x6841</span></span>  <br/> |
|<span data-ttu-id="b3e5b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b3e5b-110">Data type:</span></span>  <br/> |<span data-ttu-id="b3e5b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b3e5b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b3e5b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b3e5b-112">Area:</span></span>  <br/> |<span data-ttu-id="b3e5b-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="b3e5b-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b3e5b-114">说明</span><span class="sxs-lookup"><span data-stu-id="b3e5b-114">Remarks</span></span>

<span data-ttu-id="b3e5b-115">此属性必须设置为零 (0) 时发送和接收时被忽略。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-115">This property must be set to zero (0) when sent and ignored upon receipt.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b3e5b-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="b3e5b-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b3e5b-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="b3e5b-117">Protocol specifications</span></span>

<span data-ttu-id="b3e5b-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3e5b-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3e5b-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b3e5b-120">[[MS OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3e5b-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b3e5b-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b3e5b-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b3e5b-122">Header files</span></span>

<span data-ttu-id="b3e5b-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b3e5b-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="b3e5b-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="b3e5b-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b3e5b-125">Mapitags.h</span></span>
  
> <span data-ttu-id="b3e5b-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b3e5b-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b3e5b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3e5b-127">See also</span></span>



[<span data-ttu-id="b3e5b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b3e5b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b3e5b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b3e5b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b3e5b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b3e5b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b3e5b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b3e5b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

