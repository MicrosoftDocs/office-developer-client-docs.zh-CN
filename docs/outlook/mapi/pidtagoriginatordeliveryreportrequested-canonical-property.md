---
title: PidTagOriginatorDeliveryReportRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginatorDeliveryReportRequested
api_type:
- COM
ms.assetid: 4461b35d-e2b9-41ff-b079-31bfef02e2bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e508f9c3d84272a0641a27e18c94e0620a7072c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574403"
---
# <a name="pidtagoriginatordeliveryreportrequested-canonical-property"></a><span data-ttu-id="42fe8-103">PidTagOriginatorDeliveryReportRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="42fe8-103">PidTagOriginatorDeliveryReportRequested Canonical Property</span></span>

  
  
<span data-ttu-id="42fe8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="42fe8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="42fe8-105">如果邮件发件人请求特定收件人从邮件系统的送达报告之前消息置于消息存储库中，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="42fe8-105">Contains TRUE if a message sender requests a delivery report for a particular recipient from the messaging system before the message is placed in the message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="42fe8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="42fe8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="42fe8-107">邮件已被阅读</span><span class="sxs-lookup"><span data-stu-id="42fe8-107">PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="42fe8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="42fe8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="42fe8-109">0x0023</span><span class="sxs-lookup"><span data-stu-id="42fe8-109">0x0023</span></span>  <br/> |
|<span data-ttu-id="42fe8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="42fe8-110">Data type:</span></span>  <br/> |<span data-ttu-id="42fe8-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="42fe8-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="42fe8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="42fe8-112">Area:</span></span>  <br/> |<span data-ttu-id="42fe8-113">MIME</span><span class="sxs-lookup"><span data-stu-id="42fe8-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="42fe8-114">注解</span><span class="sxs-lookup"><span data-stu-id="42fe8-114">Remarks</span></span>

<span data-ttu-id="42fe8-115">此属性用于直接在邮件系统中处理已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="42fe8-115">This property is used to direct the messaging system in handling delivered messages.</span></span> <span data-ttu-id="42fe8-116">在这种情况下，邮件还必须提供**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="42fe8-116">In this case, the message must also furnish the **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) property set to FALSE.</span></span>
  
<span data-ttu-id="42fe8-117">上一条消息设置的**邮件已被阅读**属性是一种方法传递状态报告请求的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="42fe8-117">Setting the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** property on a message is a way to request delivery status reports for all recipients.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="42fe8-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="42fe8-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="42fe8-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="42fe8-119">Protocol specifications</span></span>

<span data-ttu-id="42fe8-120">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="42fe8-120">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="42fe8-121">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="42fe8-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="42fe8-122">头文件</span><span class="sxs-lookup"><span data-stu-id="42fe8-122">Header files</span></span>

<span data-ttu-id="42fe8-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="42fe8-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="42fe8-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="42fe8-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="42fe8-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="42fe8-125">Mapitags.h</span></span>
  
> <span data-ttu-id="42fe8-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="42fe8-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="42fe8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42fe8-127">See also</span></span>



[<span data-ttu-id="42fe8-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="42fe8-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="42fe8-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="42fe8-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="42fe8-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="42fe8-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="42fe8-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="42fe8-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

