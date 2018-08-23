---
title: PidTagRequestedDeliveryMethod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRequestedDeliveryMethod
api_type:
- COM
ms.assetid: cc55089b-e389-405e-8174-f5b5ec352f78
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f18d726c1b06a6fb7f79964165bbdb9074a6d4d7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571365"
---
# <a name="pidtagrequesteddeliverymethod-canonical-property"></a><span data-ttu-id="4d37d-103">PidTagRequestedDeliveryMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d37d-103">PidTagRequestedDeliveryMethod Canonical Property</span></span>

  
  
<span data-ttu-id="4d37d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d37d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d37d-105">此属性包含邮件发件人的发挥二进制交付方法 （服务提供商） 的数组。</span><span class="sxs-lookup"><span data-stu-id="4d37d-105">This property contains a binary array of delivery methods (service providers), in the order of a message sender's preference.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d37d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4d37d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4d37d-107">PR_REQUESTED_DELIVERY_METHOD</span><span class="sxs-lookup"><span data-stu-id="4d37d-107">PR_REQUESTED_DELIVERY_METHOD</span></span>  <br/> |
|<span data-ttu-id="4d37d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4d37d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4d37d-109">0x0C18</span><span class="sxs-lookup"><span data-stu-id="4d37d-109">0x0C18</span></span>  <br/> |
|<span data-ttu-id="4d37d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4d37d-110">Data type:</span></span>  <br/> |<span data-ttu-id="4d37d-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4d37d-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4d37d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4d37d-112">Area:</span></span>  <br/> |<span data-ttu-id="4d37d-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="4d37d-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4d37d-114">注解</span><span class="sxs-lookup"><span data-stu-id="4d37d-114">Remarks</span></span>

<span data-ttu-id="4d37d-115">数组包含在此属性为每个服务提供商包含 ASN.1 标识符。</span><span class="sxs-lookup"><span data-stu-id="4d37d-115">The array contained in the this property consists of ASN.1 identifiers for each of the service providers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4d37d-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="4d37d-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="4d37d-117">头文件</span><span class="sxs-lookup"><span data-stu-id="4d37d-117">Header files</span></span>

<span data-ttu-id="4d37d-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4d37d-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="4d37d-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4d37d-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="4d37d-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4d37d-120">Mapitags.h</span></span>
  
> <span data-ttu-id="4d37d-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4d37d-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4d37d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d37d-122">See also</span></span>



[<span data-ttu-id="4d37d-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4d37d-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4d37d-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4d37d-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4d37d-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4d37d-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4d37d-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4d37d-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

