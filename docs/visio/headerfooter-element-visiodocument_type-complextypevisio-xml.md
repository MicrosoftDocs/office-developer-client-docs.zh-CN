---
title: HeaderFooter 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 026926cf-3d0b-984c-897e-9d28346b7ba7
description: 包含文档的页眉和页脚的元素。
ms.openlocfilehash: e5933ad318b8100569046668e3cc372ce9a03788
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780390"
---
# <a name="headerfooter-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="96b1c-103">HeaderFooter 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="96b1c-103">HeaderFooter element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="96b1c-104">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="96b1c-104">Contains elements for a document's header and footer.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="96b1c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="96b1c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="96b1c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="96b1c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="96b1c-107">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-107">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="96b1c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="96b1c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="96b1c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="96b1c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="96b1c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="96b1c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="96b1c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="96b1c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="96b1c-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="96b1c-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="96b1c-113">定义</span><span class="sxs-lookup"><span data-stu-id="96b1c-113">Definition</span></span>

```XML
< xs:element name="HeaderFooter" type="HeaderFooter_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="96b1c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="96b1c-114">Elements and attributes</span></span>

<span data-ttu-id="96b1c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="96b1c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="96b1c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="96b1c-116">Parent elements</span></span>

|<span data-ttu-id="96b1c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="96b1c-117">**Element**</span></span>|<span data-ttu-id="96b1c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="96b1c-118">**Type**</span></span>|<span data-ttu-id="96b1c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="96b1c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="96b1c-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="96b1c-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="96b1c-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="96b1c-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="96b1c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="96b1c-123">Child elements</span></span>

|<span data-ttu-id="96b1c-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="96b1c-124">**Element**</span></span>|<span data-ttu-id="96b1c-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="96b1c-125">**Type**</span></span>|<span data-ttu-id="96b1c-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="96b1c-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="96b1c-127">FooterCenter</span><span class="sxs-lookup"><span data-stu-id="96b1c-127">FooterCenter</span></span>](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-128">FooterCenter_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-128">FooterCenter_Type</span></span>](footercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-129">包含文档页脚的中心部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-129">Contains the text string that appears in the center portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-130">FooterLeft</span><span class="sxs-lookup"><span data-stu-id="96b1c-130">FooterLeft</span></span>](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-131">FooterLeft_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-131">FooterLeft_Type</span></span>](footerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-132">包含的文档的页脚部分中显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-132">Contains the text string that appears in the left portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-133">FooterMargin</span><span class="sxs-lookup"><span data-stu-id="96b1c-133">FooterMargin</span></span>](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-134">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-134">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-135">指定文档的页脚的边距。</span><span class="sxs-lookup"><span data-stu-id="96b1c-135">Specifies the margin of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-136">FooterRight</span><span class="sxs-lookup"><span data-stu-id="96b1c-136">FooterRight</span></span>](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-137">FooterRight_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-137">FooterRight_Type</span></span>](footerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-138">包含文档页脚的右侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-138">Contains the text string that appears in the right portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-139">HeaderCenter</span><span class="sxs-lookup"><span data-stu-id="96b1c-139">HeaderCenter</span></span>](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-140">HeaderCenter_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-140">HeaderCenter_Type</span></span>](headercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-141">包含文档页眉的中心部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-141">Contains the text string that appears in the center portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-142">HeaderFooterFont</span><span class="sxs-lookup"><span data-stu-id="96b1c-142">HeaderFooterFont</span></span>](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-143">HeaderFooterFont_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-143">HeaderFooterFont_Type</span></span>](headerfooterfont_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-144">指定用于页眉和页脚文本的字体。</span><span class="sxs-lookup"><span data-stu-id="96b1c-144">Specifies the font used for the header and footer text.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-145">HeaderLeft</span><span class="sxs-lookup"><span data-stu-id="96b1c-145">HeaderLeft</span></span>](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-146">HeaderLeft_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-146">HeaderLeft_Type</span></span>](headerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-147">包含文档页眉的左侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-147">Contains the text string that appears in the left portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-148">HeaderMargin</span><span class="sxs-lookup"><span data-stu-id="96b1c-148">HeaderMargin</span></span>](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-149">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-149">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-150">指定文档的页眉的边距。</span><span class="sxs-lookup"><span data-stu-id="96b1c-150">Specifies the margin of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="96b1c-151">HeaderRight</span><span class="sxs-lookup"><span data-stu-id="96b1c-151">HeaderRight</span></span>](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="96b1c-152">HeaderRight_Type</span><span class="sxs-lookup"><span data-stu-id="96b1c-152">HeaderRight_Type</span></span>](headerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="96b1c-153">包含文档页眉的右侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="96b1c-153">Contains the text string that appears in the right portion of a document's header.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="96b1c-154">属性</span><span class="sxs-lookup"><span data-stu-id="96b1c-154">Attributes</span></span>

|<span data-ttu-id="96b1c-155">**属性**</span><span class="sxs-lookup"><span data-stu-id="96b1c-155">**Attribute**</span></span>|<span data-ttu-id="96b1c-156">**类型**</span><span class="sxs-lookup"><span data-stu-id="96b1c-156">**Type**</span></span>|<span data-ttu-id="96b1c-157">**必需**</span><span class="sxs-lookup"><span data-stu-id="96b1c-157">**Required**</span></span>|<span data-ttu-id="96b1c-158">**说明**</span><span class="sxs-lookup"><span data-stu-id="96b1c-158">**Description**</span></span>|<span data-ttu-id="96b1c-159">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="96b1c-159">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96b1c-160">HeaderFooterColor</span><span class="sxs-lookup"><span data-stu-id="96b1c-160">HeaderFooterColor</span></span>  <br/> |<span data-ttu-id="96b1c-161">xsd: string</span><span class="sxs-lookup"><span data-stu-id="96b1c-161">xsd:string</span></span>  <br/> |<span data-ttu-id="96b1c-162">可选</span><span class="sxs-lookup"><span data-stu-id="96b1c-162">optional</span></span>  <br/> |<span data-ttu-id="96b1c-163">页眉和页脚以十六进制; 的文本颜色的 RGB 值例如，#rrggbb。</span><span class="sxs-lookup"><span data-stu-id="96b1c-163">The RGB value of the text color for the header and footer in hexadecimal notation; for example, #rrggbb.</span></span>  <br/> |<span data-ttu-id="96b1c-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="96b1c-164">Values of the xsd:string type.</span></span>  <br/> |
   

