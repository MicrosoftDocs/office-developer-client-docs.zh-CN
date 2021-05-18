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
# <a name="pidtagdeferreddeliverytime-canonical-property"></a><span data-ttu-id="6d58e-103">PidTagDeferredDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d58e-103">PidTagDeferredDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="6d58e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6d58e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6d58e-105">包含邮件发件人希望传递邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6d58e-105">Contains the date and time when a message sender wants a message delivered.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6d58e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6d58e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6d58e-107">PR_DEFERRED_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="6d58e-107">PR_DEFERRED_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="6d58e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6d58e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6d58e-109">0x000F</span><span class="sxs-lookup"><span data-stu-id="6d58e-109">0x000F</span></span>  <br/> |
|<span data-ttu-id="6d58e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6d58e-110">Data type:</span></span>  <br/> |<span data-ttu-id="6d58e-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="6d58e-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="6d58e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6d58e-112">Area:</span></span>  <br/> |<span data-ttu-id="6d58e-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="6d58e-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6d58e-114">备注</span><span class="sxs-lookup"><span data-stu-id="6d58e-114">Remarks</span></span>

<span data-ttu-id="6d58e-115">MAPI 不执行延迟传递;它是基础邮件系统的一个选项，用于处理延迟传递。</span><span class="sxs-lookup"><span data-stu-id="6d58e-115">MAPI does not perform the deferred delivery; it is an option of the underlying messaging system to handle deferred delivery.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6d58e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6d58e-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6d58e-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6d58e-117">Protocol specifications</span></span>

<span data-ttu-id="6d58e-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d58e-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6d58e-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="6d58e-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6d58e-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6d58e-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6d58e-121">指定允许对电子邮件执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="6d58e-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6d58e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6d58e-122">Header files</span></span>

<span data-ttu-id="6d58e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6d58e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6d58e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6d58e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6d58e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6d58e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6d58e-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6d58e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6d58e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d58e-127">See also</span></span>



[<span data-ttu-id="6d58e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6d58e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6d58e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6d58e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6d58e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6d58e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6d58e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6d58e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

