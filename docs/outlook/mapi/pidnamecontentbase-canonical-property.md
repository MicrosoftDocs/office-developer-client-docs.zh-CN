---
title: PidNameContentBase 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameContentBase
api_type:
- COM
ms.assetid: ab197ace-6e7d-4ec5-9f6d-4a63a1eda11c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 21469b944bb2ce5db0576e40012335d89d48cb49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777228"
---
# <a name="pidnamecontentbase-canonical-property"></a><span data-ttu-id="c17a6-103">PidNameContentBase 规范属性</span><span class="sxs-lookup"><span data-stu-id="c17a6-103">PidNameContentBase Canonical Property</span></span>

  
  
<span data-ttu-id="c17a6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c17a6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c17a6-105">包含 [RFC3282] 内容库标头字段值。</span><span class="sxs-lookup"><span data-stu-id="c17a6-105">Contains an [RFC3282] Content-Base header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c17a6-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="c17a6-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="c17a6-107">BodyContentBase</span><span class="sxs-lookup"><span data-stu-id="c17a6-107">BodyContentBase</span></span>  <br/> |
|<span data-ttu-id="c17a6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="c17a6-108">Property set:</span></span>  <br/> |<span data-ttu-id="c17a6-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="c17a6-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="c17a6-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="c17a6-110">Property name:</span></span>  <br/> |<span data-ttu-id="c17a6-111">内容库</span><span class="sxs-lookup"><span data-stu-id="c17a6-111">Content-Base</span></span>  <br/> |
|<span data-ttu-id="c17a6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c17a6-112">Data type:</span></span>  <br/> |<span data-ttu-id="c17a6-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c17a6-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="c17a6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c17a6-114">Area:</span></span>  <br/> |<span data-ttu-id="c17a6-115">Email</span><span class="sxs-lookup"><span data-stu-id="c17a6-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c17a6-116">备注</span><span class="sxs-lookup"><span data-stu-id="c17a6-116">Remarks</span></span>

<span data-ttu-id="c17a6-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端必须所需的值都写入到内容库头字段映射到邮件正文 MIME 实体。</span><span class="sxs-lookup"><span data-stu-id="c17a6-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write the desired value to a Content-Base header field on a MIME entity that maps to a message body.</span></span> <span data-ttu-id="c17a6-118">MIME 读者必须将此类的 MIME 实体的内容库标头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="c17a6-118">MIME readers must copy the value of a Content-Base header field on such a MIME entity to the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c17a6-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c17a6-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c17a6-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="c17a6-120">Protocol specifications</span></span>

<span data-ttu-id="c17a6-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c17a6-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c17a6-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c17a6-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c17a6-123">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c17a6-123">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c17a6-124">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="c17a6-124">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c17a6-125">头文件</span><span class="sxs-lookup"><span data-stu-id="c17a6-125">Header files</span></span>

<span data-ttu-id="c17a6-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c17a6-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="c17a6-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c17a6-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c17a6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c17a6-128">See also</span></span>



[<span data-ttu-id="c17a6-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c17a6-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c17a6-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c17a6-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c17a6-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c17a6-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c17a6-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c17a6-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

