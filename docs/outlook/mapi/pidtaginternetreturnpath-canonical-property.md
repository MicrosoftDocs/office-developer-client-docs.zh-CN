---
title: PidTagInternetReturnPath 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetReturnPath
api_type:
- HeaderDef
ms.assetid: 4530dbcf-9436-4f29-b79e-1bb0f791f60b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b3f108ff1053c0aa1046597cd2f11b74bc2dab0c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574172"
---
# <a name="pidtaginternetreturnpath-canonical-property"></a><span data-ttu-id="fd0da-103">PidTagInternetReturnPath 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd0da-103">PidTagInternetReturnPath Canonical Property</span></span>

  
  
<span data-ttu-id="fd0da-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd0da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd0da-105">包含多用途 Internet 邮件扩展 (MIME) 消息的返回路径标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="fd0da-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's Return-Path header field.</span></span> <span data-ttu-id="fd0da-106">发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fd0da-106">The email address of the message's sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fd0da-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fd0da-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="fd0da-108">PR_INTERNET_RETURN_PATH，PR_INTERNET_RETURN_PATH_A，PR_INTERNET_RETURN_PATH_W</span><span class="sxs-lookup"><span data-stu-id="fd0da-108">PR_INTERNET_RETURN_PATH, PR_INTERNET_RETURN_PATH_A, PR_INTERNET_RETURN_PATH_W</span></span>  <br/> |
|<span data-ttu-id="fd0da-109">标识符：</span><span class="sxs-lookup"><span data-stu-id="fd0da-109">Identifier:</span></span>  <br/> |<span data-ttu-id="fd0da-110">0x1046</span><span class="sxs-lookup"><span data-stu-id="fd0da-110">0x1046</span></span>  <br/> |
|<span data-ttu-id="fd0da-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fd0da-111">Data type:</span></span>  <br/> |<span data-ttu-id="fd0da-112">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fd0da-112">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="fd0da-113">区域：</span><span class="sxs-lookup"><span data-stu-id="fd0da-113">Area:</span></span>  <br/> |<span data-ttu-id="fd0da-114">MIME</span><span class="sxs-lookup"><span data-stu-id="fd0da-114">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd0da-115">注解</span><span class="sxs-lookup"><span data-stu-id="fd0da-115">Remarks</span></span>

<span data-ttu-id="fd0da-116">若要检索此属性的值，首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取的属性标记，然后指定[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中的此属性标记。</span><span class="sxs-lookup"><span data-stu-id="fd0da-116">To retrieve the value of this property, first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="fd0da-117">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="fd0da-117">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fd0da-118">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="fd0da-118">lpGuid:</span></span>  <br/> |<span data-ttu-id="fd0da-119">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="fd0da-119">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="fd0da-120">ulKind:</span><span class="sxs-lookup"><span data-stu-id="fd0da-120">ulKind:</span></span>  <br/> |<span data-ttu-id="fd0da-121">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="fd0da-121">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="fd0da-122">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="fd0da-122">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="fd0da-123">L"返回路径"</span><span class="sxs-lookup"><span data-stu-id="fd0da-123">L"return-path"</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="fd0da-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="fd0da-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fd0da-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="fd0da-125">Protocol specifications</span></span>

<span data-ttu-id="fd0da-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd0da-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd0da-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fd0da-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fd0da-128">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fd0da-128">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fd0da-129">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="fd0da-129">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fd0da-130">头文件</span><span class="sxs-lookup"><span data-stu-id="fd0da-130">Header files</span></span>

<span data-ttu-id="fd0da-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fd0da-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="fd0da-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fd0da-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="fd0da-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fd0da-133">Mapitags.h</span></span>
  
> <span data-ttu-id="fd0da-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fd0da-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fd0da-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd0da-135">See also</span></span>



[<span data-ttu-id="fd0da-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fd0da-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fd0da-137">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="fd0da-137">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="fd0da-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd0da-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fd0da-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fd0da-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fd0da-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fd0da-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

