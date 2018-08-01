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
ms.openlocfilehash: 3912c429f1aa932b4956d943579a4ed99634dca2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777526"
---
# <a name="pidtagdeferredsendtime-canonical-property"></a><span data-ttu-id="977e1-103">PidTagDeferredSendTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="977e1-103">PidTagDeferredSendTime Canonical Property</span></span>

  
  
<span data-ttu-id="977e1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="977e1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="977e1-105">指示当客户端希望推迟发送一条消息的时间。</span><span class="sxs-lookup"><span data-stu-id="977e1-105">Indicates a time when a client would like to defer sending a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="977e1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="977e1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="977e1-107">PR_DEFERRED_SEND_TIME</span><span class="sxs-lookup"><span data-stu-id="977e1-107">PR_DEFERRED_SEND_TIME</span></span>  <br/> |
|<span data-ttu-id="977e1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="977e1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="977e1-109">0x3FEF</span><span class="sxs-lookup"><span data-stu-id="977e1-109">0x3FEF</span></span>  <br/> |
|<span data-ttu-id="977e1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="977e1-110">Data type:</span></span>  <br/> |<span data-ttu-id="977e1-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="977e1-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="977e1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="977e1-112">Area:</span></span>  <br/> |<span data-ttu-id="977e1-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="977e1-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="977e1-114">说明</span><span class="sxs-lookup"><span data-stu-id="977e1-114">Remarks</span></span>

<span data-ttu-id="977e1-115">如果存在**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 和**PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 属性，此属性的值通过使用以下公式重新计算和旧值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="977e1-115">If the **PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) and **PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) properties are present, the value of this property is recomputed by using the following formula and the old value is ignored.</span></span>
  
 <span data-ttu-id="977e1-116">**PR_DEFERRED_SEND_TIME** = **期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* 时间 (**PR_DEFERRED_SEND_UNITS**)</span><span class="sxs-lookup"><span data-stu-id="977e1-116">**PR_DEFERRED_SEND_TIME** = **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) + **PR_DEFERRED_SEND_NUMBER** \* TimeOf(**PR_DEFERRED_SEND_UNITS**)</span></span>
  
<span data-ttu-id="977e1-117">如果**PR_DEFERRED_SEND_TIME**值为早于当前时间 （采用 UTC)，立即发送邮件。</span><span class="sxs-lookup"><span data-stu-id="977e1-117">If **PR_DEFERRED_SEND_TIME** value is earlier than the current time (in UTC), the message is sent immediately.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="977e1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="977e1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="977e1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="977e1-119">Protocol specifications</span></span>

<span data-ttu-id="977e1-120">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="977e1-120">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="977e1-121">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="977e1-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="977e1-122">头文件</span><span class="sxs-lookup"><span data-stu-id="977e1-122">Header files</span></span>

<span data-ttu-id="977e1-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="977e1-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="977e1-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="977e1-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="977e1-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="977e1-125">Mapitags.h</span></span>
  
> <span data-ttu-id="977e1-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="977e1-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="977e1-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="977e1-127">See also</span></span>



[<span data-ttu-id="977e1-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="977e1-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="977e1-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="977e1-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="977e1-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="977e1-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="977e1-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="977e1-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

