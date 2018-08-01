---
title: PidTagAttachTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachTag
api_type:
- HeaderDef
ms.assetid: 3d223809-b697-47c6-bc3c-2206aff7ad33
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d8d8d32bddb98e0ac180b0898478c67297980492
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777386"
---
# <a name="pidtagattachtag-canonical-property"></a><span data-ttu-id="346df-103">PidTagAttachTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="346df-103">PidTagAttachTag Canonical Property</span></span>

  
  
<span data-ttu-id="346df-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="346df-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="346df-105">包含指定的应用程序提供附件 ASN.1 对象标识符。</span><span class="sxs-lookup"><span data-stu-id="346df-105">Contains an ASN.1 object identifier specifying the application that supplied an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="346df-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="346df-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="346df-107">PR_ATTACH_TAG</span><span class="sxs-lookup"><span data-stu-id="346df-107">PR_ATTACH_TAG</span></span>  <br/> |
|<span data-ttu-id="346df-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="346df-108">Identifier:</span></span>  <br/> |<span data-ttu-id="346df-109">0x370A</span><span class="sxs-lookup"><span data-stu-id="346df-109">0x370A</span></span>  <br/> |
|<span data-ttu-id="346df-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="346df-110">Data type:</span></span>  <br/> |<span data-ttu-id="346df-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="346df-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="346df-112">区域：</span><span class="sxs-lookup"><span data-stu-id="346df-112">Area:</span></span>  <br/> |<span data-ttu-id="346df-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="346df-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="346df-114">说明</span><span class="sxs-lookup"><span data-stu-id="346df-114">Remarks</span></span>

<span data-ttu-id="346df-115">此属性标识最初生成附件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="346df-115">This property identifies the application that originally generated the attachment.</span></span>
  
 <span data-ttu-id="346df-116">**注释**不能混淆**PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) 和**PR_ATTACH_TAG**属性。</span><span class="sxs-lookup"><span data-stu-id="346df-116">**Note** The **PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) and **PR_ATTACH_TAG** properties should not be confused.</span></span> <span data-ttu-id="346df-117">它们不是配对或相关。</span><span class="sxs-lookup"><span data-stu-id="346df-117">They are not paired or related.</span></span> <span data-ttu-id="346df-118">**PR_ATTACH_ENCODING**标识用于转换附件中的数据的算法。</span><span class="sxs-lookup"><span data-stu-id="346df-118">**PR_ATTACH_ENCODING** identifies the algorithm used to transform the data in an attachment.</span></span> <span data-ttu-id="346df-119">"对象"具有更常规的含义和 X.400 使用率中的术语对象标识符，比在面向对象的编程。</span><span class="sxs-lookup"><span data-stu-id="346df-119">"Object" has a much more general meaning in the term object identifier, and in X.400 usage, than in object-oriented programming.</span></span> 
  
<span data-ttu-id="346df-120">MAPIOID 中定义的对象标识符语法和示例对象标识符。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="346df-120">The object identifier syntax and sample object identifiers are defined in the MAPIOID.H header file.</span></span> <span data-ttu-id="346df-121">**PR_ATTACH_TAG**值不限于 MAPIOID 中定义的值。H。</span><span class="sxs-lookup"><span data-stu-id="346df-121">Values for **PR_ATTACH_TAG** are not limited to those defined in MAPIOID.H.</span></span> 
  
<span data-ttu-id="346df-122">有关这些对象标识符的完整信息，请参阅 ASN.1、 X.208 和 X.209 上的文档。</span><span class="sxs-lookup"><span data-stu-id="346df-122">For complete information on these object identifiers, see the documentation on ASN.1, X.208, and X.209.</span></span> <span data-ttu-id="346df-123">文件传输正文部分 (FTBP) 环境的应用程序引用元素中找到对象标识符。</span><span class="sxs-lookup"><span data-stu-id="346df-123">The object identifier is found in the application-reference element of the File Transfer Body Part (FTBP) environment.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="346df-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="346df-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="346df-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="346df-125">Protocol specifications</span></span>

<span data-ttu-id="346df-126">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="346df-126">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="346df-127">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="346df-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="346df-128">头文件</span><span class="sxs-lookup"><span data-stu-id="346df-128">Header files</span></span>

<span data-ttu-id="346df-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="346df-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="346df-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="346df-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="346df-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="346df-131">Mapitags.h</span></span>
  
> <span data-ttu-id="346df-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="346df-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="346df-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="346df-133">See also</span></span>



[<span data-ttu-id="346df-134">PidTagAttachMimeTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="346df-134">PidTagAttachMimeTag Canonical Property</span></span>](pidtagattachmimetag-canonical-property.md)


[<span data-ttu-id="346df-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="346df-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="346df-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="346df-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="346df-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="346df-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="346df-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="346df-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

