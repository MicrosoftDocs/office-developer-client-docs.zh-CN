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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bbe277092b450a4254e02d00d2cf54e35ec6be44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355655"
---
# <a name="pidtagoriginaldeliverytime-canonical-property"></a><span data-ttu-id="70ec9-103">PidTagOriginalDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="70ec9-103">PidTagOriginalDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="70ec9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70ec9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70ec9-105">包含原始邮件在线程中的传递日期和时间的副本。</span><span class="sxs-lookup"><span data-stu-id="70ec9-105">Contains a copy of the original message's delivery date and time in a thread.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="70ec9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="70ec9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="70ec9-107">PR_ORIGINAL_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="70ec9-107">PR_ORIGINAL_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="70ec9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="70ec9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="70ec9-109">0x0055</span><span class="sxs-lookup"><span data-stu-id="70ec9-109">0x0055</span></span>  <br/> |
|<span data-ttu-id="70ec9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="70ec9-110">Data type:</span></span>  <br/> |<span data-ttu-id="70ec9-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="70ec9-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="70ec9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="70ec9-112">Area:</span></span>  <br/> |<span data-ttu-id="70ec9-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="70ec9-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="70ec9-114">备注</span><span class="sxs-lookup"><span data-stu-id="70ec9-114">Remarks</span></span>

<span data-ttu-id="70ec9-115">此属性从原始 PR_MESSAGE_DELIVERY_TIME ( [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性复制到后续答复或转发操作中，并用于读取和非读取报告。</span><span class="sxs-lookup"><span data-stu-id="70ec9-115">This property is copied from the original **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) property in subsequent reply or forward operations and used in read and nonread reports.</span></span> <span data-ttu-id="70ec9-116">送达报告使用 **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="70ec9-116">Delivery reports use the **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md)) property instead.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="70ec9-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="70ec9-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="70ec9-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="70ec9-118">Protocol specifications</span></span>

<span data-ttu-id="70ec9-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70ec9-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70ec9-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="70ec9-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="70ec9-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70ec9-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70ec9-122">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="70ec9-122">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="70ec9-123">头文件</span><span class="sxs-lookup"><span data-stu-id="70ec9-123">Header files</span></span>

<span data-ttu-id="70ec9-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="70ec9-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="70ec9-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="70ec9-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="70ec9-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="70ec9-126">Mapitags.h</span></span>
  
> <span data-ttu-id="70ec9-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="70ec9-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="70ec9-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70ec9-128">See also</span></span>



[<span data-ttu-id="70ec9-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="70ec9-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="70ec9-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="70ec9-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="70ec9-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="70ec9-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="70ec9-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="70ec9-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

