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
ms.openlocfilehash: a05743f2fa10326a358dd92a72cf530740274f2d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777413"
---
# <a name="pidtagbodycontentlocation-canonical-property"></a><span data-ttu-id="31ddd-103">PidTagBodyContentLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="31ddd-103">PidTagBodyContentLocation Canonical Property</span></span>

  
  
<span data-ttu-id="31ddd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31ddd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31ddd-105">包含 MIME 内容位置标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="31ddd-105">Contains the value of a MIME Content-Location header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="31ddd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="31ddd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="31ddd-107">PR_BODY_CONTENT_LOCATION，PR_BODY_CONTENT_LOCATION_A，PR_BODY_CONTENT_LOCATION_W</span><span class="sxs-lookup"><span data-stu-id="31ddd-107">PR_BODY_CONTENT_LOCATION, PR_BODY_CONTENT_LOCATION_A, PR_BODY_CONTENT_LOCATION_W</span></span>  <br/> |
|<span data-ttu-id="31ddd-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="31ddd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="31ddd-109">0x1014</span><span class="sxs-lookup"><span data-stu-id="31ddd-109">0x1014</span></span>  <br/> |
|<span data-ttu-id="31ddd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="31ddd-110">Data type:</span></span>  <br/> |<span data-ttu-id="31ddd-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="31ddd-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="31ddd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="31ddd-112">Area:</span></span>  <br/> |<span data-ttu-id="31ddd-113">MIME</span><span class="sxs-lookup"><span data-stu-id="31ddd-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="31ddd-114">说明</span><span class="sxs-lookup"><span data-stu-id="31ddd-114">Remarks</span></span>

<span data-ttu-id="31ddd-115">若要设置这些属性的值，MIME 客户端应所需的值都写入到内容位置标头字段映射到邮件正文 MIME 实体。</span><span class="sxs-lookup"><span data-stu-id="31ddd-115">To set the value of these properties, MIME clients should write the desired value to a Content-Location header field on a MIME entity that maps to a message body.</span></span>
  
<span data-ttu-id="31ddd-116">MIME 读者应将此类的 MIME 实体的内容位置标头字段的值复制到这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="31ddd-116">MIME readers should copy the value of a Content-Location header field on such a MIME entity to the value of these properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="31ddd-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="31ddd-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="31ddd-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="31ddd-118">Protocol specifications</span></span>

<span data-ttu-id="31ddd-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31ddd-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31ddd-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="31ddd-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="31ddd-121">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="31ddd-121">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="31ddd-122">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="31ddd-122">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="31ddd-123">头文件</span><span class="sxs-lookup"><span data-stu-id="31ddd-123">Header files</span></span>

<span data-ttu-id="31ddd-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="31ddd-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="31ddd-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="31ddd-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="31ddd-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="31ddd-126">Mapitags.h</span></span>
  
> <span data-ttu-id="31ddd-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="31ddd-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="31ddd-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31ddd-128">See also</span></span>



[<span data-ttu-id="31ddd-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="31ddd-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="31ddd-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="31ddd-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="31ddd-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="31ddd-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="31ddd-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="31ddd-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

