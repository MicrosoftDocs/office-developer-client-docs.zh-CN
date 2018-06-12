---
title: PidTagSpoolerStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSpoolerStatus
api_type:
- COM
ms.assetid: a10d86fc-3a73-49dc-b974-ed852ec715e9
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: df52f668e91b707c0436b394186b27fdbb3a5dbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778443"
---
# <a name="pidtagspoolerstatus-canonical-property"></a><span data-ttu-id="a27c2-103">PidTagSpoolerStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="a27c2-103">PidTagSpoolerStatus Canonical Property</span></span>

  
  
<span data-ttu-id="a27c2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a27c2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a27c2-105">包含基于可供 MAPI 后台处理程序的信息消息的状态。</span><span class="sxs-lookup"><span data-stu-id="a27c2-105">Contains the status of the message based on information that is available to the MAPI spooler.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a27c2-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="a27c2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a27c2-107">PR_SPOOLER_STATUS</span><span class="sxs-lookup"><span data-stu-id="a27c2-107">PR_SPOOLER_STATUS</span></span>  <br/> |
|<span data-ttu-id="a27c2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a27c2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a27c2-109">0x0E10</span><span class="sxs-lookup"><span data-stu-id="a27c2-109">0x0E10</span></span>  <br/> |
|<span data-ttu-id="a27c2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a27c2-110">Data type:</span></span>  <br/> |<span data-ttu-id="a27c2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a27c2-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a27c2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a27c2-112">Area:</span></span>  <br/> |<span data-ttu-id="a27c2-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="a27c2-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a27c2-114">备注</span><span class="sxs-lookup"><span data-stu-id="a27c2-114">Remarks</span></span>

<span data-ttu-id="a27c2-115">此属性在消息对象上通过 MAPI 计算。</span><span class="sxs-lookup"><span data-stu-id="a27c2-115">This property is computed by MAPI on message objects.</span></span>
  
<span data-ttu-id="a27c2-116">此属性仅入站邮件上的显示，并保留其他所有情况下。</span><span class="sxs-lookup"><span data-stu-id="a27c2-116">This property appears on inbound messages only and is reserved in all other cases.</span></span> <span data-ttu-id="a27c2-117">表示一条消息，指示已传递给其最终位置或是否消息挂接提供程序可能已删除邮件重新路由它时。</span><span class="sxs-lookup"><span data-stu-id="a27c2-117">It indicates whether or not a message has been delivered to its final location or whether a messaging hook provider potentially deleted the message while rerouting it.</span></span>
  
<span data-ttu-id="a27c2-118">客户端应用程序应永远不会将该属性。</span><span class="sxs-lookup"><span data-stu-id="a27c2-118">Client applications should never set this property.</span></span> <span data-ttu-id="a27c2-119">入站邮件，客户端或服务提供程序可以调用此属性可以确定邮件状态[IMAPIProp::GetProps](imapiprop-getprops.md) 。</span><span class="sxs-lookup"><span data-stu-id="a27c2-119">For an inbound message, a client or service provider can call [IMAPIProp::GetProps](imapiprop-getprops.md) on this property to determine the message status.</span></span> <span data-ttu-id="a27c2-120">值 S_OK 指示邮件已成功递送到消息存储库。</span><span class="sxs-lookup"><span data-stu-id="a27c2-120">The value S_OK indicates that the message was successfully delivered to the message store.</span></span> <span data-ttu-id="a27c2-121">值 MAPI_E_OBJECT_DELETED 指示邮件已被删除，永远不会被提交到存储区。</span><span class="sxs-lookup"><span data-stu-id="a27c2-121">The value MAPI_E_OBJECT_DELETED indicates that the message was deleted and was never committed to the store.</span></span> 
  
<span data-ttu-id="a27c2-122">消息存储提供程序应在邮件、 收件人表和传出队列表支持此属性。</span><span class="sxs-lookup"><span data-stu-id="a27c2-122">Message store providers should support this property on messages, recipient tables, and the outgoing queue table.</span></span> <span data-ttu-id="a27c2-123">客户端和提供程序应能够在传出队列表上设置列方法和 restrict 基于此属性。</span><span class="sxs-lookup"><span data-stu-id="a27c2-123">Clients and providers should be able to set columns on the outgoing queue table and restrict based on this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a27c2-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="a27c2-124">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="a27c2-125">头文件</span><span class="sxs-lookup"><span data-stu-id="a27c2-125">Header files</span></span>

<span data-ttu-id="a27c2-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a27c2-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="a27c2-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a27c2-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="a27c2-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a27c2-128">Mapitags.h</span></span>
  
> <span data-ttu-id="a27c2-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a27c2-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a27c2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a27c2-130">See also</span></span>



[<span data-ttu-id="a27c2-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a27c2-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a27c2-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a27c2-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a27c2-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a27c2-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a27c2-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a27c2-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

