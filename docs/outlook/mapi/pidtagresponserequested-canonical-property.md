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
ms.openlocfilehash: 77c724affd2057ca6347d752323c5ba0a3094ecf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330154"
---
# <a name="pidtagresponserequested-canonical-property"></a><span data-ttu-id="9f04e-103">PidTagResponseRequested 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f04e-103">PidTagResponseRequested Canonical Property</span></span>

  
  
<span data-ttu-id="9f04e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f04e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f04e-105">如果邮件发件人想要响应会议请求, 则该参数包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9f04e-105">Contains TRUE if the message sender wants a response to a meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9f04e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9f04e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9f04e-107">PR_RESPONSE_REQUESTED</span><span class="sxs-lookup"><span data-stu-id="9f04e-107">PR_RESPONSE_REQUESTED</span></span>  <br/> |
|<span data-ttu-id="9f04e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9f04e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9f04e-109">0x0063</span><span class="sxs-lookup"><span data-stu-id="9f04e-109">0x0063</span></span>  <br/> |
|<span data-ttu-id="9f04e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9f04e-110">Data type:</span></span>  <br/> |<span data-ttu-id="9f04e-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="9f04e-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="9f04e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9f04e-112">Area:</span></span>  <br/> |<span data-ttu-id="9f04e-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="9f04e-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f04e-114">注解</span><span class="sxs-lookup"><span data-stu-id="9f04e-114">Remarks</span></span>

<span data-ttu-id="9f04e-115">此属性用于会议请求。</span><span class="sxs-lookup"><span data-stu-id="9f04e-115">This property is used for meeting requests.</span></span> <span data-ttu-id="9f04e-116">接收客户端应用程序应提示用户接受或拒绝请求, 然后将此响应发送回发件人。</span><span class="sxs-lookup"><span data-stu-id="9f04e-116">The receiving client application should prompt the user to accept or decline the request and then send this response back to the sender.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9f04e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9f04e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9f04e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="9f04e-118">Protocol specifications</span></span>

<span data-ttu-id="9f04e-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f04e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f04e-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9f04e-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9f04e-121">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f04e-121">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f04e-122">指定在电子邮件中允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9f04e-122">Specifies the properties and operations that are permissible on email messages.</span></span>
    
<span data-ttu-id="9f04e-123">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f04e-123">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f04e-124">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9f04e-124">Specifies the properties and operations related to flagging.</span></span>
    
<span data-ttu-id="9f04e-125">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9f04e-125">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9f04e-126">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9f04e-126">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9f04e-127">头文件</span><span class="sxs-lookup"><span data-stu-id="9f04e-127">Header files</span></span>

<span data-ttu-id="9f04e-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9f04e-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="9f04e-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9f04e-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="9f04e-130">Mapitags</span><span class="sxs-lookup"><span data-stu-id="9f04e-130">Mapitags.h</span></span>
  
> <span data-ttu-id="9f04e-131">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9f04e-131">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9f04e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f04e-132">See also</span></span>



[<span data-ttu-id="9f04e-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9f04e-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9f04e-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f04e-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9f04e-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9f04e-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9f04e-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9f04e-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

