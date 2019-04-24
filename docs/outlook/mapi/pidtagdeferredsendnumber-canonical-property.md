---
title: PidTagDeferredSendNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendNumber
api_type:
- HeaderDef
ms.assetid: 8ada5c9b-bec5-42d8-bc58-f0411ec4e88b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e3a30dad433b255573e4e3f041e6475b9227a54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357734"
---
# <a name="pidtagdeferredsendnumber-canonical-property"></a><span data-ttu-id="569ee-103">PidTagDeferredSendNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="569ee-103">PidTagDeferredSendNumber Canonical Property</span></span>

  
  
<span data-ttu-id="569ee-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="569ee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="569ee-105">包含可用于计算发送邮件的延期的号码。</span><span class="sxs-lookup"><span data-stu-id="569ee-105">Contains a number that can be used to compute the deferment of sending a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="569ee-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="569ee-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="569ee-107">PR_DEFERRED_SEND_NUMBER</span><span class="sxs-lookup"><span data-stu-id="569ee-107">PR_DEFERRED_SEND_NUMBER</span></span>  <br/> |
|<span data-ttu-id="569ee-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="569ee-108">Identifier:</span></span>  <br/> |<span data-ttu-id="569ee-109">0x3FEB</span><span class="sxs-lookup"><span data-stu-id="569ee-109">0x3FEB</span></span>  <br/> |
|<span data-ttu-id="569ee-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="569ee-110">Data type:</span></span>  <br/> |<span data-ttu-id="569ee-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="569ee-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="569ee-112">区域：</span><span class="sxs-lookup"><span data-stu-id="569ee-112">Area:</span></span>  <br/> |<span data-ttu-id="569ee-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="569ee-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="569ee-114">注解</span><span class="sxs-lookup"><span data-stu-id="569ee-114">Remarks</span></span>

<span data-ttu-id="569ee-115">此属性用于在**PR_DEFERRED_SEND_TIME** ([PidTagDeferredSendTime](pidtagdeferredsendtime-canonical-property.md)) 属性不存在时对其进行计算。</span><span class="sxs-lookup"><span data-stu-id="569ee-115">This property is used for computing the **PR_DEFERRED_SEND_TIME** ([PidTagDeferredSendTime](pidtagdeferredsendtime-canonical-property.md)) property when it is not present.</span></span> <span data-ttu-id="569ee-116">当延迟发送邮件时, 如果**PR_DEFERRED_SEND_TIME**属性不存在, 则**PR_DEFERRED_SEND_NUMBER**属性应与**PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) 属性一起设置。</span><span class="sxs-lookup"><span data-stu-id="569ee-116">When sending a message is deferred, the **PR_DEFERRED_SEND_NUMBER** property should be set along with the **PR_DEFERRED_SEND_UNITS** ([PidTagDeferredSendUnits](pidtagdeferredsendunits-canonical-property.md)) property, if the **PR_DEFERRED_SEND_TIME** property is absent.</span></span> 
  
<span data-ttu-id="569ee-117">必须在0和999之间设置**PR_DEFERRED_SEND_NUMBER**值。</span><span class="sxs-lookup"><span data-stu-id="569ee-117">The **PR_DEFERRED_SEND_NUMBER** value must be set between 0 and 999.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="569ee-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="569ee-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="569ee-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="569ee-119">Protocol specifications</span></span>

<span data-ttu-id="569ee-120">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="569ee-120">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="569ee-121">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="569ee-121">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="569ee-122">头文件</span><span class="sxs-lookup"><span data-stu-id="569ee-122">Header files</span></span>

<span data-ttu-id="569ee-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="569ee-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="569ee-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="569ee-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="569ee-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="569ee-125">Mapitags.h</span></span>
  
> <span data-ttu-id="569ee-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="569ee-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="569ee-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="569ee-127">See also</span></span>



[<span data-ttu-id="569ee-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="569ee-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="569ee-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="569ee-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="569ee-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="569ee-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="569ee-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="569ee-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

