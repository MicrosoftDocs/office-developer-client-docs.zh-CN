---
title: PidTagAttachEncoding 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachEncoding
api_type:
- HeaderDef
ms.assetid: 3b30cec6-da1e-4ef1-8c17-24b66f31cf0a
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: cdeb432e20f2779bbb625566108551748b48a01f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777349"
---
# <a name="pidtagattachencoding-canonical-property"></a><span data-ttu-id="4b9c1-103">PidTagAttachEncoding 规范属性</span><span class="sxs-lookup"><span data-stu-id="4b9c1-103">PidTagAttachEncoding Canonical Property</span></span>

  
  
<span data-ttu-id="4b9c1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4b9c1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4b9c1-105">包含指定的附件的编码 ASN.1 对象标识符。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-105">Contains an ASN.1 object identifier that specifies the encoding for an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4b9c1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="4b9c1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4b9c1-107">PR_ATTACH_ENCODING</span><span class="sxs-lookup"><span data-stu-id="4b9c1-107">PR_ATTACH_ENCODING</span></span>  <br/> |
|<span data-ttu-id="4b9c1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4b9c1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4b9c1-109">0x3702</span><span class="sxs-lookup"><span data-stu-id="4b9c1-109">0x3702</span></span>  <br/> |
|<span data-ttu-id="4b9c1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4b9c1-110">Data type:</span></span>  <br/> |<span data-ttu-id="4b9c1-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="4b9c1-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="4b9c1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4b9c1-112">Area:</span></span>  <br/> |<span data-ttu-id="4b9c1-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="4b9c1-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4b9c1-114">备注</span><span class="sxs-lookup"><span data-stu-id="4b9c1-114">Remarks</span></span>

<span data-ttu-id="4b9c1-115">此属性标识用于转换附件中的数据的算法。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-115">This property identifies the algorithm used to transform the data in an attachment.</span></span>
  
 <span data-ttu-id="4b9c1-116">**注释**不能混淆**PR_ATTACH_ENCODING**和**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-116">**Note** The **PR_ATTACH_ENCODING** and **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) properties should not be confused.</span></span> <span data-ttu-id="4b9c1-117">它们不是配对或相关。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-117">They are not paired or related.</span></span> <span data-ttu-id="4b9c1-118">**PR_ATTACH_TAG**标识最初生成附件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-118">**PR_ATTACH_TAG** identifies the application that originally generated the attachment.</span></span> <span data-ttu-id="4b9c1-119">在面向对象的编程情况下，"对象"具有比的术语对象标识符，在和中 X.400，更加常规的含义。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-119">"Object" has a much more general meaning in the term object identifier, and in X.400, than in object-oriented programming.</span></span> 
  
<span data-ttu-id="4b9c1-120">MAPIOID 中定义的对象标识符语法和示例对象标识符。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-120">The object identifier syntax and sample object identifiers are defined in the MAPIOID.H header file.</span></span> <span data-ttu-id="4b9c1-121">**PR_ATTACH_ENCODING**值不限于 MAPIOID 中定义的值。H。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-121">Values for **PR_ATTACH_ENCODING** are not limited to those defined in MAPIOID.H.</span></span> <span data-ttu-id="4b9c1-122">例如，Macintosh 附件可以使用如 MacBinary 标识符。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-122">For example, attached Macintosh files can use an identifier such as MacBinary.</span></span> 
  
<span data-ttu-id="4b9c1-123">有关这些对象标识符的完整信息，请参阅 ASN.1、 X.208 和 X.209 上的文档。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-123">For complete information on these object identifiers, see the documentation on ASN.1, X.208, and X.209.</span></span> <span data-ttu-id="4b9c1-124">FTBP （文件传输正文部分） 环境的应用程序引用元素中找到对象标识符。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-124">The object identifier is found in the application-reference element of the FTBP (File Transfer Body Part) environment.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4b9c1-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="4b9c1-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4b9c1-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="4b9c1-126">Protocol specifications</span></span>

<span data-ttu-id="4b9c1-127">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4b9c1-127">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4b9c1-128">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-128">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4b9c1-129">头文件</span><span class="sxs-lookup"><span data-stu-id="4b9c1-129">Header files</span></span>

<span data-ttu-id="4b9c1-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4b9c1-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="4b9c1-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="4b9c1-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4b9c1-132">Mapitags.h</span></span>
  
> <span data-ttu-id="4b9c1-133">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4b9c1-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4b9c1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b9c1-134">See also</span></span>



[<span data-ttu-id="4b9c1-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4b9c1-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4b9c1-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4b9c1-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4b9c1-137">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4b9c1-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4b9c1-138">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4b9c1-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

