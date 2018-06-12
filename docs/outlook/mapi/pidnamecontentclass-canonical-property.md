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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 1ad4f83cb9021cef82ce62b6b6f5616a3fc3d118
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777205"
---
# <a name="pidnamecontentclass-canonical-property"></a><span data-ttu-id="3cc14-103">PidNameContentClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cc14-103">PidNameContentClass Canonical Property</span></span>

  
  
<span data-ttu-id="3cc14-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3cc14-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cc14-105">包含 [RFC3282] Content-class 标头字段值。</span><span class="sxs-lookup"><span data-stu-id="3cc14-105">Contains an [RFC3282] Content-Class header field value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cc14-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="3cc14-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="3cc14-107">无</span><span class="sxs-lookup"><span data-stu-id="3cc14-107">None</span></span>  <br/> |
|<span data-ttu-id="3cc14-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="3cc14-108">Property set:</span></span>  <br/> |<span data-ttu-id="3cc14-109">PS_INTERNET_HEADERS</span><span class="sxs-lookup"><span data-stu-id="3cc14-109">PS_INTERNET_HEADERS</span></span>  <br/> |
|<span data-ttu-id="3cc14-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="3cc14-110">Property name:</span></span>  <br/> |<span data-ttu-id="3cc14-111">Content-Class</span><span class="sxs-lookup"><span data-stu-id="3cc14-111">Content-Class</span></span>  <br/> |
|<span data-ttu-id="3cc14-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3cc14-112">Data type:</span></span>  <br/> |<span data-ttu-id="3cc14-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3cc14-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3cc14-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3cc14-114">Area:</span></span>  <br/> |<span data-ttu-id="3cc14-115">Email</span><span class="sxs-lookup"><span data-stu-id="3cc14-115">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cc14-116">备注</span><span class="sxs-lookup"><span data-stu-id="3cc14-116">Remarks</span></span>

<span data-ttu-id="3cc14-117">若要设置此属性的值，多用途 Internet 邮件扩展 (MIME) 客户端必须编写内容类标头字段与所需的值。</span><span class="sxs-lookup"><span data-stu-id="3cc14-117">To set the value of this property, Multipurpose Internet Message Extensions (MIME) clients must write a Content-Class header field with the desired value.</span></span> <span data-ttu-id="3cc14-118">MIME 读者必须将内容类标头字段的值复制到此属性的值。</span><span class="sxs-lookup"><span data-stu-id="3cc14-118">MIME readers must copy the value of a Content-Class header field to the value of this property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3cc14-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3cc14-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3cc14-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="3cc14-120">Protocol specifications</span></span>

<span data-ttu-id="3cc14-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cc14-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cc14-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="3cc14-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3cc14-123">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cc14-123">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cc14-124">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="3cc14-124">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="3cc14-125">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cc14-125">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cc14-126">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="3cc14-126">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3cc14-127">头文件</span><span class="sxs-lookup"><span data-stu-id="3cc14-127">Header files</span></span>

<span data-ttu-id="3cc14-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3cc14-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="3cc14-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3cc14-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3cc14-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc14-130">See also</span></span>



[<span data-ttu-id="3cc14-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3cc14-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3cc14-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cc14-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3cc14-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cc14-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3cc14-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cc14-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

