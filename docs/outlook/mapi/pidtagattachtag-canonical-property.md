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
ms.openlocfilehash: 5a908b3543dff5cf011c9bd4d5d05b3a07004ead
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361080"
---
# <a name="pidtagattachtag-canonical-property"></a><span data-ttu-id="c20f2-103">PidTagAttachTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="c20f2-103">PidTagAttachTag Canonical Property</span></span>

  
  
<span data-ttu-id="c20f2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c20f2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c20f2-105">包含指定提供附件的应用程序的 ASN.1 对象标识符。</span><span class="sxs-lookup"><span data-stu-id="c20f2-105">Contains an ASN.1 object identifier specifying the application that supplied an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c20f2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c20f2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c20f2-107">PR_ATTACH_TAG</span><span class="sxs-lookup"><span data-stu-id="c20f2-107">PR_ATTACH_TAG</span></span>  <br/> |
|<span data-ttu-id="c20f2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c20f2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c20f2-109">0x370A</span><span class="sxs-lookup"><span data-stu-id="c20f2-109">0x370A</span></span>  <br/> |
|<span data-ttu-id="c20f2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c20f2-110">Data type:</span></span>  <br/> |<span data-ttu-id="c20f2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="c20f2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="c20f2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c20f2-112">Area:</span></span>  <br/> |<span data-ttu-id="c20f2-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="c20f2-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c20f2-114">备注</span><span class="sxs-lookup"><span data-stu-id="c20f2-114">Remarks</span></span>

<span data-ttu-id="c20f2-115">此属性标识最初生成附件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c20f2-115">This property identifies the application that originally generated the attachment.</span></span>
  
 <span data-ttu-id="c20f2-116">**注意** 不应 **PR_ATTACH_ENCODING (** [PidTagAttachEncoding) PR_ATTACH_TAG PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)属性。 </span><span class="sxs-lookup"><span data-stu-id="c20f2-116">**Note** The **PR_ATTACH_ENCODING** ([PidTagAttachEncoding](pidtagattachencoding-canonical-property.md)) and **PR_ATTACH_TAG** properties should not be confused.</span></span> <span data-ttu-id="c20f2-117">它们不配对或相关。</span><span class="sxs-lookup"><span data-stu-id="c20f2-117">They are not paired or related.</span></span> <span data-ttu-id="c20f2-118">**PR_ATTACH_ENCODING** 标识用于转换附件中数据的算法。</span><span class="sxs-lookup"><span data-stu-id="c20f2-118">**PR_ATTACH_ENCODING** identifies the algorithm used to transform the data in an attachment.</span></span> <span data-ttu-id="c20f2-119">"对象"在术语对象标识符和 X.400 用法中比在面向对象的编程中具有更为一般的含义。</span><span class="sxs-lookup"><span data-stu-id="c20f2-119">"Object" has a much more general meaning in the term object identifier, and in X.400 usage, than in object-oriented programming.</span></span> 
  
<span data-ttu-id="c20f2-120">对象标识符语法和示例对象标识符在 MAPIOID 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="c20f2-120">The object identifier syntax and sample object identifiers are defined in the MAPIOID.H header file.</span></span> <span data-ttu-id="c20f2-121">值 **PR_ATTACH_TAG** MAPIOID.H 中定义的值。</span><span class="sxs-lookup"><span data-stu-id="c20f2-121">Values for **PR_ATTACH_TAG** are not limited to those defined in MAPIOID.H.</span></span> 
  
<span data-ttu-id="c20f2-122">有关这些对象标识符的完整信息，请参阅有关 ASN.1、X.208 和 X.209 的文档。</span><span class="sxs-lookup"><span data-stu-id="c20f2-122">For complete information on these object identifiers, see the documentation on ASN.1, X.208, and X.209.</span></span> <span data-ttu-id="c20f2-123">对象标识符位于 FTBP 环境的文件传输正文部件的应用程序 (元素) 元素。</span><span class="sxs-lookup"><span data-stu-id="c20f2-123">The object identifier is found in the application-reference element of the File Transfer Body Part (FTBP) environment.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c20f2-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="c20f2-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c20f2-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="c20f2-125">Protocol specifications</span></span>

<span data-ttu-id="c20f2-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c20f2-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c20f2-127">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="c20f2-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c20f2-128">头文件</span><span class="sxs-lookup"><span data-stu-id="c20f2-128">Header files</span></span>

<span data-ttu-id="c20f2-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c20f2-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="c20f2-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c20f2-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="c20f2-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c20f2-131">Mapitags.h</span></span>
  
> <span data-ttu-id="c20f2-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c20f2-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c20f2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c20f2-133">See also</span></span>



[<span data-ttu-id="c20f2-134">PidTagAttachMimeTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="c20f2-134">PidTagAttachMimeTag Canonical Property</span></span>](pidtagattachmimetag-canonical-property.md)


[<span data-ttu-id="c20f2-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c20f2-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c20f2-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c20f2-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c20f2-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c20f2-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c20f2-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c20f2-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

