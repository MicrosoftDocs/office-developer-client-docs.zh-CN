---
title: PidTagBodyContentLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBodyContentLocation
api_type:
- HeaderDef
ms.assetid: a66d1c64-5c5a-4980-9acd-72448108fd2c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 90a873174b5b990f165d0b2173efa38fc7df2d9d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350937"
---
# <a name="pidtagbodycontentlocation-canonical-property"></a><span data-ttu-id="47364-103">PidTagBodyContentLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="47364-103">PidTagBodyContentLocation Canonical Property</span></span>

  
  
<span data-ttu-id="47364-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47364-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47364-105">包含 MIME Content-Location 头字段的值。</span><span class="sxs-lookup"><span data-stu-id="47364-105">Contains the value of a MIME Content-Location header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="47364-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="47364-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="47364-107">PR_BODY_CONTENT_LOCATION、PR_BODY_CONTENT_LOCATION_A、PR_BODY_CONTENT_LOCATION_W</span><span class="sxs-lookup"><span data-stu-id="47364-107">PR_BODY_CONTENT_LOCATION, PR_BODY_CONTENT_LOCATION_A, PR_BODY_CONTENT_LOCATION_W</span></span>  <br/> |
|<span data-ttu-id="47364-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="47364-108">Identifier:</span></span>  <br/> |<span data-ttu-id="47364-109">0x1014</span><span class="sxs-lookup"><span data-stu-id="47364-109">0x1014</span></span>  <br/> |
|<span data-ttu-id="47364-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="47364-110">Data type:</span></span>  <br/> |<span data-ttu-id="47364-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="47364-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="47364-112">区域：</span><span class="sxs-lookup"><span data-stu-id="47364-112">Area:</span></span>  <br/> |<span data-ttu-id="47364-113">MIME</span><span class="sxs-lookup"><span data-stu-id="47364-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47364-114">备注</span><span class="sxs-lookup"><span data-stu-id="47364-114">Remarks</span></span>

<span data-ttu-id="47364-115">若要设置这些属性的值，MIME 客户端应该将所需的值写入映射到邮件正文的 MIME 实体上的 Content-Location 头字段。</span><span class="sxs-lookup"><span data-stu-id="47364-115">To set the value of these properties, MIME clients should write the desired value to a Content-Location header field on a MIME entity that maps to a message body.</span></span>
  
<span data-ttu-id="47364-116">MIME 读者应将此类 MIME 实体上 Content-Location 头字段的值复制到这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="47364-116">MIME readers should copy the value of a Content-Location header field on such a MIME entity to the value of these properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="47364-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="47364-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="47364-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="47364-118">Protocol specifications</span></span>

<span data-ttu-id="47364-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="47364-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="47364-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="47364-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="47364-121">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="47364-121">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="47364-122">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="47364-122">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="47364-123">头文件</span><span class="sxs-lookup"><span data-stu-id="47364-123">Header files</span></span>

<span data-ttu-id="47364-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="47364-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="47364-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="47364-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="47364-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="47364-126">Mapitags.h</span></span>
  
> <span data-ttu-id="47364-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="47364-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="47364-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47364-128">See also</span></span>



[<span data-ttu-id="47364-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="47364-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="47364-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="47364-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="47364-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="47364-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="47364-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="47364-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

