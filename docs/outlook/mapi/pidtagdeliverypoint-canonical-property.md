---
title: PidTagDeliveryPoint 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeliveryPoint
api_type:
- HeaderDef
ms.assetid: 715a9dbd-78f8-41e1-a76e-29448d06ec19
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e18b08bcbd76cacf7dbb5b5fd36d80d5f266364d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360877"
---
# <a name="pidtagdeliverypoint-canonical-property"></a><span data-ttu-id="b0805-103">PidTagDeliveryPoint 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0805-103">PidTagDeliveryPoint Canonical Property</span></span>

  
  
<span data-ttu-id="b0805-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0805-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0805-105">指定功能实体的性质, 方法是通过邮件是由邮件传递的, 还是已传递给收件人。</span><span class="sxs-lookup"><span data-stu-id="b0805-105">Specifies the nature of the functional entity by means of which a message was or would have been delivered to the recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b0805-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b0805-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b0805-107">PR_DELIVERY_POINT</span><span class="sxs-lookup"><span data-stu-id="b0805-107">PR_DELIVERY_POINT</span></span>  <br/> |
|<span data-ttu-id="b0805-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b0805-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b0805-109">0x0C07</span><span class="sxs-lookup"><span data-stu-id="b0805-109">0x0C07</span></span>  <br/> |
|<span data-ttu-id="b0805-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b0805-110">Data type:</span></span>  <br/> |<span data-ttu-id="b0805-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b0805-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b0805-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b0805-112">Area:</span></span>  <br/> |<span data-ttu-id="b0805-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="b0805-113">MAPI recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b0805-114">注解</span><span class="sxs-lookup"><span data-stu-id="b0805-114">Remarks</span></span>

<span data-ttu-id="b0805-115">此属性可以具有下列值之一:</span><span class="sxs-lookup"><span data-stu-id="b0805-115">This property can have exactly one of the following values:</span></span> 
  
<span data-ttu-id="b0805-116">MAPI_MH_DP_ML</span><span class="sxs-lookup"><span data-stu-id="b0805-116">MAPI_MH_DP_ML</span></span> 
  
> <span data-ttu-id="b0805-117">传递到通讯组列表, 这一传递点又可能将邮件分发给多个收件人。</span><span class="sxs-lookup"><span data-stu-id="b0805-117">Delivered to a distribution list, a delivery point which in turn may distribute the message to many recipients.</span></span>
    
<span data-ttu-id="b0805-118">MAPI_MH_DP_MS</span><span class="sxs-lookup"><span data-stu-id="b0805-118">MAPI_MH_DP_MS</span></span> 
  
> <span data-ttu-id="b0805-119">传递到邮件存储, 而不是直接传递给收件人。</span><span class="sxs-lookup"><span data-stu-id="b0805-119">Delivered to a message store instead of directly to a recipient.</span></span>
    
<span data-ttu-id="b0805-120">MAPI_MH_DP_OTHER_AU</span><span class="sxs-lookup"><span data-stu-id="b0805-120">MAPI_MH_DP_OTHER_AU</span></span> 
  
> <span data-ttu-id="b0805-121">传递给除物理传递访问单元 (PDAU) 以外的访问单元 (AU), 例如传真系统。</span><span class="sxs-lookup"><span data-stu-id="b0805-121">Delivered to an access unit (AU) other than a physical delivery access unit (PDAU), such as a FAX system.</span></span>
    
<span data-ttu-id="b0805-122">MAPI_MH_DP_PDAU</span><span class="sxs-lookup"><span data-stu-id="b0805-122">MAPI_MH_DP_PDAU</span></span> 
  
> <span data-ttu-id="b0805-123">传递给物理传递访问单元, 如 "人体邮政" 运营商。</span><span class="sxs-lookup"><span data-stu-id="b0805-123">Delivered to a physical delivery access unit, such as a human postal carrier.</span></span>
    
<span data-ttu-id="b0805-124">MAPI_MH_DP_PDS_PATRON</span><span class="sxs-lookup"><span data-stu-id="b0805-124">MAPI_MH_DP_PDS_PATRON</span></span> 
  
> <span data-ttu-id="b0805-125">传递到物理传递系统 patron, 如常规邮政邮箱。</span><span class="sxs-lookup"><span data-stu-id="b0805-125">Delivered to a physical delivery system patron, such as a conventional postal mailbox.</span></span>
    
<span data-ttu-id="b0805-126">MAPI_MH_DP_PRIVATE_UA</span><span class="sxs-lookup"><span data-stu-id="b0805-126">MAPI_MH_DP_PRIVATE_UA</span></span> 
  
> <span data-ttu-id="b0805-127">传递给私有用户代理 (UA), 例如内部邮件系统中的客户端。</span><span class="sxs-lookup"><span data-stu-id="b0805-127">Delivered to a private user agent (UA), such as a client in an in-house messaging system.</span></span>
    
<span data-ttu-id="b0805-128">MAPI_MH_DP_PUBLIC_UA</span><span class="sxs-lookup"><span data-stu-id="b0805-128">MAPI_MH_DP_PUBLIC_UA</span></span> 
  
> <span data-ttu-id="b0805-129">传递给公用用户代理或公共服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b0805-129">Delivered to a public user agent, or public service provider.</span></span>
    
<span data-ttu-id="b0805-130">默认值为 MAPI_MH_DP_PRIVATE_UA, 即 MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="b0805-130">The default value is MAPI_MH_DP_PRIVATE_UA, that is, a MAPI client.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b0805-131">相关资源</span><span class="sxs-lookup"><span data-stu-id="b0805-131">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="b0805-132">头文件</span><span class="sxs-lookup"><span data-stu-id="b0805-132">Header files</span></span>

<span data-ttu-id="b0805-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b0805-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="b0805-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b0805-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="b0805-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b0805-135">Mapitags.h</span></span>
  
> <span data-ttu-id="b0805-136">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b0805-136">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0805-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0805-137">See also</span></span>



[<span data-ttu-id="b0805-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b0805-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b0805-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0805-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b0805-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b0805-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b0805-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b0805-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

