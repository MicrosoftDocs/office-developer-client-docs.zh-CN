---
title: PidTagNextSendAcct 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNextSendAcct
api_type:
- HeaderDef
ms.assetid: b7429c2e-0d9d-4921-9f56-9ecad817f8cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 76584e248f03deac62af94e4638fcead15594b3e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581130"
---
# <a name="pidtagnextsendacct-canonical-property"></a><span data-ttu-id="7246e-103">PidTagNextSendAcct 规范属性</span><span class="sxs-lookup"><span data-stu-id="7246e-103">PidTagNextSendAcct Canonical Property</span></span>

  
  
<span data-ttu-id="7246e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7246e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7246e-105">指定客户端当前尝试使用来发送电子邮件的服务器。</span><span class="sxs-lookup"><span data-stu-id="7246e-105">Specifies the server that a client is currently attempting to use to send email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7246e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7246e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7246e-107">PR_NEXT_SEND_ACCT</span><span class="sxs-lookup"><span data-stu-id="7246e-107">PR_NEXT_SEND_ACCT</span></span>  <br/> |
|<span data-ttu-id="7246e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7246e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7246e-109">0x0E29</span><span class="sxs-lookup"><span data-stu-id="7246e-109">0x0E29</span></span>  <br/> |
|<span data-ttu-id="7246e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7246e-110">Data type:</span></span>  <br/> |<span data-ttu-id="7246e-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7246e-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7246e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7246e-112">Area:</span></span>  <br/> |<span data-ttu-id="7246e-113">Outlook 应用程序</span><span class="sxs-lookup"><span data-stu-id="7246e-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7246e-114">注解</span><span class="sxs-lookup"><span data-stu-id="7246e-114">Remarks</span></span>

<span data-ttu-id="7246e-115">此属性的格式是实现相关。</span><span class="sxs-lookup"><span data-stu-id="7246e-115">The format of this property is implementation dependent.</span></span> <span data-ttu-id="7246e-116">此属性可由客户端用来确定哪些服务器直接将电子邮件到，但是可选的和值没有任何意义到服务器。</span><span class="sxs-lookup"><span data-stu-id="7246e-116">This property can be used by the client to determine which server to direct the email to, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7246e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="7246e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7246e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="7246e-118">Protocol specifications</span></span>

<span data-ttu-id="7246e-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7246e-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7246e-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="7246e-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7246e-121">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7246e-121">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7246e-122">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="7246e-122">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="7246e-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7246e-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7246e-124">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="7246e-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7246e-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7246e-125">Header files</span></span>

<span data-ttu-id="7246e-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7246e-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7246e-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7246e-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="7246e-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7246e-128">Mapitags.h</span></span>
  
> <span data-ttu-id="7246e-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7246e-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7246e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7246e-130">See also</span></span>



[<span data-ttu-id="7246e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7246e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7246e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7246e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7246e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7246e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7246e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7246e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

