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
ms.openlocfilehash: 8f8706ec3db36cddbe7be7420ba27683c190cd43
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331442"
---
# <a name="pidnamecrossreference-canonical-property"></a><span data-ttu-id="35a44-103">PidNameCrossReference 规范属性</span><span class="sxs-lookup"><span data-stu-id="35a44-103">PidNameCrossReference Canonical Property</span></span>

  
  
<span data-ttu-id="35a44-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35a44-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35a44-105">包含 [RFC3282] Xref 头字段值。</span><span class="sxs-lookup"><span data-stu-id="35a44-105">Contains an [RFC3282] Xref header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="35a44-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="35a44-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="35a44-107">无</span><span class="sxs-lookup"><span data-stu-id="35a44-107">None</span></span>  <br/> |
|<span data-ttu-id="35a44-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="35a44-108">Property set:</span></span>  <br/> |<span data-ttu-id="35a44-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="35a44-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="35a44-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="35a44-110">Property name:</span></span>  <br/> |<span data-ttu-id="35a44-111">Xref</span><span class="sxs-lookup"><span data-stu-id="35a44-111">Xref</span></span>  <br/> |
|<span data-ttu-id="35a44-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="35a44-112">Data type:</span></span>  <br/> |<span data-ttu-id="35a44-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="35a44-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="35a44-114">区域：</span><span class="sxs-lookup"><span data-stu-id="35a44-114">Area:</span></span>  <br/> |<span data-ttu-id="35a44-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="35a44-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="35a44-116">备注</span><span class="sxs-lookup"><span data-stu-id="35a44-116">Remarks</span></span>

<span data-ttu-id="35a44-117">若要设置此属性的值，MIME 客户端的多用途 Internet 邮件扩展 (MIME) 必须将所需的值写入 XRef 头字段。</span><span class="sxs-lookup"><span data-stu-id="35a44-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write the desired value to an XRef header field.</span></span> <span data-ttu-id="35a44-118">MIME 读取器必须将 XRef 头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="35a44-118">MIME readers must copy the value of an XRef header field to the value of this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="35a44-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="35a44-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="35a44-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="35a44-120">Protocol specifications</span></span>

<span data-ttu-id="35a44-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35a44-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35a44-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="35a44-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="35a44-123">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35a44-123">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35a44-124">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="35a44-124">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="35a44-125">头文件</span><span class="sxs-lookup"><span data-stu-id="35a44-125">Header files</span></span>

<span data-ttu-id="35a44-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="35a44-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="35a44-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="35a44-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="35a44-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35a44-128">See also</span></span>



[<span data-ttu-id="35a44-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="35a44-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="35a44-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="35a44-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="35a44-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="35a44-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="35a44-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="35a44-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

