---
title: PidNameContentClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameContentClass
api_type:
- COM
ms.assetid: 6f623345-b30e-452f-a822-9308b455697a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 51788a49d1c0d01ef7ff5daca853000a8f1e34a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356348"
---
# <a name="pidnamecontentclass-canonical-property"></a><span data-ttu-id="137e1-103">PidNameContentClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="137e1-103">PidNameContentClass Canonical Property</span></span>

  
  
<span data-ttu-id="137e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="137e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="137e1-105">包含 [RFC3282] Content Class 标头字段值。</span><span class="sxs-lookup"><span data-stu-id="137e1-105">Contains an [RFC3282] Content-Class header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="137e1-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="137e1-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="137e1-107">无</span><span class="sxs-lookup"><span data-stu-id="137e1-107">None</span></span>  <br/> |
|<span data-ttu-id="137e1-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="137e1-108">Property set:</span></span>  <br/> |<span data-ttu-id="137e1-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="137e1-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="137e1-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="137e1-110">Property name:</span></span>  <br/> |<span data-ttu-id="137e1-111">Content 类</span><span class="sxs-lookup"><span data-stu-id="137e1-111">Content-Class</span></span>  <br/> |
|<span data-ttu-id="137e1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="137e1-112">Data type:</span></span>  <br/> |<span data-ttu-id="137e1-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="137e1-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="137e1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="137e1-114">Area:</span></span>  <br/> |<span data-ttu-id="137e1-115">电子邮件</span><span class="sxs-lookup"><span data-stu-id="137e1-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="137e1-116">注解</span><span class="sxs-lookup"><span data-stu-id="137e1-116">Remarks</span></span>

<span data-ttu-id="137e1-117">若要设置此属性的值, 多用途 Internet 邮件扩展 (MIME) 客户端必须使用所需值写入 Content Class 标头字段。</span><span class="sxs-lookup"><span data-stu-id="137e1-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write a Content-Class header field with the desired value.</span></span> <span data-ttu-id="137e1-118">MIME 读取器必须将 Content Class 标头字段的值复制到该属性的值。</span><span class="sxs-lookup"><span data-stu-id="137e1-118">MIME readers must copy the value of a Content-Class header field to the value of this property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="137e1-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="137e1-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="137e1-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="137e1-120">Protocol specifications</span></span>

<span data-ttu-id="137e1-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="137e1-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="137e1-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="137e1-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="137e1-123">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="137e1-123">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="137e1-124">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="137e1-124">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="137e1-125">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="137e1-125">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="137e1-126">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="137e1-126">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="137e1-127">头文件</span><span class="sxs-lookup"><span data-stu-id="137e1-127">Header files</span></span>

<span data-ttu-id="137e1-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="137e1-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="137e1-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="137e1-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="137e1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="137e1-130">See also</span></span>



[<span data-ttu-id="137e1-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="137e1-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="137e1-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="137e1-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="137e1-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="137e1-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="137e1-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="137e1-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

