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
# <a name="pidnameacceptlanguage-canonical-property"></a><span data-ttu-id="e4759-103">PidNameAcceptLanguage 规范属性</span><span class="sxs-lookup"><span data-stu-id="e4759-103">PidNameAcceptLanguage Canonical Property</span></span>

  
  
<span data-ttu-id="e4759-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4759-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4759-105">包含一个 [RFC3282] Accept-Language标头字段值。</span><span class="sxs-lookup"><span data-stu-id="e4759-105">Contains an [RFC3282] Accept-Language header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e4759-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="e4759-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="e4759-107">AcceptLanguage</span><span class="sxs-lookup"><span data-stu-id="e4759-107">AcceptLanguage</span></span>  <br/> |
|<span data-ttu-id="e4759-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="e4759-108">Property set:</span></span>  <br/> |<span data-ttu-id="e4759-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="e4759-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="e4759-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="e4759-110">Property name:</span></span>  <br/> |<span data-ttu-id="e4759-111">Accept-Language</span><span class="sxs-lookup"><span data-stu-id="e4759-111">Accept-Language</span></span>  <br/> |
|<span data-ttu-id="e4759-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e4759-112">Data type:</span></span>  <br/> |<span data-ttu-id="e4759-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e4759-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e4759-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e4759-114">Area:</span></span>  <br/> |<span data-ttu-id="e4759-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="e4759-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4759-116">备注</span><span class="sxs-lookup"><span data-stu-id="e4759-116">Remarks</span></span>

<span data-ttu-id="e4759-117">若要设置此属性的值，MIME 客户端的多用途 Internet 邮件扩展 (MIME) 编写具有所需值的 Accept-Language 头字段。</span><span class="sxs-lookup"><span data-stu-id="e4759-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients should write an Accept-Language header field with the desired value.</span></span> <span data-ttu-id="e4759-118">MIME 客户端可以改为编写 X-Accept-Language 头字段。</span><span class="sxs-lookup"><span data-stu-id="e4759-118">MIME clients may write an X-Accept-Language header field instead.</span></span> <span data-ttu-id="e4759-119">MIME 读者应该将任一头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="e4759-119">MIME readers should copy the value of either header field to the value of this property.</span></span> <span data-ttu-id="e4759-120">如果存在这两个头字段，则 MIME 读者应该使用 Accept-Language 头字段。</span><span class="sxs-lookup"><span data-stu-id="e4759-120">If both header fields are present, MIME readers should use the Accept-Language header field.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e4759-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="e4759-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e4759-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="e4759-122">Protocol specifications</span></span>

<span data-ttu-id="e4759-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4759-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4759-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="e4759-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e4759-125">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4759-125">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4759-126">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="e4759-126">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e4759-127">头文件</span><span class="sxs-lookup"><span data-stu-id="e4759-127">Header files</span></span>

<span data-ttu-id="e4759-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e4759-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="e4759-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e4759-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e4759-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4759-130">See also</span></span>



[<span data-ttu-id="e4759-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e4759-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e4759-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e4759-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e4759-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e4759-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e4759-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e4759-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

