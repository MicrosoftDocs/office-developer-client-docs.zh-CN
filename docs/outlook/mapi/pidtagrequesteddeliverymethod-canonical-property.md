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
ms.openlocfilehash: ecfed5684ba2166c1c00c1fd07fa074b4ce9fd79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331414"
---
# <a name="pidtagrequesteddeliverymethod-canonical-property"></a><span data-ttu-id="c002c-103">PidTagRequestedDeliveryMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="c002c-103">PidTagRequestedDeliveryMethod Canonical Property</span></span>

  
  
<span data-ttu-id="c002c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c002c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c002c-105">此属性包含以邮件发件人的首选项顺序排列的传递方法 (服务提供程序) 的二进制数组。</span><span class="sxs-lookup"><span data-stu-id="c002c-105">This property contains a binary array of delivery methods (service providers), in the order of a message sender's preference.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c002c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c002c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c002c-107">PR_REQUESTED_DELIVERY_METHOD</span><span class="sxs-lookup"><span data-stu-id="c002c-107">PR_REQUESTED_DELIVERY_METHOD</span></span>  <br/> |
|<span data-ttu-id="c002c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c002c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c002c-109">0x0C18</span><span class="sxs-lookup"><span data-stu-id="c002c-109">0x0C18</span></span>  <br/> |
|<span data-ttu-id="c002c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c002c-110">Data type:</span></span>  <br/> |<span data-ttu-id="c002c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c002c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c002c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c002c-112">Area:</span></span>  <br/> |<span data-ttu-id="c002c-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="c002c-113">MAPI Recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c002c-114">注解</span><span class="sxs-lookup"><span data-stu-id="c002c-114">Remarks</span></span>

<span data-ttu-id="c002c-115">此属性中包含的数组包含 ASN。1个每个服务提供程序的标识符。</span><span class="sxs-lookup"><span data-stu-id="c002c-115">The array contained in the this property consists of ASN.1 identifiers for each of the service providers.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c002c-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="c002c-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c002c-117">头文件</span><span class="sxs-lookup"><span data-stu-id="c002c-117">Header files</span></span>

<span data-ttu-id="c002c-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c002c-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="c002c-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c002c-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="c002c-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c002c-120">Mapitags.h</span></span>
  
> <span data-ttu-id="c002c-121">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c002c-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c002c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c002c-122">See also</span></span>



[<span data-ttu-id="c002c-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c002c-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c002c-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c002c-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c002c-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c002c-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c002c-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c002c-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

