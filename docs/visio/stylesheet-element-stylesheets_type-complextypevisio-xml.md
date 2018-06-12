---
title: 样式表元素 （StyleSheets_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: 2513c7421dc8f890b7ba63f19cf3d31d23ce65ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781463"
---
# <a name="stylesheet-element-stylesheetstype-complextype-visio-xml"></a><span data-ttu-id="5b749-103">样式表元素 （StyleSheets_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5b749-103">StyleSheet element (StyleSheets_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="5b749-104">表示在文档中定义的样式。</span><span class="sxs-lookup"><span data-stu-id="5b749-104">Represents a style defined in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5b749-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5b749-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5b749-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5b749-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5b749-107">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="5b749-107">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5b749-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5b749-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5b749-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5b749-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5b749-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5b749-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5b749-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5b749-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5b749-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="5b749-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5b749-113">定义</span><span class="sxs-lookup"><span data-stu-id="5b749-113">Definition</span></span>

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5b749-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5b749-114">Elements and attributes</span></span>

<span data-ttu-id="5b749-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5b749-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5b749-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5b749-116">Parent elements</span></span>

|<span data-ttu-id="5b749-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5b749-117">**Element**</span></span>|<span data-ttu-id="5b749-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b749-118">**Type**</span></span>|<span data-ttu-id="5b749-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b749-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5b749-120">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="5b749-120">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5b749-121">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="5b749-121">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5b749-122">包含文档的**样式表**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="5b749-122">Contains a collection of **StyleSheet** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5b749-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5b749-123">Child elements</span></span>

|<span data-ttu-id="5b749-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="5b749-124">**Element**</span></span>|<span data-ttu-id="5b749-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b749-125">**Type**</span></span>|<span data-ttu-id="5b749-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b749-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5b749-127">Cell</span><span class="sxs-lookup"><span data-stu-id="5b749-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="5b749-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="5b749-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5b749-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="5b749-129">Specifies a single property.</span></span>  <br/> |
|[<span data-ttu-id="5b749-130">节</span><span class="sxs-lookup"><span data-stu-id="5b749-130">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5b749-131">Section_Type</span><span class="sxs-lookup"><span data-stu-id="5b749-131">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5b749-132">指定相关的属性的集合。</span><span class="sxs-lookup"><span data-stu-id="5b749-132">Specifies a collection of related properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="5b749-133">属性</span><span class="sxs-lookup"><span data-stu-id="5b749-133">Attributes</span></span>

|<span data-ttu-id="5b749-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="5b749-134">**Attribute**</span></span>|<span data-ttu-id="5b749-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b749-135">**Type**</span></span>|<span data-ttu-id="5b749-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="5b749-136">**Required**</span></span>|<span data-ttu-id="5b749-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b749-137">**Description**</span></span>|<span data-ttu-id="5b749-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5b749-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5b749-139">FillStyle</span><span class="sxs-lookup"><span data-stu-id="5b749-139">FillStyle</span></span>  <br/> |<span data-ttu-id="5b749-140">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5b749-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5b749-141">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-141">optional</span></span>  <br/> |<span data-ttu-id="5b749-142">从中此样式继承填充格式样式表元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="5b749-142">The ID of the StyleSheet element from which this style inherits fill formatting.</span></span>  <br/> |<span data-ttu-id="5b749-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5b749-144">ID</span><span class="sxs-lookup"><span data-stu-id="5b749-144">ID</span></span>  <br/> |<span data-ttu-id="5b749-145">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5b749-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5b749-146">必需</span><span class="sxs-lookup"><span data-stu-id="5b749-146">required</span></span>  <br/> |<span data-ttu-id="5b749-147">其父元素中的元素的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5b749-147">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="5b749-148">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5b749-149">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="5b749-149">IsCustomName</span></span>  <br/> |<span data-ttu-id="5b749-150">化</span><span class="sxs-lookup"><span data-stu-id="5b749-150">xsd:boolean</span></span>  <br/> |<span data-ttu-id="5b749-151">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-151">optional</span></span>  <br/> |<span data-ttu-id="5b749-152">指示是否由用户自定义名称。</span><span class="sxs-lookup"><span data-stu-id="5b749-152">Indicates whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="5b749-153">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-153">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="5b749-154">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="5b749-154">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="5b749-155">化</span><span class="sxs-lookup"><span data-stu-id="5b749-155">xsd:boolean</span></span>  <br/> |<span data-ttu-id="5b749-156">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-156">optional</span></span>  <br/> |<span data-ttu-id="5b749-157">指示是否由用户自定义的通用名称。</span><span class="sxs-lookup"><span data-stu-id="5b749-157">Indicates whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="5b749-158">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-158">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="5b749-159">LineStyle</span><span class="sxs-lookup"><span data-stu-id="5b749-159">LineStyle</span></span>  <br/> |<span data-ttu-id="5b749-160">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5b749-160">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5b749-161">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-161">optional</span></span>  <br/> |<span data-ttu-id="5b749-162">从中此样式继承线条格式样式表元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="5b749-162">The ID of the StyleSheet element from which this style inherits line formatting.</span></span>  <br/> |<span data-ttu-id="5b749-163">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5b749-164">名称</span><span class="sxs-lookup"><span data-stu-id="5b749-164">Name</span></span>  <br/> |<span data-ttu-id="5b749-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5b749-165">xsd:string</span></span>  <br/> |<span data-ttu-id="5b749-166">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-166">optional</span></span>  <br/> |<span data-ttu-id="5b749-167">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="5b749-167">The name of the element.</span></span>  <br/> |<span data-ttu-id="5b749-168">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-168">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5b749-169">NameU</span><span class="sxs-lookup"><span data-stu-id="5b749-169">NameU</span></span>  <br/> |<span data-ttu-id="5b749-170">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5b749-170">xsd:string</span></span>  <br/> |<span data-ttu-id="5b749-171">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-171">optional</span></span>  <br/> |<span data-ttu-id="5b749-172">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="5b749-172">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="5b749-173">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-173">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5b749-174">TextStyle</span><span class="sxs-lookup"><span data-stu-id="5b749-174">TextStyle</span></span>  <br/> |<span data-ttu-id="5b749-175">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5b749-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5b749-176">可选</span><span class="sxs-lookup"><span data-stu-id="5b749-176">optional</span></span>  <br/> |<span data-ttu-id="5b749-177">从中此样式继承文本格式样式表元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="5b749-177">The ID of the StyleSheet element from which this style inherits text formatting.</span></span>  <br/> |<span data-ttu-id="5b749-178">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5b749-178">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

