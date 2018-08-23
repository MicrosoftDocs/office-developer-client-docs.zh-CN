---
title: PidTagReceivedByAddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedByAddressType
api_type:
- COM
ms.assetid: 0eef299d-6923-4dae-9a18-91ea82ea0f3e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cd7a287a2240d372edf6cca6bac522266c0ca620
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581165"
---
# <a name="pidtagreceivedbyaddresstype-canonical-property"></a><span data-ttu-id="ad60c-103">PidTagReceivedByAddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad60c-103">PidTagReceivedByAddressType Canonical Property</span></span>

  
  
<span data-ttu-id="ad60c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad60c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad60c-105">包含的电子邮件地址类型，如 SMTP，实际收到邮件的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="ad60c-105">Contains the email address type, such as SMTP, for the messaging user who actually receives the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ad60c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ad60c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ad60c-107">PR_RECEIVED_BY_ADDRTYPE，PR_RECEIVED_BY_ADDRTYPE_A，PR_RECEIVED_BY_ADDRTYPE_W</span><span class="sxs-lookup"><span data-stu-id="ad60c-107">PR_RECEIVED_BY_ADDRTYPE, PR_RECEIVED_BY_ADDRTYPE_A, PR_RECEIVED_BY_ADDRTYPE_W</span></span>  <br/> |
|<span data-ttu-id="ad60c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ad60c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ad60c-109">0x0075</span><span class="sxs-lookup"><span data-stu-id="ad60c-109">0x0075</span></span>  <br/> |
|<span data-ttu-id="ad60c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ad60c-110">Data type:</span></span>  <br/> |<span data-ttu-id="ad60c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ad60c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ad60c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ad60c-112">Area:</span></span>  <br/> |<span data-ttu-id="ad60c-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="ad60c-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ad60c-114">注解</span><span class="sxs-lookup"><span data-stu-id="ad60c-114">Remarks</span></span>

<span data-ttu-id="ad60c-115">这些属性是实际收到邮件的邮件用户的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="ad60c-115">These properties are examples of the address properties for the messaging user who actually receives the message.</span></span> <span data-ttu-id="ad60c-116">它们必须由传入传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="ad60c-116">They must be set by the incoming transport provider.</span></span>
  
<span data-ttu-id="ad60c-117">地址类型字符串可以包含仅的大写字母字符 A 到 Z 和数字 0 到 9。</span><span class="sxs-lookup"><span data-stu-id="ad60c-117">The address type string can contain only the uppercase alphabetic characters A through Z and the numbers zero through nine.</span></span> <span data-ttu-id="ad60c-118">这些属性通过指定地址类型，如 SMTP，从而指示应如何构造地址限定**PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ad60c-118">These properties qualify the **PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md)) property by specifying an address type, such as SMTP, thereby indicating how the address should be constructed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ad60c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="ad60c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ad60c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="ad60c-120">Protocol specifications</span></span>

<span data-ttu-id="ad60c-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ad60c-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ad60c-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ad60c-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ad60c-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ad60c-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ad60c-124">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="ad60c-124">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ad60c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ad60c-125">Header files</span></span>

<span data-ttu-id="ad60c-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ad60c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ad60c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ad60c-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="ad60c-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ad60c-128">Mapitags.h</span></span>
  
> <span data-ttu-id="ad60c-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ad60c-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad60c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad60c-130">See also</span></span>



[<span data-ttu-id="ad60c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ad60c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ad60c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad60c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ad60c-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ad60c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ad60c-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ad60c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

