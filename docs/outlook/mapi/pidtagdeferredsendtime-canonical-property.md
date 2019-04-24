---
title: PidTagDeferredSendTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendTime
api_type:
- HeaderDef
ms.assetid: ee206c2d-8371-4d19-b42b-78f6479e13ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d6374c2fd3c277e2bb976930e9e105cc839b1e8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359876"
---
# <a name="pidtagdeferredsendtime-canonical-property"></a><span data-ttu-id="0b752-103">PidTagDeferredSendTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b752-103">PidTagDeferredSendTime Canonical Property</span></span>

  
  
<span data-ttu-id="0b752-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b752-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b752-105">指示客户端希望延迟发送邮件的时间。</span><span class="sxs-lookup"><span data-stu-id="0b752-105">Indicates a time when a client would like to defer sending a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0b752-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b752-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b752-107">PR_DEFERRED_SEND_TIME</span><span class="sxs-lookup"><span data-stu-id="0b752-107">PR_DEFERRED_SEND_TIME</span></span>  <br/> |
|<span data-ttu-id="0b752-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0b752-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0b752-109">0x3FEF</span><span class="sxs-lookup"><span data-stu-id="0b752-109">0x3FEF</span></span>  <br/> |
|<span data-ttu-id="0b752-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b752-110">Data type:</span></span>  <br/> |<span data-ttu-id="0b752-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="0b752-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="0b752-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0b752-112">Area:</span></span>  <br/> |<span data-ttu-id="0b752-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="0b752-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b752-114">注解</span><span class="sxs-lookup"><span data-stu-id="0b752-114">Remarks</span></span>

<span data-ttu-id="0b752-115">如果**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 和**PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 属性存在, 则使用下面的公式重新计算此属性的值, 并旧值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="0b752-115">If the **PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) and **PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) properties are present, the value of this property is recomputed by using the following formula and the old value is ignored.</span></span>
  
 <span data-ttu-id="0b752-116">**PR_DEFERRED_SEND_TIME** = **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* TimeOf (**PR_DEFERRED_SEND_UNITS**)</span><span class="sxs-lookup"><span data-stu-id="0b752-116">**PR_DEFERRED_SEND_TIME** = **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* TimeOf(**PR_DEFERRED_SEND_UNITS**)</span></span>
  
<span data-ttu-id="0b752-117">如果**PR_DEFERRED_SEND_TIME**值早于当前时间 (以 UTC 为单位), 则会立即发送邮件。</span><span class="sxs-lookup"><span data-stu-id="0b752-117">If **PR_DEFERRED_SEND_TIME** value is earlier than the current time (in UTC), the message is sent immediately.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b752-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b752-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0b752-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="0b752-119">Protocol specifications</span></span>

<span data-ttu-id="0b752-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b752-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b752-121">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0b752-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0b752-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0b752-122">Header files</span></span>

<span data-ttu-id="0b752-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0b752-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b752-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b752-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="0b752-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0b752-125">Mapitags.h</span></span>
  
> <span data-ttu-id="0b752-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0b752-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b752-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b752-127">See also</span></span>



[<span data-ttu-id="0b752-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b752-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b752-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b752-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b752-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b752-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b752-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b752-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

