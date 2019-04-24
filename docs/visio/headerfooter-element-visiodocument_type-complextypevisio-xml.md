---
title: HeaderFooter 元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 026926cf-3d0b-984c-897e-9d28346b7ba7
description: 包含文档的页眉和页脚的元素。
ms.openlocfilehash: eabb19100c4b37a546c0a271cfba5a0c865a7e83
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319023"
---
# <a name="headerfooter-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="1978b-103">HeaderFooter 元素 (VisioDocument_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="1978b-103">HeaderFooter element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="1978b-104">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="1978b-104">Contains elements for a document's header and footer.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="1978b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="1978b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1978b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="1978b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="1978b-107">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-107">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="1978b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1978b-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="1978b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1978b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="1978b-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="1978b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="1978b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="1978b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="1978b-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="1978b-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1978b-113">定义</span><span class="sxs-lookup"><span data-stu-id="1978b-113">Definition</span></span>

```XML
< xs:element name="HeaderFooter" type="HeaderFooter_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1978b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1978b-114">Elements and attributes</span></span>

<span data-ttu-id="1978b-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1978b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="1978b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="1978b-116">Parent elements</span></span>

|<span data-ttu-id="1978b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="1978b-117">**Element**</span></span>|<span data-ttu-id="1978b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="1978b-118">**Type**</span></span>|<span data-ttu-id="1978b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="1978b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1978b-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="1978b-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="1978b-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="1978b-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="1978b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="1978b-123">Child elements</span></span>

|<span data-ttu-id="1978b-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="1978b-124">**Element**</span></span>|<span data-ttu-id="1978b-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="1978b-125">**Type**</span></span>|<span data-ttu-id="1978b-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="1978b-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1978b-127">FooterCenter</span><span class="sxs-lookup"><span data-stu-id="1978b-127">FooterCenter</span></span>](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-128">FooterCenter_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-128">FooterCenter_Type</span></span>](footercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-129">包含显示在文档页脚中间部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-129">Contains the text string that appears in the center portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="1978b-130">FooterLeft</span><span class="sxs-lookup"><span data-stu-id="1978b-130">FooterLeft</span></span>](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-131">FooterLeft_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-131">FooterLeft_Type</span></span>](footerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-132">包含显示在文档页脚左侧部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-132">Contains the text string that appears in the left portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="1978b-133">FooterMargin</span><span class="sxs-lookup"><span data-stu-id="1978b-133">FooterMargin</span></span>](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-134">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-134">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-135">指定文档页脚的边距。</span><span class="sxs-lookup"><span data-stu-id="1978b-135">Specifies the margin of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="1978b-136">FooterRight</span><span class="sxs-lookup"><span data-stu-id="1978b-136">FooterRight</span></span>](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-137">FooterRight_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-137">FooterRight_Type</span></span>](footerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-138">包含显示在文档页脚右侧部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-138">Contains the text string that appears in the right portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="1978b-139">HeaderCenter</span><span class="sxs-lookup"><span data-stu-id="1978b-139">HeaderCenter</span></span>](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-140">HeaderCenter_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-140">HeaderCenter_Type</span></span>](headercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-141">包含显示在文档页眉中心部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-141">Contains the text string that appears in the center portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="1978b-142">HeaderFooterFont</span><span class="sxs-lookup"><span data-stu-id="1978b-142">HeaderFooterFont</span></span>](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-143">HeaderFooterFont_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-143">HeaderFooterFont_Type</span></span>](headerfooterfont_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-144">指定用于页眉和页脚文本的字体。</span><span class="sxs-lookup"><span data-stu-id="1978b-144">Specifies the font used for the header and footer text.</span></span>  <br/> |
|[<span data-ttu-id="1978b-145">HeaderLeft</span><span class="sxs-lookup"><span data-stu-id="1978b-145">HeaderLeft</span></span>](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-146">HeaderLeft_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-146">HeaderLeft_Type</span></span>](headerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-147">包含显示在文档页眉左侧部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-147">Contains the text string that appears in the left portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="1978b-148">HeaderMargin</span><span class="sxs-lookup"><span data-stu-id="1978b-148">HeaderMargin</span></span>](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-149">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-149">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-150">指定文档页眉的边距。</span><span class="sxs-lookup"><span data-stu-id="1978b-150">Specifies the margin of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="1978b-151">HeaderRight</span><span class="sxs-lookup"><span data-stu-id="1978b-151">HeaderRight</span></span>](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1978b-152">HeaderRight_Type</span><span class="sxs-lookup"><span data-stu-id="1978b-152">HeaderRight_Type</span></span>](headerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="1978b-153">包含显示在文档页眉右侧部分的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="1978b-153">Contains the text string that appears in the right portion of a document's header.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="1978b-154">属性</span><span class="sxs-lookup"><span data-stu-id="1978b-154">Attributes</span></span>

|<span data-ttu-id="1978b-155">**属性**</span><span class="sxs-lookup"><span data-stu-id="1978b-155">**Attribute**</span></span>|<span data-ttu-id="1978b-156">**类型**</span><span class="sxs-lookup"><span data-stu-id="1978b-156">**Type**</span></span>|<span data-ttu-id="1978b-157">**必需**</span><span class="sxs-lookup"><span data-stu-id="1978b-157">**Required**</span></span>|<span data-ttu-id="1978b-158">**描述**</span><span class="sxs-lookup"><span data-stu-id="1978b-158">**Description**</span></span>|<span data-ttu-id="1978b-159">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1978b-159">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1978b-160">HeaderFooterColor</span><span class="sxs-lookup"><span data-stu-id="1978b-160">HeaderFooterColor</span></span>  <br/> |<span data-ttu-id="1978b-161">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1978b-161">xsd:string</span></span>  <br/> |<span data-ttu-id="1978b-162">可选</span><span class="sxs-lookup"><span data-stu-id="1978b-162">optional</span></span>  <br/> |<span data-ttu-id="1978b-163">以十六进制表示法表示的页眉和页脚的文本颜色的 RGB 值。例如, #rrggbb。</span><span class="sxs-lookup"><span data-stu-id="1978b-163">The RGB value of the text color for the header and footer in hexadecimal notation; for example, #rrggbb.</span></span>  <br/> |<span data-ttu-id="1978b-164">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1978b-164">Values of the xsd:string type.</span></span>  <br/> |
   

