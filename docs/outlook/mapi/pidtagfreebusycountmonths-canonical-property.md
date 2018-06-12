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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5ba76b5735687e3bb65e530b3de0d257754559c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777666"
---
# <a name="pidtagfreebusycountmonths-canonical-property"></a><span data-ttu-id="8d8c2-103">PidTagFreeBusyCountMonths 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d8c2-103">PidTagFreeBusyCountMonths Canonical Property</span></span>

  
  
<span data-ttu-id="8d8c2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8d8c2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8d8c2-105">包含用于计算将其发布到公用文件夹的忙/闲数据范围的开始和结束日期值。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-105">Contains the value for calculating the start and end dates of the range of free/busy data to be published to public folders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d8c2-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="8d8c2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8d8c2-107">PR_FREEBUSY_COUNT_MONTHS</span><span class="sxs-lookup"><span data-stu-id="8d8c2-107">PR_FREEBUSY_COUNT_MONTHS</span></span>  <br/> |
|<span data-ttu-id="8d8c2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8d8c2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8d8c2-109">0x6869</span><span class="sxs-lookup"><span data-stu-id="8d8c2-109">0x6869</span></span>  <br/> |
|<span data-ttu-id="8d8c2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8d8c2-110">Data type:</span></span>  <br/> |<span data-ttu-id="8d8c2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8d8c2-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8d8c2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8d8c2-112">Area:</span></span>  <br/> |<span data-ttu-id="8d8c2-113">类定义消息可传送</span><span class="sxs-lookup"><span data-stu-id="8d8c2-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8d8c2-114">备注</span><span class="sxs-lookup"><span data-stu-id="8d8c2-114">Remarks</span></span>

<span data-ttu-id="8d8c2-115">此属性的值必须大于或等于 0 且小于或等于 36。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-115">This property's value must be greater than or equal to 0 and less than or equal to 36.</span></span> <span data-ttu-id="8d8c2-116">这不是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-116">This is not a required property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8d8c2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="8d8c2-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8d8c2-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="8d8c2-118">Protocol specifications</span></span>

<span data-ttu-id="8d8c2-119">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d8c2-119">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d8c2-120">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-120">Publishes the availability of a user or resource.</span></span>
    
<span data-ttu-id="8d8c2-121">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d8c2-121">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d8c2-122">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-122">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8d8c2-123">头文件</span><span class="sxs-lookup"><span data-stu-id="8d8c2-123">Header files</span></span>

<span data-ttu-id="8d8c2-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8d8c2-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="8d8c2-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="8d8c2-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8d8c2-126">Mapitags.h</span></span>
  
> <span data-ttu-id="8d8c2-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8d8c2-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8d8c2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d8c2-128">See also</span></span>



[<span data-ttu-id="8d8c2-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8d8c2-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8d8c2-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d8c2-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8d8c2-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8d8c2-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8d8c2-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8d8c2-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

