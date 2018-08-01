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
ms.openlocfilehash: d2c2fb31b722e76034b08077632c817d6adde802
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777170"
---
# <a name="pidnameacceptlanguage-canonical-property"></a><span data-ttu-id="aceeb-103">PidNameAcceptLanguage 规范属性</span><span class="sxs-lookup"><span data-stu-id="aceeb-103">PidNameAcceptLanguage Canonical Property</span></span>

  
  
<span data-ttu-id="aceeb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="aceeb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="aceeb-105">包含 [RFC3282] 接受语言标头字段值。</span><span class="sxs-lookup"><span data-stu-id="aceeb-105">Contains an [RFC3282] Accept-Language header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aceeb-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="aceeb-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="aceeb-107">AcceptLanguage</span><span class="sxs-lookup"><span data-stu-id="aceeb-107">AcceptLanguage</span></span>  <br/> |
|<span data-ttu-id="aceeb-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="aceeb-108">Property set:</span></span>  <br/> |<span data-ttu-id="aceeb-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="aceeb-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="aceeb-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="aceeb-110">Property name:</span></span>  <br/> |<span data-ttu-id="aceeb-111">接受语言</span><span class="sxs-lookup"><span data-stu-id="aceeb-111">Accept-Language</span></span>  <br/> |
|<span data-ttu-id="aceeb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="aceeb-112">Data type:</span></span>  <br/> |<span data-ttu-id="aceeb-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="aceeb-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="aceeb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="aceeb-114">Area:</span></span>  <br/> |<span data-ttu-id="aceeb-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="aceeb-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aceeb-116">说明</span><span class="sxs-lookup"><span data-stu-id="aceeb-116">Remarks</span></span>

<span data-ttu-id="aceeb-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端应编写将接受语言标头字段与所需的值。</span><span class="sxs-lookup"><span data-stu-id="aceeb-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients should write an Accept-Language header field with the desired value.</span></span> <span data-ttu-id="aceeb-118">MIME 客户端可能会改为编写 X 接受语言标头字段。</span><span class="sxs-lookup"><span data-stu-id="aceeb-118">MIME clients may write an X-Accept-Language header field instead.</span></span> <span data-ttu-id="aceeb-119">MIME 读者应将任一标头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="aceeb-119">MIME readers should copy the value of either header field to the value of this property.</span></span> <span data-ttu-id="aceeb-120">如果存在两个标头字段时，MIME 读者应使用接受语言标头字段。</span><span class="sxs-lookup"><span data-stu-id="aceeb-120">If both header fields are present, MIME readers should use the Accept-Language header field.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="aceeb-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="aceeb-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="aceeb-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="aceeb-122">Protocol specifications</span></span>

<span data-ttu-id="aceeb-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aceeb-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aceeb-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="aceeb-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="aceeb-125">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="aceeb-125">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="aceeb-126">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="aceeb-126">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="aceeb-127">头文件</span><span class="sxs-lookup"><span data-stu-id="aceeb-127">Header files</span></span>

<span data-ttu-id="aceeb-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aceeb-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="aceeb-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="aceeb-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aceeb-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aceeb-130">See also</span></span>



[<span data-ttu-id="aceeb-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aceeb-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="aceeb-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="aceeb-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="aceeb-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="aceeb-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="aceeb-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="aceeb-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

