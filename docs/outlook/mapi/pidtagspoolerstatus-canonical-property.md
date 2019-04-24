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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 426d26cae147faf3f843ac547de9d205d766ac44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348207"
---
# <a name="pidtagspoolerstatus-canonical-property"></a><span data-ttu-id="ddbb3-103">PidTagSpoolerStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="ddbb3-103">PidTagSpoolerStatus Canonical Property</span></span>

  
  
<span data-ttu-id="ddbb3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ddbb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ddbb3-105">包含邮件的状态, 该邮件基于可用于 MAPI 后台处理程序的信息。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-105">Contains the status of the message based on information that is available to the MAPI spooler.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ddbb3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ddbb3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ddbb3-107">PR_SPOOLER_STATUS</span><span class="sxs-lookup"><span data-stu-id="ddbb3-107">PR_SPOOLER_STATUS</span></span>  <br/> |
|<span data-ttu-id="ddbb3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ddbb3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ddbb3-109">0x0E10</span><span class="sxs-lookup"><span data-stu-id="ddbb3-109">0x0E10</span></span>  <br/> |
|<span data-ttu-id="ddbb3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ddbb3-110">Data type:</span></span>  <br/> |<span data-ttu-id="ddbb3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ddbb3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ddbb3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ddbb3-112">Area:</span></span>  <br/> |<span data-ttu-id="ddbb3-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="ddbb3-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ddbb3-114">注解</span><span class="sxs-lookup"><span data-stu-id="ddbb3-114">Remarks</span></span>

<span data-ttu-id="ddbb3-115">此属性由 MAPI 对邮件对象计算。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-115">This property is computed by MAPI on message objects.</span></span>
  
<span data-ttu-id="ddbb3-116">此属性仅在入站邮件中显示, 并在所有其他情况下保留。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-116">This property appears on inbound messages only and is reserved in all other cases.</span></span> <span data-ttu-id="ddbb3-117">它指示是否已将邮件传递到其最终位置, 或者消息传递挂钩提供程序在重新路由邮件时是否可能删除邮件。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-117">It indicates whether or not a message has been delivered to its final location or whether a messaging hook provider potentially deleted the message while rerouting it.</span></span>
  
<span data-ttu-id="ddbb3-118">客户端应用程序永远不应设置此属性。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-118">Client applications should never set this property.</span></span> <span data-ttu-id="ddbb3-119">对于入站邮件, 客户端或服务提供商可以对此属性调用[IMAPIProp:: GetProps](imapiprop-getprops.md)以确定邮件状态。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-119">For an inbound message, a client or service provider can call [IMAPIProp::GetProps](imapiprop-getprops.md) on this property to determine the message status.</span></span> <span data-ttu-id="ddbb3-120">值 S_OK 指示邮件已成功传递到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-120">The value S_OK indicates that the message was successfully delivered to the message store.</span></span> <span data-ttu-id="ddbb3-121">值 MAPI_E_OBJECT_DELETED 指示邮件已被删除且从未提交到存储区。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-121">The value MAPI_E_OBJECT_DELETED indicates that the message was deleted and was never committed to the store.</span></span> 
  
<span data-ttu-id="ddbb3-122">邮件存储提供程序应支持邮件、收件人表和传出队列表上的此属性。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-122">Message store providers should support this property on messages, recipient tables, and the outgoing queue table.</span></span> <span data-ttu-id="ddbb3-123">客户端和提供程序应能够对传出队列表设置列, 并根据此属性进行限制。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-123">Clients and providers should be able to set columns on the outgoing queue table and restrict based on this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ddbb3-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="ddbb3-124">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ddbb3-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ddbb3-125">Header files</span></span>

<span data-ttu-id="ddbb3-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ddbb3-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ddbb3-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="ddbb3-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ddbb3-128">Mapitags.h</span></span>
  
> <span data-ttu-id="ddbb3-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ddbb3-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ddbb3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddbb3-130">See also</span></span>



[<span data-ttu-id="ddbb3-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ddbb3-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ddbb3-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ddbb3-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ddbb3-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ddbb3-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ddbb3-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ddbb3-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

