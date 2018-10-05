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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397203"
---
# <a name="pidtagdeferredsendtime-canonical-property"></a><span data-ttu-id="24d32-103">PidTagDeferredSendTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="24d32-103">PidTagDeferredSendTime Canonical Property</span></span>

  
  
<span data-ttu-id="24d32-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24d32-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24d32-105">指示当客户端希望推迟发送一条消息的时间。</span><span class="sxs-lookup"><span data-stu-id="24d32-105">Indicates a time when a client would like to defer sending a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24d32-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24d32-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24d32-107">PR_DEFERRED_SEND_TIME</span><span class="sxs-lookup"><span data-stu-id="24d32-107">PR_DEFERRED_SEND_TIME</span></span>  <br/> |
|<span data-ttu-id="24d32-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="24d32-108">Identifier:</span></span>  <br/> |<span data-ttu-id="24d32-109">0x3FEF</span><span class="sxs-lookup"><span data-stu-id="24d32-109">0x3FEF</span></span>  <br/> |
|<span data-ttu-id="24d32-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24d32-110">Data type:</span></span>  <br/> |<span data-ttu-id="24d32-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="24d32-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="24d32-112">区域：</span><span class="sxs-lookup"><span data-stu-id="24d32-112">Area:</span></span>  <br/> |<span data-ttu-id="24d32-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="24d32-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24d32-114">说明</span><span class="sxs-lookup"><span data-stu-id="24d32-114">Remarks</span></span>

<span data-ttu-id="24d32-115">如果存在**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 和**PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 属性，此属性的值通过使用以下公式重新计算和旧值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="24d32-115">If the **PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) and **PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) properties are present, the value of this property is recomputed by using the following formula and the old value is ignored.</span></span>
  
 <span data-ttu-id="24d32-116">**PR_DEFERRED_SEND_TIME** = **期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* 时间 (**PR_DEFERRED_SEND_UNITS**)</span><span class="sxs-lookup"><span data-stu-id="24d32-116">**PR_DEFERRED_SEND_TIME** = **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* TimeOf(**PR_DEFERRED_SEND_UNITS**)</span></span>
  
<span data-ttu-id="24d32-117">如果**PR_DEFERRED_SEND_TIME**值为早于当前时间 （采用 UTC)，立即发送邮件。</span><span class="sxs-lookup"><span data-stu-id="24d32-117">If **PR_DEFERRED_SEND_TIME** value is earlier than the current time (in UTC), the message is sent immediately.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="24d32-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="24d32-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24d32-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="24d32-119">Protocol specifications</span></span>

<span data-ttu-id="24d32-120">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24d32-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24d32-121">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="24d32-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24d32-122">头文件</span><span class="sxs-lookup"><span data-stu-id="24d32-122">Header files</span></span>

<span data-ttu-id="24d32-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="24d32-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="24d32-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24d32-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="24d32-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="24d32-125">Mapitags.h</span></span>
  
> <span data-ttu-id="24d32-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="24d32-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24d32-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24d32-127">See also</span></span>



[<span data-ttu-id="24d32-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24d32-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24d32-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24d32-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24d32-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24d32-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24d32-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24d32-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

