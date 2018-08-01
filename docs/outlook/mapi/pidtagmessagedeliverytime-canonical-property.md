---
title: PidTagMessageDeliveryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageDeliveryTime
api_type:
- HeaderDef
ms.assetid: 4f9d44f2-4faa-4f16-9e33-22f80c17db85
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4fd74e99a8073db03ad47292677ff98efca58af3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777844"
---
# <a name="pidtagmessagedeliverytime-canonical-property"></a><span data-ttu-id="f022c-103">PidTagMessageDeliveryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="f022c-103">PidTagMessageDeliveryTime Canonical Property</span></span>

  
  
<span data-ttu-id="f022c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f022c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f022c-105">包含的日期和时间时邮件已送达。</span><span class="sxs-lookup"><span data-stu-id="f022c-105">Contains the date and time when a message was delivered.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f022c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f022c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f022c-107">PR_MESSAGE_DELIVERY_TIME</span><span class="sxs-lookup"><span data-stu-id="f022c-107">PR_MESSAGE_DELIVERY_TIME</span></span>  <br/> |
|<span data-ttu-id="f022c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f022c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f022c-109">0x0E06</span><span class="sxs-lookup"><span data-stu-id="f022c-109">0x0E06</span></span>  <br/> |
|<span data-ttu-id="f022c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f022c-110">Data type:</span></span>  <br/> |<span data-ttu-id="f022c-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="f022c-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="f022c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f022c-112">Area:</span></span>  <br/> |<span data-ttu-id="f022c-113">消息时间</span><span class="sxs-lookup"><span data-stu-id="f022c-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f022c-114">说明</span><span class="sxs-lookup"><span data-stu-id="f022c-114">Remarks</span></span>

<span data-ttu-id="f022c-115">此属性描述了消息存储在服务器上的时间，而不是时传输提供程序将邮件从服务器复制到本地存储的下载时间。</span><span class="sxs-lookup"><span data-stu-id="f022c-115">This property describes the time the message was stored at the server, rather than the download time when the transport provider copied the message from the server to the local store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f022c-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="f022c-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f022c-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="f022c-117">Protocol specifications</span></span>

<span data-ttu-id="f022c-118">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f022c-118">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f022c-119">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="f022c-119">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f022c-120">头文件</span><span class="sxs-lookup"><span data-stu-id="f022c-120">Header files</span></span>

<span data-ttu-id="f022c-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f022c-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="f022c-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f022c-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="f022c-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f022c-123">Mapitags.h</span></span>
  
> <span data-ttu-id="f022c-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f022c-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f022c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f022c-125">See also</span></span>



[<span data-ttu-id="f022c-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f022c-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f022c-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f022c-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f022c-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f022c-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f022c-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f022c-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

