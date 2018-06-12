---
title: PidTagOriginalDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDeliveryTime
api_type:
- COM
ms.assetid: 700ccfc9-493a-483b-aca0-aa2d7f6bb229
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cd8c44923e64fcea4464f758389db05bb6b7e374
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777922"
---
# <a name="pidtagoriginaldeliverytime-canonical-property"></a><span data-ttu-id="cffd5-103">PidTagOriginalDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="cffd5-103">PidTagOriginalDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="cffd5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cffd5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cffd5-105">包含一份原始邮件的传递日期和时间线程中的项目。</span><span class="sxs-lookup"><span data-stu-id="cffd5-105">Contains a copy of the original message's delivery date and time in a thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cffd5-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="cffd5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cffd5-107">PR_ORIGINAL_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="cffd5-107">PR_ORIGINAL_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="cffd5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="cffd5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cffd5-109">0x0055</span><span class="sxs-lookup"><span data-stu-id="cffd5-109">0x0055</span></span>  <br/> |
|<span data-ttu-id="cffd5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cffd5-110">Data type:</span></span>  <br/> |<span data-ttu-id="cffd5-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="cffd5-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="cffd5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cffd5-112">Area:</span></span>  <br/> |<span data-ttu-id="cffd5-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="cffd5-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cffd5-114">备注</span><span class="sxs-lookup"><span data-stu-id="cffd5-114">Remarks</span></span>

<span data-ttu-id="cffd5-115">此属性是从后续答复或正向操作中的原始**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性复制，读取和 nonread 报表中使用。</span><span class="sxs-lookup"><span data-stu-id="cffd5-115">This property is copied from the original **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) property in subsequent reply or forward operations and used in read and nonread reports.</span></span> <span data-ttu-id="cffd5-116">送达报告改用**PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="cffd5-116">Delivery reports use the **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) property instead.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cffd5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="cffd5-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cffd5-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="cffd5-118">Protocol specifications</span></span>

<span data-ttu-id="cffd5-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cffd5-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cffd5-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="cffd5-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cffd5-121">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cffd5-121">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cffd5-122">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="cffd5-122">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cffd5-123">头文件</span><span class="sxs-lookup"><span data-stu-id="cffd5-123">Header files</span></span>

<span data-ttu-id="cffd5-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cffd5-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="cffd5-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cffd5-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="cffd5-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cffd5-126">Mapitags.h</span></span>
  
> <span data-ttu-id="cffd5-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cffd5-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cffd5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cffd5-128">See also</span></span>



[<span data-ttu-id="cffd5-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cffd5-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cffd5-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cffd5-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cffd5-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cffd5-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cffd5-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cffd5-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

