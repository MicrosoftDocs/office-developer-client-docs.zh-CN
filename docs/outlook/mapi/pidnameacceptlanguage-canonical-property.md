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
ms.openlocfilehash: f66a570273d78f63ced110a4bdc8a12a49c531b6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595242"
---
# <a name="pidnameacceptlanguage-canonical-property"></a><span data-ttu-id="11efe-103">PidNameAcceptLanguage 规范属性</span><span class="sxs-lookup"><span data-stu-id="11efe-103">PidNameAcceptLanguage Canonical Property</span></span>

  
  
<span data-ttu-id="11efe-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="11efe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="11efe-105">包含 [RFC3282] 接受语言标头字段值。</span><span class="sxs-lookup"><span data-stu-id="11efe-105">Contains an [RFC3282] Accept-Language header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="11efe-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="11efe-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="11efe-107">AcceptLanguage</span><span class="sxs-lookup"><span data-stu-id="11efe-107">AcceptLanguage</span></span>  <br/> |
|<span data-ttu-id="11efe-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="11efe-108">Property set:</span></span>  <br/> |<span data-ttu-id="11efe-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="11efe-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="11efe-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="11efe-110">Property name:</span></span>  <br/> |<span data-ttu-id="11efe-111">接受语言</span><span class="sxs-lookup"><span data-stu-id="11efe-111">Accept-Language</span></span>  <br/> |
|<span data-ttu-id="11efe-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="11efe-112">Data type:</span></span>  <br/> |<span data-ttu-id="11efe-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="11efe-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="11efe-114">区域：</span><span class="sxs-lookup"><span data-stu-id="11efe-114">Area:</span></span>  <br/> |<span data-ttu-id="11efe-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="11efe-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="11efe-116">注解</span><span class="sxs-lookup"><span data-stu-id="11efe-116">Remarks</span></span>

<span data-ttu-id="11efe-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端应编写将接受语言标头字段与所需的值。</span><span class="sxs-lookup"><span data-stu-id="11efe-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients should write an Accept-Language header field with the desired value.</span></span> <span data-ttu-id="11efe-118">MIME 客户端可能会改为编写 X 接受语言标头字段。</span><span class="sxs-lookup"><span data-stu-id="11efe-118">MIME clients may write an X-Accept-Language header field instead.</span></span> <span data-ttu-id="11efe-119">MIME 读者应将任一标头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="11efe-119">MIME readers should copy the value of either header field to the value of this property.</span></span> <span data-ttu-id="11efe-120">如果存在两个标头字段时，MIME 读者应使用接受语言标头字段。</span><span class="sxs-lookup"><span data-stu-id="11efe-120">If both header fields are present, MIME readers should use the Accept-Language header field.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="11efe-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="11efe-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="11efe-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="11efe-122">Protocol specifications</span></span>

<span data-ttu-id="11efe-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="11efe-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="11efe-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="11efe-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="11efe-125">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="11efe-125">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="11efe-126">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="11efe-126">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="11efe-127">头文件</span><span class="sxs-lookup"><span data-stu-id="11efe-127">Header files</span></span>

<span data-ttu-id="11efe-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="11efe-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="11efe-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="11efe-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="11efe-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11efe-130">See also</span></span>



[<span data-ttu-id="11efe-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="11efe-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="11efe-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="11efe-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="11efe-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="11efe-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="11efe-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="11efe-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

