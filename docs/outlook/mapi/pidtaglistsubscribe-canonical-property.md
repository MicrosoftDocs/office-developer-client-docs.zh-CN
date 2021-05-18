---
title: PidTagListSubscribe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListSubscribe
api_type:
- HeaderDef
ms.assetid: 97387a82-8e40-4c76-818c-2229fac12e01
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bee11c495d7f1ef21f9af70e6aa89f8c0d0f78b4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279655"
---
# <a name="pidtaglistsubscribe-canonical-property"></a><span data-ttu-id="294ba-103">PidTagListSubscribe 规范属性</span><span class="sxs-lookup"><span data-stu-id="294ba-103">PidTagListSubscribe Canonical Property</span></span>

  
  
<span data-ttu-id="294ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="294ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="294ba-105">包含多用途 Internet 邮件扩展 (MIME) 邮件的List-Subscribe字段。</span><span class="sxs-lookup"><span data-stu-id="294ba-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's List-Subscribe header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="294ba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="294ba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="294ba-107">PR_LIST_SUBSCRIBE、PR_LIST_SUBSCRIBE_A、PR_LIST_SUBSCRIBE_W</span><span class="sxs-lookup"><span data-stu-id="294ba-107">PR_LIST_SUBSCRIBE, PR_LIST_SUBSCRIBE_A, PR_LIST_SUBSCRIBE_W</span></span>  <br/> |
|<span data-ttu-id="294ba-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="294ba-108">Identifier:</span></span>  <br/> |<span data-ttu-id="294ba-109">0x1044</span><span class="sxs-lookup"><span data-stu-id="294ba-109">0x1044</span></span>  <br/> |
|<span data-ttu-id="294ba-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="294ba-110">Data type:</span></span>  <br/> |<span data-ttu-id="294ba-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="294ba-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="294ba-112">区域：</span><span class="sxs-lookup"><span data-stu-id="294ba-112">Area:</span></span>  <br/> |<span data-ttu-id="294ba-113">其他</span><span class="sxs-lookup"><span data-stu-id="294ba-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="294ba-114">备注</span><span class="sxs-lookup"><span data-stu-id="294ba-114">Remarks</span></span>

<span data-ttu-id="294ba-115">若要生成List-Subscribe字段，客户端必须将这些属性的值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="294ba-115">To generate a List-Subscribe header field, clients must set the value of these properties to the desired value.</span></span> <span data-ttu-id="294ba-116">MIME 编写器必须将这些属性的值复制到List-Subscribe字段中。</span><span class="sxs-lookup"><span data-stu-id="294ba-116">MIME writers must copy the value of these properties to the List-Subscribe header field.</span></span>
  
<span data-ttu-id="294ba-117">若要设置与服务器相关的类似属性的值，MIME 客户端必须编写下表中指定的头字段。</span><span class="sxs-lookup"><span data-stu-id="294ba-117">To set the value of server-related properties like these, MIME clients must write the header fields as specified in the following table.</span></span>
  
|<span data-ttu-id="294ba-118">**Property**</span><span class="sxs-lookup"><span data-stu-id="294ba-118">**Property**</span></span>|<span data-ttu-id="294ba-119">**首选标题字段名称**</span><span class="sxs-lookup"><span data-stu-id="294ba-119">**Preferred header field name**</span></span>|<span data-ttu-id="294ba-120">**备用标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="294ba-120">**Alternate header field name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="294ba-121">**PidTagListSubscribe**</span><span class="sxs-lookup"><span data-stu-id="294ba-121">**PidTagListSubscribe**</span></span> <br/> |<span data-ttu-id="294ba-122">List-Subscribe</span><span class="sxs-lookup"><span data-stu-id="294ba-122">List-Subscribe</span></span>  <br/> |<span data-ttu-id="294ba-123">X-List-Subscribe</span><span class="sxs-lookup"><span data-stu-id="294ba-123">X-List-Subscribe</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="294ba-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="294ba-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="294ba-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="294ba-125">Protocol specifications</span></span>

<span data-ttu-id="294ba-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="294ba-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="294ba-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="294ba-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="294ba-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="294ba-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="294ba-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="294ba-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="294ba-130">头文件</span><span class="sxs-lookup"><span data-stu-id="294ba-130">Header files</span></span>

<span data-ttu-id="294ba-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="294ba-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="294ba-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="294ba-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="294ba-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="294ba-133">Mapitags.h</span></span>
  
> <span data-ttu-id="294ba-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="294ba-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="294ba-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="294ba-135">See also</span></span>



[<span data-ttu-id="294ba-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="294ba-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="294ba-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="294ba-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="294ba-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="294ba-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="294ba-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="294ba-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

