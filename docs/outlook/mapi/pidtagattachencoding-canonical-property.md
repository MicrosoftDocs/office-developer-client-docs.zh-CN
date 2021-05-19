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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bda4783012a3a5cd50d9c0aea6a37ccd238b660
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345491"
---
# <a name="pidtagattachencoding-canonical-property"></a><span data-ttu-id="413fa-103">PidTagAttachEncoding 规范属性</span><span class="sxs-lookup"><span data-stu-id="413fa-103">PidTagAttachEncoding Canonical Property</span></span>

  
  
<span data-ttu-id="413fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="413fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="413fa-105">包含指定附件编码的 ASN.1 对象标识符。</span><span class="sxs-lookup"><span data-stu-id="413fa-105">Contains an ASN.1 object identifier that specifies the encoding for an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="413fa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="413fa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="413fa-107">PR_ATTACH_ENCODING</span><span class="sxs-lookup"><span data-stu-id="413fa-107">PR_ATTACH_ENCODING</span></span>  <br/> |
|<span data-ttu-id="413fa-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="413fa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="413fa-109">0x3702</span><span class="sxs-lookup"><span data-stu-id="413fa-109">0x3702</span></span>  <br/> |
|<span data-ttu-id="413fa-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="413fa-110">Data type:</span></span>  <br/> |<span data-ttu-id="413fa-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="413fa-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="413fa-112">区域：</span><span class="sxs-lookup"><span data-stu-id="413fa-112">Area:</span></span>  <br/> |<span data-ttu-id="413fa-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="413fa-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="413fa-114">备注</span><span class="sxs-lookup"><span data-stu-id="413fa-114">Remarks</span></span>

<span data-ttu-id="413fa-115">此属性标识用于转换附件中数据的算法。</span><span class="sxs-lookup"><span data-stu-id="413fa-115">This property identifies the algorithm used to transform the data in an attachment.</span></span>
  
 <span data-ttu-id="413fa-116">**注意** 不应 **混淆 PR_ATTACH_ENCODING** **PR_ATTACH_TAG (** [PidTagAttachTag) 和 PidTagAttachTag](pidtagattachtag-canonical-property.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="413fa-116">**Note** The **PR_ATTACH_ENCODING** and **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) properties should not be confused.</span></span> <span data-ttu-id="413fa-117">它们不配对或相关。</span><span class="sxs-lookup"><span data-stu-id="413fa-117">They are not paired or related.</span></span> <span data-ttu-id="413fa-118">**PR_ATTACH_TAG** 标识最初生成附件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="413fa-118">**PR_ATTACH_TAG** identifies the application that originally generated the attachment.</span></span> <span data-ttu-id="413fa-119">"对象"在术语对象标识符和 X.400 中比在面向对象的编程中具有更为一般的含义。</span><span class="sxs-lookup"><span data-stu-id="413fa-119">"Object" has a much more general meaning in the term object identifier, and in X.400, than in object-oriented programming.</span></span> 
  
<span data-ttu-id="413fa-120">对象标识符语法和示例对象标识符在 MAPIOID 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="413fa-120">The object identifier syntax and sample object identifiers are defined in the MAPIOID.H header file.</span></span> <span data-ttu-id="413fa-121">值 **PR_ATTACH_ENCODING** MAPIOID.H 中定义的值。</span><span class="sxs-lookup"><span data-stu-id="413fa-121">Values for **PR_ATTACH_ENCODING** are not limited to those defined in MAPIOID.H.</span></span> <span data-ttu-id="413fa-122">例如，附加的 Macintosh 文件可以使用标识符（如 MacBinary）。</span><span class="sxs-lookup"><span data-stu-id="413fa-122">For example, attached Macintosh files can use an identifier such as MacBinary.</span></span> 
  
<span data-ttu-id="413fa-123">有关这些对象标识符的完整信息，请参阅有关 ASN.1、X.208 和 X.209 的文档。</span><span class="sxs-lookup"><span data-stu-id="413fa-123">For complete information on these object identifiers, see the documentation on ASN.1, X.208, and X.209.</span></span> <span data-ttu-id="413fa-124">对象标识符位于 FTBP 文件传输正文部分 (应用程序引用) 元素。</span><span class="sxs-lookup"><span data-stu-id="413fa-124">The object identifier is found in the application-reference element of the FTBP (File Transfer Body Part) environment.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="413fa-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="413fa-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="413fa-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="413fa-126">Protocol specifications</span></span>

<span data-ttu-id="413fa-127">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="413fa-127">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="413fa-128">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="413fa-128">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="413fa-129">头文件</span><span class="sxs-lookup"><span data-stu-id="413fa-129">Header files</span></span>

<span data-ttu-id="413fa-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="413fa-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="413fa-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="413fa-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="413fa-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="413fa-132">Mapitags.h</span></span>
  
> <span data-ttu-id="413fa-133">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="413fa-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="413fa-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="413fa-134">See also</span></span>



[<span data-ttu-id="413fa-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="413fa-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="413fa-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="413fa-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="413fa-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="413fa-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="413fa-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="413fa-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

