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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 501b54cfb7846a91aec7172cbe1d846c24704923
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331498"
---
# <a name="pidnamecontentbase-canonical-property"></a><span data-ttu-id="558c4-103">PidNameContentBase 规范属性</span><span class="sxs-lookup"><span data-stu-id="558c4-103">PidNameContentBase Canonical Property</span></span>

  
  
<span data-ttu-id="558c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="558c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="558c4-105">包含 [RFC3282] Content-Base 标头字段值。</span><span class="sxs-lookup"><span data-stu-id="558c4-105">Contains an [RFC3282] Content-Base header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="558c4-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="558c4-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="558c4-107">BodyContentBase</span><span class="sxs-lookup"><span data-stu-id="558c4-107">BodyContentBase</span></span>  <br/> |
|<span data-ttu-id="558c4-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="558c4-108">Property set:</span></span>  <br/> |<span data-ttu-id="558c4-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="558c4-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="558c4-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="558c4-110">Property name:</span></span>  <br/> |<span data-ttu-id="558c4-111">Content-Base</span><span class="sxs-lookup"><span data-stu-id="558c4-111">Content-Base</span></span>  <br/> |
|<span data-ttu-id="558c4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="558c4-112">Data type:</span></span>  <br/> |<span data-ttu-id="558c4-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="558c4-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="558c4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="558c4-114">Area:</span></span>  <br/> |<span data-ttu-id="558c4-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="558c4-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="558c4-116">备注</span><span class="sxs-lookup"><span data-stu-id="558c4-116">Remarks</span></span>

<span data-ttu-id="558c4-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端必须将所需的值写入映射到邮件正文的 MIME 实体上的 Content-Base 头字段。</span><span class="sxs-lookup"><span data-stu-id="558c4-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write the desired value to a Content-Base header field on a MIME entity that maps to a message body.</span></span> <span data-ttu-id="558c4-118">MIME 阅读器必须将此类 MIME 实体上 Content-Base 头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="558c4-118">MIME readers must copy the value of a Content-Base header field on such a MIME entity to the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="558c4-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="558c4-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="558c4-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="558c4-120">Protocol specifications</span></span>

<span data-ttu-id="558c4-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="558c4-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="558c4-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="558c4-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="558c4-123">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="558c4-123">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="558c4-124">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="558c4-124">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="558c4-125">头文件</span><span class="sxs-lookup"><span data-stu-id="558c4-125">Header files</span></span>

<span data-ttu-id="558c4-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="558c4-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="558c4-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="558c4-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="558c4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="558c4-128">See also</span></span>



[<span data-ttu-id="558c4-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="558c4-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="558c4-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="558c4-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="558c4-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="558c4-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="558c4-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="558c4-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

