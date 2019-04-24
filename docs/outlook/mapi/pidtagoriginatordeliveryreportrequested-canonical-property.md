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
ms.openlocfilehash: a92ee13e571032c050f69677d9daba8dad7aea3c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356299"
---
# <a name="pidtagoriginatordeliveryreportrequested-canonical-property"></a><span data-ttu-id="3cc4f-103">PidTagOriginatorDeliveryReportRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cc4f-103">PidTagOriginatorDeliveryReportRequested Canonical Property</span></span>

  
  
<span data-ttu-id="3cc4f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3cc4f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3cc4f-105">如果邮件发件人在将邮件放入邮件存储区之前从邮件系统中请求某个收件人的送达报告, 则该属性值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-105">Contains TRUE if a message sender requests a delivery report for a particular recipient from the messaging system before the message is placed in the message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cc4f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3cc4f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3cc4f-107">PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="3cc4f-107">PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="3cc4f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3cc4f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3cc4f-109">0x0023</span><span class="sxs-lookup"><span data-stu-id="3cc4f-109">0x0023</span></span>  <br/> |
|<span data-ttu-id="3cc4f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3cc4f-110">Data type:</span></span>  <br/> |<span data-ttu-id="3cc4f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="3cc4f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="3cc4f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3cc4f-112">Area:</span></span>  <br/> |<span data-ttu-id="3cc4f-113">MIME</span><span class="sxs-lookup"><span data-stu-id="3cc4f-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cc4f-114">注解</span><span class="sxs-lookup"><span data-stu-id="3cc4f-114">Remarks</span></span>

<span data-ttu-id="3cc4f-115">此属性用于指示邮件系统处理已传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-115">This property is used to direct the messaging system in handling delivered messages.</span></span> <span data-ttu-id="3cc4f-116">在这种情况下, 邮件还必须将**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-116">In this case, the message must also furnish the **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) property set to FALSE.</span></span>
  
<span data-ttu-id="3cc4f-117">设置邮件的**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED**属性是为所有收件人请求传递状态报告的一种方式。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-117">Setting the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** property on a message is a way to request delivery status reports for all recipients.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3cc4f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3cc4f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3cc4f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="3cc4f-119">Protocol specifications</span></span>

<span data-ttu-id="3cc4f-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cc4f-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cc4f-121">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3cc4f-122">头文件</span><span class="sxs-lookup"><span data-stu-id="3cc4f-122">Header files</span></span>

<span data-ttu-id="3cc4f-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3cc4f-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="3cc4f-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="3cc4f-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="3cc4f-125">Mapitags.h</span></span>
  
> <span data-ttu-id="3cc4f-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3cc4f-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3cc4f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc4f-127">See also</span></span>



[<span data-ttu-id="3cc4f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3cc4f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3cc4f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cc4f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3cc4f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3cc4f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3cc4f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cc4f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

