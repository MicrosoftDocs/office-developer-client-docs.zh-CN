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
# <a name="headerfooter-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="dbccc-103">HeaderFooter 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="dbccc-103">HeaderFooter element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="dbccc-104">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="dbccc-104">Contains elements for a document's header and footer.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="dbccc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="dbccc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dbccc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="dbccc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="dbccc-107">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-107">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="dbccc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="dbccc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="dbccc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="dbccc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="dbccc-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="dbccc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="dbccc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="dbccc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="dbccc-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="dbccc-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="dbccc-113">定义</span><span class="sxs-lookup"><span data-stu-id="dbccc-113">Definition</span></span>

```XML
< xs:element name="HeaderFooter" type="HeaderFooter_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="dbccc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="dbccc-114">Elements and attributes</span></span>

<span data-ttu-id="dbccc-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="dbccc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="dbccc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="dbccc-116">Parent elements</span></span>

|<span data-ttu-id="dbccc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="dbccc-117">**Element**</span></span>|<span data-ttu-id="dbccc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="dbccc-118">**Type**</span></span>|<span data-ttu-id="dbccc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbccc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="dbccc-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="dbccc-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="dbccc-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="dbccc-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="dbccc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="dbccc-123">Child elements</span></span>

|<span data-ttu-id="dbccc-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="dbccc-124">**Element**</span></span>|<span data-ttu-id="dbccc-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="dbccc-125">**Type**</span></span>|<span data-ttu-id="dbccc-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbccc-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="dbccc-127">FooterCenter</span><span class="sxs-lookup"><span data-stu-id="dbccc-127">FooterCenter</span></span>](footercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-128">FooterCenter_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-128">FooterCenter_Type</span></span>](footercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-129">包含文档页脚的中心部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-129">Contains the text string that appears in the center portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-130">FooterLeft</span><span class="sxs-lookup"><span data-stu-id="dbccc-130">FooterLeft</span></span>](footerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-131">FooterLeft_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-131">FooterLeft_Type</span></span>](footerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-132">包含的文档的页脚部分中显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-132">Contains the text string that appears in the left portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-133">FooterMargin</span><span class="sxs-lookup"><span data-stu-id="dbccc-133">FooterMargin</span></span>](footermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-134">FooterMargin_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-134">FooterMargin_Type</span></span>](footermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-135">指定文档的页脚的边距。</span><span class="sxs-lookup"><span data-stu-id="dbccc-135">Specifies the margin of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-136">FooterRight</span><span class="sxs-lookup"><span data-stu-id="dbccc-136">FooterRight</span></span>](footerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-137">FooterRight_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-137">FooterRight_Type</span></span>](footerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-138">包含文档页脚的右侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-138">Contains the text string that appears in the right portion of a document's footer.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-139">HeaderCenter</span><span class="sxs-lookup"><span data-stu-id="dbccc-139">HeaderCenter</span></span>](headercenter-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-140">HeaderCenter_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-140">HeaderCenter_Type</span></span>](headercenter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-141">包含文档页眉的中心部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-141">Contains the text string that appears in the center portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-142">HeaderFooterFont</span><span class="sxs-lookup"><span data-stu-id="dbccc-142">HeaderFooterFont</span></span>](headerfooterfont-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-143">HeaderFooterFont_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-143">HeaderFooterFont_Type</span></span>](headerfooterfont_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-144">指定用于页眉和页脚文本的字体。</span><span class="sxs-lookup"><span data-stu-id="dbccc-144">Specifies the font used for the header and footer text.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-145">HeaderLeft</span><span class="sxs-lookup"><span data-stu-id="dbccc-145">HeaderLeft</span></span>](headerleft-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-146">HeaderLeft_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-146">HeaderLeft_Type</span></span>](headerleft_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-147">包含文档页眉的左侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-147">Contains the text string that appears in the left portion of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-148">HeaderMargin</span><span class="sxs-lookup"><span data-stu-id="dbccc-148">HeaderMargin</span></span>](headermargin-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-149">HeaderMargin_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-149">HeaderMargin_Type</span></span>](headermargin_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-150">指定文档的页眉的边距。</span><span class="sxs-lookup"><span data-stu-id="dbccc-150">Specifies the margin of a document's header.</span></span>  <br/> |
|[<span data-ttu-id="dbccc-151">HeaderRight</span><span class="sxs-lookup"><span data-stu-id="dbccc-151">HeaderRight</span></span>](headerright-element-headerfooter_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dbccc-152">HeaderRight_Type</span><span class="sxs-lookup"><span data-stu-id="dbccc-152">HeaderRight_Type</span></span>](headerright_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="dbccc-153">包含文档页眉的右侧部分显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="dbccc-153">Contains the text string that appears in the right portion of a document's header.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="dbccc-154">Attributes</span><span class="sxs-lookup"><span data-stu-id="dbccc-154">Attributes</span></span>

|<span data-ttu-id="dbccc-155">**属性**</span><span class="sxs-lookup"><span data-stu-id="dbccc-155">**Attribute**</span></span>|<span data-ttu-id="dbccc-156">**类型**</span><span class="sxs-lookup"><span data-stu-id="dbccc-156">**Type**</span></span>|<span data-ttu-id="dbccc-157">**必需**</span><span class="sxs-lookup"><span data-stu-id="dbccc-157">**Required**</span></span>|<span data-ttu-id="dbccc-158">**说明**</span><span class="sxs-lookup"><span data-stu-id="dbccc-158">**Description**</span></span>|<span data-ttu-id="dbccc-159">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="dbccc-159">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dbccc-160">HeaderFooterColor</span><span class="sxs-lookup"><span data-stu-id="dbccc-160">HeaderFooterColor</span></span>  <br/> |<span data-ttu-id="dbccc-161">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dbccc-161">xsd:string</span></span>  <br/> |<span data-ttu-id="dbccc-162">可选</span><span class="sxs-lookup"><span data-stu-id="dbccc-162">optional</span></span>  <br/> |<span data-ttu-id="dbccc-163">页眉和页脚以十六进制; 的文本颜色的 RGB 值例如，#rrggbb。</span><span class="sxs-lookup"><span data-stu-id="dbccc-163">The RGB value of the text color for the header and footer in hexadecimal notation; for example, #rrggbb.</span></span>  <br/> |<span data-ttu-id="dbccc-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dbccc-164">Values of the xsd:string type.</span></span>  <br/> |
   

