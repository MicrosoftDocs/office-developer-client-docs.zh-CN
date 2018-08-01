---
title: PidTagInternetReferences 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetReferences
api_type:
- HeaderDef
ms.assetid: 645fe61d-414a-455e-b034-db3cfd003b9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4558fcdba11aed92eb21972ed62320209ade77ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777754"
---
# <a name="pidtaginternetreferences-canonical-property"></a><span data-ttu-id="c5d7f-103">PidTagInternetReferences 规范属性</span><span class="sxs-lookup"><span data-stu-id="c5d7f-103">PidTagInternetReferences Canonical Property</span></span>

  
  
<span data-ttu-id="c5d7f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c5d7f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c5d7f-105">包含多用途 Internet 邮件扩展 (MIME) 消息的引用标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's References header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c5d7f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c5d7f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c5d7f-107">PR_INTERNET_REFERENCES，PR_INTERNET_REFERENCES_A，PR_INTERNET_REFERENCES_W</span><span class="sxs-lookup"><span data-stu-id="c5d7f-107">PR_INTERNET_REFERENCES, PR_INTERNET_REFERENCES_A, PR_INTERNET_REFERENCES_W</span></span>  <br/> |
|<span data-ttu-id="c5d7f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c5d7f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c5d7f-109">0x1039</span><span class="sxs-lookup"><span data-stu-id="c5d7f-109">0x1039</span></span>  <br/> |
|<span data-ttu-id="c5d7f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c5d7f-110">Data type:</span></span>  <br/> |<span data-ttu-id="c5d7f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c5d7f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="c5d7f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c5d7f-112">Area:</span></span>  <br/> |<span data-ttu-id="c5d7f-113">MIME</span><span class="sxs-lookup"><span data-stu-id="c5d7f-113">MIME</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c5d7f-114">说明</span><span class="sxs-lookup"><span data-stu-id="c5d7f-114">Remarks</span></span>

<span data-ttu-id="c5d7f-115">若要生成一个引用标头字段，客户端必须将这些属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-115">To generate a References header field, clients must set these properties to the desired value.</span></span> <span data-ttu-id="c5d7f-116">MIME 作者必须将这些属性的值复制到引用标头字段。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-116">MIME writers must copy the value of these properties to the References header field.</span></span>
  
<span data-ttu-id="c5d7f-117">若要设置这些属性的值，MIME 客户端必须所需的值都写入到一个引用标头字段中。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-117">To set the value of these properties, MIME clients must write the desired value to a References header field.</span></span> <span data-ttu-id="c5d7f-118">MIME 读者必须将引用标头字段的值复制到这些属性。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-118">MIME readers must copy the value of the References header field to these properties.</span></span> <span data-ttu-id="c5d7f-119">MIME 读者可能会截断这些属性的值，如果它的长度超过 64 KB。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-119">MIME readers may truncate the value of these properties if it exceeds 64KB in length.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c5d7f-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="c5d7f-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c5d7f-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="c5d7f-121">Protocol specifications</span></span>

<span data-ttu-id="c5d7f-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d7f-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c5d7f-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c5d7f-124">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c5d7f-124">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c5d7f-125">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-125">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c5d7f-126">头文件</span><span class="sxs-lookup"><span data-stu-id="c5d7f-126">Header files</span></span>

<span data-ttu-id="c5d7f-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c5d7f-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="c5d7f-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="c5d7f-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c5d7f-129">Mapitags.h</span></span>
  
> <span data-ttu-id="c5d7f-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c5d7f-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c5d7f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d7f-131">See also</span></span>



[<span data-ttu-id="c5d7f-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c5d7f-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c5d7f-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c5d7f-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c5d7f-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c5d7f-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c5d7f-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c5d7f-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

