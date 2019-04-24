---
title: PidLidCategories 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCategories
api_type:
- COM
ms.assetid: 6ad2aedc-405b-475e-ac76-7ecbbef28f73
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b2047f04f3f4a8d2b3e58e07a71e7e2463eff9cf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344973"
---
# <a name="pidlidcategories-canonical-property"></a><span data-ttu-id="70582-103">PidLidCategories 规范属性</span><span class="sxs-lookup"><span data-stu-id="70582-103">PidLidCategories Canonical Property</span></span>

  
  
<span data-ttu-id="70582-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70582-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70582-105">指定项的类别列表。</span><span class="sxs-lookup"><span data-stu-id="70582-105">Specifies a list of categories for an item.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70582-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="70582-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="70582-107">dispidCategories</span><span class="sxs-lookup"><span data-stu-id="70582-107">dispidCategories</span></span>  <br/> |
|<span data-ttu-id="70582-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="70582-108">Property set:</span></span>  <br/> |<span data-ttu-id="70582-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="70582-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="70582-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="70582-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="70582-111">0x00002328</span><span class="sxs-lookup"><span data-stu-id="70582-111">0x00002328</span></span>  <br/> |
|<span data-ttu-id="70582-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="70582-112">Data type:</span></span>  <br/> |<span data-ttu-id="70582-113">PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="70582-113">PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="70582-114">区域：</span><span class="sxs-lookup"><span data-stu-id="70582-114">Area:</span></span>  <br/> |<span data-ttu-id="70582-115">常见</span><span class="sxs-lookup"><span data-stu-id="70582-115">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="70582-116">注解</span><span class="sxs-lookup"><span data-stu-id="70582-116">Remarks</span></span>

<span data-ttu-id="70582-117">若要生成关键字标头字段, 客户端必须将此属性的值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="70582-117">To generate a keywords header field, clients must set the value of this property to the desired values.</span></span> <span data-ttu-id="70582-118">此属性包含多个字符串;应将每个类别映射到单个关键字。</span><span class="sxs-lookup"><span data-stu-id="70582-118">This property has multiple strings; each category should be mapped to a single keyword.</span></span>
  
<span data-ttu-id="70582-119">多用途 Internet 邮件扩展 (MIME) 编写器应将此属性的每个子值复制到关键字标头字段中的单独关键字中, 并用逗号 (u + 002C) 和空格 (u + 0020) 分隔每个关键字。</span><span class="sxs-lookup"><span data-stu-id="70582-119">Multipurpose Internet Mail Extensions (MIME) writers should copy each sub-value of this property to a separate keyword in the Keywords header field, with a comma (U+002C) and space (U+0020) separating each keyword.</span></span> <span data-ttu-id="70582-120">MIME 编写器可能会删除该属性, 而不是将其复制到关键字标头字段, 以避免不同组织中不同类别集之间发生冲突。</span><span class="sxs-lookup"><span data-stu-id="70582-120">MIME writers may drop this property instead of copying it to the keywords header field, in order to avoid conflict among different sets of categories in different organizations.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="70582-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="70582-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="70582-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="70582-122">Protocol specifications</span></span>

<span data-ttu-id="70582-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70582-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70582-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="70582-124">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="70582-125">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="70582-125">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="70582-126">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="70582-126">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="70582-127">头文件</span><span class="sxs-lookup"><span data-stu-id="70582-127">Header files</span></span>

<span data-ttu-id="70582-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="70582-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="70582-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="70582-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="70582-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70582-130">See also</span></span>



[<span data-ttu-id="70582-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="70582-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="70582-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="70582-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="70582-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="70582-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="70582-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="70582-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

