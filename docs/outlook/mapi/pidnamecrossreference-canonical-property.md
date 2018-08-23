---
title: PidNameCrossReference 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameCrossReference
api_type:
- COM
ms.assetid: d16e1adf-c911-427e-9c98-678a303e6791
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5daf8c1ee249cfc7fb1bc1ffb6dfc68b400fe953
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571127"
---
# <a name="pidnamecrossreference-canonical-property"></a><span data-ttu-id="5b3e8-103">PidNameCrossReference 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b3e8-103">PidNameCrossReference Canonical Property</span></span>

  
  
<span data-ttu-id="5b3e8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5b3e8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5b3e8-105">包含 [RFC3282] Xref 标头字段值。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-105">Contains an [RFC3282] Xref header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5b3e8-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="5b3e8-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="5b3e8-107">无</span><span class="sxs-lookup"><span data-stu-id="5b3e8-107">None</span></span>  <br/> |
|<span data-ttu-id="5b3e8-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="5b3e8-108">Property set:</span></span>  <br/> |<span data-ttu-id="5b3e8-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="5b3e8-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="5b3e8-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="5b3e8-110">Property name:</span></span>  <br/> |<span data-ttu-id="5b3e8-111">Xref</span><span class="sxs-lookup"><span data-stu-id="5b3e8-111">Xref</span></span>  <br/> |
|<span data-ttu-id="5b3e8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5b3e8-112">Data type:</span></span>  <br/> |<span data-ttu-id="5b3e8-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5b3e8-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5b3e8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5b3e8-114">Area:</span></span>  <br/> |<span data-ttu-id="5b3e8-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="5b3e8-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5b3e8-116">注解</span><span class="sxs-lookup"><span data-stu-id="5b3e8-116">Remarks</span></span>

<span data-ttu-id="5b3e8-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端必须所需的值都写入到 XRef 标头字段中。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write the desired value to an XRef header field.</span></span> <span data-ttu-id="5b3e8-118">MIME 读者必须将 XRef 标头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-118">MIME readers must copy the value of an XRef header field to the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5b3e8-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="5b3e8-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5b3e8-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="5b3e8-120">Protocol specifications</span></span>

<span data-ttu-id="5b3e8-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b3e8-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b3e8-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5b3e8-123">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b3e8-123">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5b3e8-124">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-124">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5b3e8-125">头文件</span><span class="sxs-lookup"><span data-stu-id="5b3e8-125">Header files</span></span>

<span data-ttu-id="5b3e8-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5b3e8-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="5b3e8-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5b3e8-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5b3e8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b3e8-128">See also</span></span>



[<span data-ttu-id="5b3e8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5b3e8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5b3e8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5b3e8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5b3e8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5b3e8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5b3e8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5b3e8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

