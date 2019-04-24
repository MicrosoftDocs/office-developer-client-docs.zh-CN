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
ms.openlocfilehash: c2d8eaf627f789c3e862a83d71e4ca2e3e55e1e0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327956"
---
# <a name="pidtaginternetreturnpath-canonical-property"></a><span data-ttu-id="2626f-103">PidTagInternetReturnPath 规范属性</span><span class="sxs-lookup"><span data-stu-id="2626f-103">PidTagInternetReturnPath Canonical Property</span></span>

  
  
<span data-ttu-id="2626f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2626f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2626f-105">包含多用途 Internet 邮件扩展 (MIME) 邮件的返回路径头字段的值。</span><span class="sxs-lookup"><span data-stu-id="2626f-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's Return-Path header field.</span></span> <span data-ttu-id="2626f-106">邮件发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2626f-106">The email address of the message's sender.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2626f-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2626f-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="2626f-108">PR_INTERNET_RETURN_PATH、PR_INTERNET_RETURN_PATH_A、PR_INTERNET_RETURN_PATH_W</span><span class="sxs-lookup"><span data-stu-id="2626f-108">PR_INTERNET_RETURN_PATH, PR_INTERNET_RETURN_PATH_A, PR_INTERNET_RETURN_PATH_W</span></span>  <br/> |
|<span data-ttu-id="2626f-109">标识符:</span><span class="sxs-lookup"><span data-stu-id="2626f-109">Identifier:</span></span>  <br/> |<span data-ttu-id="2626f-110">0x1046</span><span class="sxs-lookup"><span data-stu-id="2626f-110">0x1046</span></span>  <br/> |
|<span data-ttu-id="2626f-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2626f-111">Data type:</span></span>  <br/> |<span data-ttu-id="2626f-112">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2626f-112">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2626f-113">区域：</span><span class="sxs-lookup"><span data-stu-id="2626f-113">Area:</span></span>  <br/> |<span data-ttu-id="2626f-114">MIME</span><span class="sxs-lookup"><span data-stu-id="2626f-114">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2626f-115">注解</span><span class="sxs-lookup"><span data-stu-id="2626f-115">Remarks</span></span>

<span data-ttu-id="2626f-116">若要检索此属性的值, 请先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="2626f-116">To retrieve the value of this property, first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="2626f-117">调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:</span><span class="sxs-lookup"><span data-stu-id="2626f-117">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2626f-118">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="2626f-118">lpGuid:</span></span>  <br/> |<span data-ttu-id="2626f-119">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="2626f-119">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="2626f-120">ulKind:</span><span class="sxs-lookup"><span data-stu-id="2626f-120">ulKind:</span></span>  <br/> |<span data-ttu-id="2626f-121">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="2626f-121">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="2626f-122">类型 lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="2626f-122">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="2626f-123">L "return-路径"</span><span class="sxs-lookup"><span data-stu-id="2626f-123">L"return-path"</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="2626f-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="2626f-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2626f-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="2626f-125">Protocol specifications</span></span>

<span data-ttu-id="2626f-126">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2626f-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2626f-127">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2626f-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2626f-128">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2626f-128">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2626f-129">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="2626f-129">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2626f-130">头文件</span><span class="sxs-lookup"><span data-stu-id="2626f-130">Header files</span></span>

<span data-ttu-id="2626f-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2626f-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="2626f-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2626f-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="2626f-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="2626f-133">Mapitags.h</span></span>
  
> <span data-ttu-id="2626f-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2626f-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2626f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2626f-135">See also</span></span>



[<span data-ttu-id="2626f-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2626f-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2626f-137">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2626f-137">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="2626f-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2626f-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2626f-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2626f-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2626f-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2626f-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

