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
ms.openlocfilehash: 3640ec4471b72dea81d56cc2c462ef145095480f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590923"
---
# <a name="pidtaglatestdeliverytime-canonical-property"></a><span data-ttu-id="72ff7-103">PidTagLatestDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="72ff7-103">PidTagLatestDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="72ff7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="72ff7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="72ff7-105">包含的最新的日期和时间时邮件传输代理 (MTA) 应将邮件传递。</span><span class="sxs-lookup"><span data-stu-id="72ff7-105">Contains the latest date and time when a message transfer agent (MTA) should deliver a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="72ff7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="72ff7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="72ff7-107">PR_LATEST_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="72ff7-107">PR_LATEST_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="72ff7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="72ff7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="72ff7-109">0x0019</span><span class="sxs-lookup"><span data-stu-id="72ff7-109">0x0019</span></span>  <br/> |
|<span data-ttu-id="72ff7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="72ff7-110">Data type:</span></span>  <br/> |<span data-ttu-id="72ff7-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="72ff7-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="72ff7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="72ff7-112">Area:</span></span>  <br/> |<span data-ttu-id="72ff7-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="72ff7-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="72ff7-114">注解</span><span class="sxs-lookup"><span data-stu-id="72ff7-114">Remarks</span></span>

<span data-ttu-id="72ff7-115">如果按此属性指定的时间，MTA 无法传送一条消息，它会取消没有传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="72ff7-115">If an MTA cannot deliver a message by the time this property specifies, it cancels the message without delivery.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="72ff7-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="72ff7-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="72ff7-117">头文件</span><span class="sxs-lookup"><span data-stu-id="72ff7-117">Header files</span></span>

<span data-ttu-id="72ff7-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="72ff7-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="72ff7-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="72ff7-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="72ff7-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="72ff7-120">Mapitags.h</span></span>
  
> <span data-ttu-id="72ff7-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="72ff7-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="72ff7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72ff7-122">See also</span></span>



[<span data-ttu-id="72ff7-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="72ff7-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="72ff7-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="72ff7-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="72ff7-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="72ff7-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="72ff7-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="72ff7-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

