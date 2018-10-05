---
title: PidTagFreeBusyPublishStart 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyPublishStart
api_type:
- HeaderDef
ms.assetid: d059f913-3d61-4bec-8215-5b07f0fba488
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3277ee9d0008954746890f8b33155f4e88f01766
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400374"
---
# <a name="pidtagfreebusypublishstart-canonical-property"></a><span data-ttu-id="6f893-103">PidTagFreeBusyPublishStart 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f893-103">PidTagFreeBusyPublishStart Canonical Property</span></span>

  
  
<span data-ttu-id="6f893-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f893-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6f893-105">包含发布范围的开始时间。</span><span class="sxs-lookup"><span data-stu-id="6f893-105">Contains the start time of the publishing range.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6f893-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6f893-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6f893-107">PR_FREEBUSY_PUBLISH_START</span><span class="sxs-lookup"><span data-stu-id="6f893-107">PR_FREEBUSY_PUBLISH_START</span></span>  <br/> |
|<span data-ttu-id="6f893-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6f893-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6f893-109">0x6847</span><span class="sxs-lookup"><span data-stu-id="6f893-109">0x6847</span></span>  <br/> |
|<span data-ttu-id="6f893-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6f893-110">Data type:</span></span>  <br/> |<span data-ttu-id="6f893-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6f893-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6f893-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6f893-112">Area:</span></span>  <br/> |<span data-ttu-id="6f893-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="6f893-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6f893-114">说明</span><span class="sxs-lookup"><span data-stu-id="6f893-114">Remarks</span></span>

<span data-ttu-id="6f893-115">此属性的值是自午夜开始，采用协调世界时 (UTC) 1601 年 1 月 1 日的分钟数。</span><span class="sxs-lookup"><span data-stu-id="6f893-115">The value for this property is the number of minutes since midnight, January 1, 1601 in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6f893-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6f893-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6f893-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6f893-117">Protocol specifications</span></span>

<span data-ttu-id="6f893-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f893-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f893-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6f893-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6f893-120">[[MS OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6f893-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6f893-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="6f893-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6f893-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6f893-122">Header files</span></span>

<span data-ttu-id="6f893-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6f893-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6f893-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6f893-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6f893-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6f893-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6f893-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6f893-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6f893-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f893-127">See also</span></span>



[<span data-ttu-id="6f893-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6f893-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6f893-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6f893-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6f893-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6f893-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6f893-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6f893-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

