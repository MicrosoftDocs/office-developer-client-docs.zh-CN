---
title: PidTagLatestDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLatestDeliveryTime
api_type:
- HeaderDef
ms.assetid: 6c2e64bc-786e-4867-a504-46f4d1214337
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cf25dc5a1182d019ea183f2c0714925f220aeb8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777802"
---
# <a name="pidtaglatestdeliverytime-canonical-property"></a><span data-ttu-id="d04e7-103">PidTagLatestDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="d04e7-103">PidTagLatestDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="d04e7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d04e7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d04e7-105">包含的最新的日期和时间时邮件传输代理 (MTA) 应将邮件传递。</span><span class="sxs-lookup"><span data-stu-id="d04e7-105">Contains the latest date and time when a message transfer agent (MTA) should deliver a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d04e7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d04e7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d04e7-107">PR_LATEST_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="d04e7-107">PR_LATEST_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="d04e7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d04e7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d04e7-109">0x0019</span><span class="sxs-lookup"><span data-stu-id="d04e7-109">0x0019</span></span>  <br/> |
|<span data-ttu-id="d04e7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d04e7-110">Data type:</span></span>  <br/> |<span data-ttu-id="d04e7-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d04e7-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="d04e7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d04e7-112">Area:</span></span>  <br/> |<span data-ttu-id="d04e7-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="d04e7-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d04e7-114">说明</span><span class="sxs-lookup"><span data-stu-id="d04e7-114">Remarks</span></span>

<span data-ttu-id="d04e7-115">如果按此属性指定的时间，MTA 无法传送一条消息，它会取消没有传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="d04e7-115">If an MTA cannot deliver a message by the time this property specifies, it cancels the message without delivery.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d04e7-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="d04e7-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d04e7-117">头文件</span><span class="sxs-lookup"><span data-stu-id="d04e7-117">Header files</span></span>

<span data-ttu-id="d04e7-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d04e7-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="d04e7-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d04e7-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="d04e7-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d04e7-120">Mapitags.h</span></span>
  
> <span data-ttu-id="d04e7-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d04e7-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d04e7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d04e7-122">See also</span></span>



[<span data-ttu-id="d04e7-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d04e7-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d04e7-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d04e7-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d04e7-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d04e7-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d04e7-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d04e7-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

