---
title: PidTagNonReceiptNotificationRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNonReceiptNotificationRequested
api_type:
- HeaderDef
ms.assetid: 747f7ba8-42d3-4be3-9908-269e9a347c7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 896cfa2bf8a1b33fd6dee09649853b71618f31be
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582782"
---
# <a name="pidtagnonreceiptnotificationrequested-canonical-property"></a><span data-ttu-id="01c31-103">PidTagNonReceiptNotificationRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="01c31-103">PidTagNonReceiptNotificationRequested Canonical Property</span></span>

  
  
<span data-ttu-id="01c31-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="01c31-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="01c31-105">如果邮件发件人的指定收件人的非回执通知，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="01c31-105">Contains TRUE if a message sender wants notification of non-receipt for a specified recipient.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="01c31-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="01c31-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="01c31-107">PR_NON_RECEIPT_NOTIFICATION_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="01c31-107">PR_NON_RECEIPT_NOTIFICATION_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="01c31-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="01c31-108">Identifier:</span></span>  <br/> |<span data-ttu-id="01c31-109">0x0C06</span><span class="sxs-lookup"><span data-stu-id="01c31-109">0x0C06</span></span>  <br/> |
|<span data-ttu-id="01c31-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="01c31-110">Data type:</span></span>  <br/> |<span data-ttu-id="01c31-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="01c31-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="01c31-112">区域：</span><span class="sxs-lookup"><span data-stu-id="01c31-112">Area:</span></span>  <br/> |<span data-ttu-id="01c31-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="01c31-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="01c31-114">注解</span><span class="sxs-lookup"><span data-stu-id="01c31-114">Remarks</span></span>

<span data-ttu-id="01c31-115">此属性包含 FALSE 并且**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性包含 TRUE，如果服务提供商可以重写**PR_NON_RECEIPT_NOTIFICATION_REQUESTED**属性，并生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="01c31-115">If this property contains FALSE and the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property contains TRUE, the service provider can override the **PR_NON_RECEIPT_NOTIFICATION_REQUESTED** property and generate a non-delivery report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="01c31-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="01c31-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="01c31-117">头文件</span><span class="sxs-lookup"><span data-stu-id="01c31-117">Header files</span></span>

<span data-ttu-id="01c31-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="01c31-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="01c31-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="01c31-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="01c31-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="01c31-120">Mapitags.h</span></span>
  
> <span data-ttu-id="01c31-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="01c31-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="01c31-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01c31-122">See also</span></span>



[<span data-ttu-id="01c31-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="01c31-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="01c31-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="01c31-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="01c31-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="01c31-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="01c31-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="01c31-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

