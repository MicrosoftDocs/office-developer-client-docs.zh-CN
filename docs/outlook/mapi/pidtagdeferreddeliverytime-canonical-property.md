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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401753"
---
# <a name="pidtagdeferreddeliverytime-canonical-property"></a><span data-ttu-id="b2314-103">PidTagDeferredDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="b2314-103">PidTagDeferredDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="b2314-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2314-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2314-105">包含的日期和时间当邮件发件人要发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="b2314-105">Contains the date and time when a message sender wants a message delivered.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b2314-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b2314-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b2314-107">PR_DEFERRED_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="b2314-107">PR_DEFERRED_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="b2314-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b2314-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b2314-109">0x000F</span><span class="sxs-lookup"><span data-stu-id="b2314-109">0x000F</span></span>  <br/> |
|<span data-ttu-id="b2314-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b2314-110">Data type:</span></span>  <br/> |<span data-ttu-id="b2314-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="b2314-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="b2314-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b2314-112">Area:</span></span>  <br/> |<span data-ttu-id="b2314-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="b2314-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b2314-114">说明</span><span class="sxs-lookup"><span data-stu-id="b2314-114">Remarks</span></span>

<span data-ttu-id="b2314-115">MAPI 不会执行延迟的传送;它是基础消息系统的选项来处理推迟的传递。</span><span class="sxs-lookup"><span data-stu-id="b2314-115">MAPI does not perform the deferred delivery; it is an option of the underlying messaging system to handle deferred delivery.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b2314-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="b2314-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b2314-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="b2314-117">Protocol specifications</span></span>

<span data-ttu-id="b2314-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b2314-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b2314-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b2314-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b2314-120">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b2314-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b2314-121">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="b2314-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b2314-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b2314-122">Header files</span></span>

<span data-ttu-id="b2314-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b2314-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="b2314-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b2314-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="b2314-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b2314-125">Mapitags.h</span></span>
  
> <span data-ttu-id="b2314-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b2314-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b2314-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2314-127">See also</span></span>



[<span data-ttu-id="b2314-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b2314-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b2314-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b2314-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b2314-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b2314-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b2314-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b2314-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

