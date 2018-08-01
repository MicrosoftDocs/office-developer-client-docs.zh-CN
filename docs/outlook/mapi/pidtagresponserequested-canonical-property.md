---
title: PidTagResponseRequested 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResponseRequested
api_type:
- COM
ms.assetid: e52bb48c-7107-4ac4-b030-885409759ee7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b099bf5df657b5516fbf0948e742d1d1b36af2e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778224"
---
# <a name="pidtagresponserequested-canonical-property"></a><span data-ttu-id="ead13-103">PidTagResponseRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="ead13-103">PidTagResponseRequested Canonical Property</span></span>

  
  
<span data-ttu-id="ead13-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ead13-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ead13-105">包含 TRUE，如果发件人想对会议请求的响应。</span><span class="sxs-lookup"><span data-stu-id="ead13-105">Contains TRUE if the message sender wants a response to a meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ead13-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ead13-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ead13-107">PR_RESPONSE_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="ead13-107">PR_RESPONSE_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="ead13-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ead13-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ead13-109">0x0063</span><span class="sxs-lookup"><span data-stu-id="ead13-109">0x0063</span></span>  <br/> |
|<span data-ttu-id="ead13-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ead13-110">Data type:</span></span>  <br/> |<span data-ttu-id="ead13-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ead13-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ead13-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ead13-112">Area:</span></span>  <br/> |<span data-ttu-id="ead13-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="ead13-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ead13-114">说明</span><span class="sxs-lookup"><span data-stu-id="ead13-114">Remarks</span></span>

<span data-ttu-id="ead13-115">此属性用于会议请求。</span><span class="sxs-lookup"><span data-stu-id="ead13-115">This property is used for meeting requests.</span></span> <span data-ttu-id="ead13-116">接收的客户端应用程序应提示用户可以接受或拒绝该请求，然后发送回发件人此响应。</span><span class="sxs-lookup"><span data-stu-id="ead13-116">The receiving client application should prompt the user to accept or decline the request and then send this response back to the sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ead13-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ead13-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ead13-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="ead13-118">Protocol specifications</span></span>

<span data-ttu-id="ead13-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ead13-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ead13-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ead13-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ead13-121">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ead13-121">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ead13-122">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="ead13-122">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="ead13-123">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ead13-123">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ead13-124">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="ead13-124">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="ead13-125">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ead13-125">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ead13-126">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ead13-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ead13-127">头文件</span><span class="sxs-lookup"><span data-stu-id="ead13-127">Header files</span></span>

<span data-ttu-id="ead13-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ead13-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="ead13-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ead13-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="ead13-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ead13-130">Mapitags.h</span></span>
  
> <span data-ttu-id="ead13-131">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ead13-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ead13-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ead13-132">See also</span></span>



[<span data-ttu-id="ead13-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ead13-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ead13-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ead13-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ead13-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ead13-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ead13-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ead13-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

