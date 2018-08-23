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
ms.openlocfilehash: 2d8157c761cd21d5c8fcdf04948646d8102e774a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580136"
---
# <a name="pidtagdeliverypoint-canonical-property"></a><span data-ttu-id="242c8-103">PidTagDeliveryPoint 规范属性</span><span class="sxs-lookup"><span data-stu-id="242c8-103">PidTagDeliveryPoint Canonical Property</span></span>

  
  
<span data-ttu-id="242c8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="242c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="242c8-105">指定一条消息已通过其或已传递给收件人功能实体的特性。</span><span class="sxs-lookup"><span data-stu-id="242c8-105">Specifies the nature of the functional entity by means of which a message was or would have been delivered to the recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="242c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="242c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="242c8-107">PR_DELIVERY_POINT</span><span class="sxs-lookup"><span data-stu-id="242c8-107">PR_DELIVERY_POINT</span></span>  <br/> |
|<span data-ttu-id="242c8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="242c8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="242c8-109">0x0C07</span><span class="sxs-lookup"><span data-stu-id="242c8-109">0x0C07</span></span>  <br/> |
|<span data-ttu-id="242c8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="242c8-110">Data type:</span></span>  <br/> |<span data-ttu-id="242c8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="242c8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="242c8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="242c8-112">Area:</span></span>  <br/> |<span data-ttu-id="242c8-113">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="242c8-113">MAPI recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="242c8-114">注解</span><span class="sxs-lookup"><span data-stu-id="242c8-114">Remarks</span></span>

<span data-ttu-id="242c8-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="242c8-115">This property can have exactly one of the following values:</span></span> 
  
<span data-ttu-id="242c8-116">MAPI_MH_DP_ML</span><span class="sxs-lookup"><span data-stu-id="242c8-116">MAPI_MH_DP_ML</span></span> 
  
> <span data-ttu-id="242c8-117">传递给通讯组列表，收信人地址的反过来可能分发很多个收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="242c8-117">Delivered to a distribution list, a delivery point which in turn may distribute the message to many recipients.</span></span>
    
<span data-ttu-id="242c8-118">MAPI_MH_DP_MS</span><span class="sxs-lookup"><span data-stu-id="242c8-118">MAPI_MH_DP_MS</span></span> 
  
> <span data-ttu-id="242c8-119">传递给而不是直接向收件人的消息存储。</span><span class="sxs-lookup"><span data-stu-id="242c8-119">Delivered to a message store instead of directly to a recipient.</span></span>
    
<span data-ttu-id="242c8-120">MAPI_MH_DP_OTHER_AU</span><span class="sxs-lookup"><span data-stu-id="242c8-120">MAPI_MH_DP_OTHER_AU</span></span> 
  
> <span data-ttu-id="242c8-121">物理传递访问单位 (PDAU)，如传真系统之外送达访问单元 (AU)。</span><span class="sxs-lookup"><span data-stu-id="242c8-121">Delivered to an access unit (AU) other than a physical delivery access unit (PDAU), such as a FAX system.</span></span>
    
<span data-ttu-id="242c8-122">MAPI_MH_DP_PDAU</span><span class="sxs-lookup"><span data-stu-id="242c8-122">MAPI_MH_DP_PDAU</span></span> 
  
> <span data-ttu-id="242c8-123">发送到物理传递访问单位，如 human 邮政运营商。</span><span class="sxs-lookup"><span data-stu-id="242c8-123">Delivered to a physical delivery access unit, such as a human postal carrier.</span></span>
    
<span data-ttu-id="242c8-124">MAPI_MH_DP_PDS_PATRON</span><span class="sxs-lookup"><span data-stu-id="242c8-124">MAPI_MH_DP_PDS_PATRON</span></span> 
  
> <span data-ttu-id="242c8-125">发送到物理传递系统记录，如传统的邮政邮箱。</span><span class="sxs-lookup"><span data-stu-id="242c8-125">Delivered to a physical delivery system patron, such as a conventional postal mailbox.</span></span>
    
<span data-ttu-id="242c8-126">MAPI_MH_DP_PRIVATE_UA</span><span class="sxs-lookup"><span data-stu-id="242c8-126">MAPI_MH_DP_PRIVATE_UA</span></span> 
  
> <span data-ttu-id="242c8-127">例如，内部邮件系统中的客户端送达专用用户代理 (UA)。</span><span class="sxs-lookup"><span data-stu-id="242c8-127">Delivered to a private user agent (UA), such as a client in an in-house messaging system.</span></span>
    
<span data-ttu-id="242c8-128">MAPI_MH_DP_PUBLIC_UA</span><span class="sxs-lookup"><span data-stu-id="242c8-128">MAPI_MH_DP_PUBLIC_UA</span></span> 
  
> <span data-ttu-id="242c8-129">传递到公共用户代理或公共服务提供商。</span><span class="sxs-lookup"><span data-stu-id="242c8-129">Delivered to a public user agent, or public service provider.</span></span>
    
<span data-ttu-id="242c8-130">默认值是 MAPI_MH_DP_PRIVATE_UA，即，MAPI 客户端。</span><span class="sxs-lookup"><span data-stu-id="242c8-130">The default value is MAPI_MH_DP_PRIVATE_UA, that is, a MAPI client.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="242c8-131">相关资源</span><span class="sxs-lookup"><span data-stu-id="242c8-131">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="242c8-132">头文件</span><span class="sxs-lookup"><span data-stu-id="242c8-132">Header files</span></span>

<span data-ttu-id="242c8-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="242c8-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="242c8-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="242c8-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="242c8-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="242c8-135">Mapitags.h</span></span>
  
> <span data-ttu-id="242c8-136">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="242c8-136">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="242c8-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="242c8-137">See also</span></span>



[<span data-ttu-id="242c8-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="242c8-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="242c8-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="242c8-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="242c8-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="242c8-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="242c8-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="242c8-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

