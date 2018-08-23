---
title: PidTagFreeBusyCountMonths 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyCountMonths
api_type:
- HeaderDef
ms.assetid: 278a77f2-65ec-4281-b406-942cc416a476
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7dc8c06fca48c5f7c124a1fdf2228ebeb9da450
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569979"
---
# <a name="pidtagfreebusycountmonths-canonical-property"></a><span data-ttu-id="0a2f6-103">PidTagFreeBusyCountMonths 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a2f6-103">PidTagFreeBusyCountMonths Canonical Property</span></span>

  
  
<span data-ttu-id="0a2f6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0a2f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0a2f6-105">包含用于计算将其发布到公用文件夹的忙/闲数据范围的开始和结束日期值。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-105">Contains the value for calculating the start and end dates of the range of free/busy data to be published to public folders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0a2f6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0a2f6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0a2f6-107">PR_FREEBUSY_COUNT_MONTHS</span><span class="sxs-lookup"><span data-stu-id="0a2f6-107">PR_FREEBUSY_COUNT_MONTHS</span></span>  <br/> |
|<span data-ttu-id="0a2f6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0a2f6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0a2f6-109">0x6869</span><span class="sxs-lookup"><span data-stu-id="0a2f6-109">0x6869</span></span>  <br/> |
|<span data-ttu-id="0a2f6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0a2f6-110">Data type:</span></span>  <br/> |<span data-ttu-id="0a2f6-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0a2f6-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0a2f6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0a2f6-112">Area:</span></span>  <br/> |<span data-ttu-id="0a2f6-113">类定义消息可传送</span><span class="sxs-lookup"><span data-stu-id="0a2f6-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a2f6-114">注解</span><span class="sxs-lookup"><span data-stu-id="0a2f6-114">Remarks</span></span>

<span data-ttu-id="0a2f6-115">此属性的值必须大于或等于 0 且小于或等于 36。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-115">This property's value must be greater than or equal to 0 and less than or equal to 36.</span></span> <span data-ttu-id="0a2f6-116">这不是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-116">This is not a required property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0a2f6-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="0a2f6-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0a2f6-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="0a2f6-118">Protocol specifications</span></span>

<span data-ttu-id="0a2f6-119">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0a2f6-119">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0a2f6-120">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-120">Publishes the availability of a user or resource.</span></span>
    
<span data-ttu-id="0a2f6-121">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0a2f6-121">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0a2f6-122">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-122">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0a2f6-123">头文件</span><span class="sxs-lookup"><span data-stu-id="0a2f6-123">Header files</span></span>

<span data-ttu-id="0a2f6-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0a2f6-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="0a2f6-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="0a2f6-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0a2f6-126">Mapitags.h</span></span>
  
> <span data-ttu-id="0a2f6-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0a2f6-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0a2f6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a2f6-128">See also</span></span>



[<span data-ttu-id="0a2f6-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0a2f6-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0a2f6-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a2f6-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0a2f6-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0a2f6-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0a2f6-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0a2f6-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

