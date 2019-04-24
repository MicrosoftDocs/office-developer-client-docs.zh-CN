---
title: PidTagDeferredDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredDeliveryTime
api_type:
- HeaderDef
ms.assetid: 263ac923-692f-40d4-bdd5-116dc5c49766
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7197159fd55016454de3fa806fc30d0700ef5f3d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359925"
---
# <a name="pidtagdeferreddeliverytime-canonical-property"></a><span data-ttu-id="67ed9-103">PidTagDeferredDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="67ed9-103">PidTagDeferredDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="67ed9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67ed9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67ed9-105">包含邮件发件人希望邮件传递的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="67ed9-105">Contains the date and time when a message sender wants a message delivered.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="67ed9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="67ed9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="67ed9-107">PR_DEFERRED_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="67ed9-107">PR_DEFERRED_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="67ed9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="67ed9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="67ed9-109">0x000F</span><span class="sxs-lookup"><span data-stu-id="67ed9-109">0x000F</span></span>  <br/> |
|<span data-ttu-id="67ed9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="67ed9-110">Data type:</span></span>  <br/> |<span data-ttu-id="67ed9-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="67ed9-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="67ed9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="67ed9-112">Area:</span></span>  <br/> |<span data-ttu-id="67ed9-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="67ed9-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="67ed9-114">注解</span><span class="sxs-lookup"><span data-stu-id="67ed9-114">Remarks</span></span>

<span data-ttu-id="67ed9-115">MAPI 不执行延迟传递;它是基础邮件系统用于处理延迟传递的选项。</span><span class="sxs-lookup"><span data-stu-id="67ed9-115">MAPI does not perform the deferred delivery; it is an option of the underlying messaging system to handle deferred delivery.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="67ed9-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="67ed9-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="67ed9-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="67ed9-117">Protocol specifications</span></span>

<span data-ttu-id="67ed9-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67ed9-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67ed9-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="67ed9-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="67ed9-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="67ed9-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="67ed9-121">指定在电子邮件中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="67ed9-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="67ed9-122">头文件</span><span class="sxs-lookup"><span data-stu-id="67ed9-122">Header files</span></span>

<span data-ttu-id="67ed9-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="67ed9-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="67ed9-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="67ed9-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="67ed9-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="67ed9-125">Mapitags.h</span></span>
  
> <span data-ttu-id="67ed9-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="67ed9-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="67ed9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67ed9-127">See also</span></span>



[<span data-ttu-id="67ed9-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="67ed9-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="67ed9-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="67ed9-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="67ed9-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="67ed9-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="67ed9-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="67ed9-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

