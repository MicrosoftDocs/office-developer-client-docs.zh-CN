---
title: PidNameAcceptLanguage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameAcceptLanguage
api_type:
- COM
ms.assetid: 4b202bc1-f718-446a-950f-634ffee47baf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 855610c43cfaa64fa69e6987743b137b188d84a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360940"
---
# <a name="pidnameacceptlanguage-canonical-property"></a><span data-ttu-id="25435-103">PidNameAcceptLanguage 规范属性</span><span class="sxs-lookup"><span data-stu-id="25435-103">PidNameAcceptLanguage Canonical Property</span></span>

  
  
<span data-ttu-id="25435-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25435-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25435-105">包含 [RFC3282] 接受语言标头字段值。</span><span class="sxs-lookup"><span data-stu-id="25435-105">Contains an [RFC3282] Accept-Language header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="25435-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="25435-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="25435-107">AcceptLanguage</span><span class="sxs-lookup"><span data-stu-id="25435-107">AcceptLanguage</span></span>  <br/> |
|<span data-ttu-id="25435-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="25435-108">Property set:</span></span>  <br/> |<span data-ttu-id="25435-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="25435-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="25435-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="25435-110">Property name:</span></span>  <br/> |<span data-ttu-id="25435-111">Accept-Language</span><span class="sxs-lookup"><span data-stu-id="25435-111">Accept-Language</span></span>  <br/> |
|<span data-ttu-id="25435-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="25435-112">Data type:</span></span>  <br/> |<span data-ttu-id="25435-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="25435-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="25435-114">区域：</span><span class="sxs-lookup"><span data-stu-id="25435-114">Area:</span></span>  <br/> |<span data-ttu-id="25435-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="25435-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="25435-116">注解</span><span class="sxs-lookup"><span data-stu-id="25435-116">Remarks</span></span>

<span data-ttu-id="25435-117">若要设置此属性的值, 多用途 Internet 邮件扩展 (MIME) 客户端应使用所需的值来编写接受语言标头字段。</span><span class="sxs-lookup"><span data-stu-id="25435-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients should write an Accept-Language header field with the desired value.</span></span> <span data-ttu-id="25435-118">MIME 客户端可以改为写入 X-接受语言的标头字段。</span><span class="sxs-lookup"><span data-stu-id="25435-118">MIME clients may write an X-Accept-Language header field instead.</span></span> <span data-ttu-id="25435-119">MIME 阅读器应将任一头字段的值复制到该属性的值。</span><span class="sxs-lookup"><span data-stu-id="25435-119">MIME readers should copy the value of either header field to the value of this property.</span></span> <span data-ttu-id="25435-120">如果同时存在这两个标头字段, 则 MIME 阅读器应使用 Accept a Language 标头字段。</span><span class="sxs-lookup"><span data-stu-id="25435-120">If both header fields are present, MIME readers should use the Accept-Language header field.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="25435-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="25435-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="25435-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="25435-122">Protocol specifications</span></span>

<span data-ttu-id="25435-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="25435-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="25435-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="25435-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="25435-125">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="25435-125">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="25435-126">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="25435-126">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="25435-127">头文件</span><span class="sxs-lookup"><span data-stu-id="25435-127">Header files</span></span>

<span data-ttu-id="25435-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="25435-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="25435-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="25435-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="25435-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25435-130">See also</span></span>



[<span data-ttu-id="25435-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="25435-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="25435-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="25435-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="25435-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="25435-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="25435-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="25435-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

