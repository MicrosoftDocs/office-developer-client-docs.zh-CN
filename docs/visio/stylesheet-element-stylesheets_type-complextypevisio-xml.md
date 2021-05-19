---
title: 'StyleSheet 元素 (StyleSheets_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: 939180d24972ae68d01b2a707e7806380b706d14
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541937"
---
# <a name="stylesheet-element-stylesheets_type-complextype-visio-xml"></a><span data-ttu-id="f12c8-103">StyleSheet 元素 (StyleSheets_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="f12c8-103">StyleSheet element (StyleSheets_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="f12c8-104">表示在文档中定义的样式。</span><span class="sxs-lookup"><span data-stu-id="f12c8-104">Represents a style defined in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f12c8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f12c8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f12c8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f12c8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f12c8-107">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="f12c8-107">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f12c8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f12c8-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f12c8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f12c8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f12c8-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f12c8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f12c8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f12c8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f12c8-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="f12c8-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f12c8-113">定义</span><span class="sxs-lookup"><span data-stu-id="f12c8-113">Definition</span></span>

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f12c8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f12c8-114">Elements and attributes</span></span>

<span data-ttu-id="f12c8-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f12c8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f12c8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f12c8-116">Parent elements</span></span>

|<span data-ttu-id="f12c8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f12c8-117">**Element**</span></span>|<span data-ttu-id="f12c8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f12c8-118">**Type**</span></span>|<span data-ttu-id="f12c8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f12c8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f12c8-120">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="f12c8-120">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f12c8-121">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="f12c8-121">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f12c8-122">包含文档的 **StyleSheet** 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f12c8-122">Contains a collection of **StyleSheet** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f12c8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f12c8-123">Child elements</span></span>

|<span data-ttu-id="f12c8-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f12c8-124">**Element**</span></span>|<span data-ttu-id="f12c8-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f12c8-125">**Type**</span></span>|<span data-ttu-id="f12c8-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f12c8-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f12c8-127">Cell</span><span class="sxs-lookup"><span data-stu-id="f12c8-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="f12c8-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f12c8-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f12c8-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="f12c8-129">Specifies a single property.</span></span>  <br/> |
|[<span data-ttu-id="f12c8-130">Section</span><span class="sxs-lookup"><span data-stu-id="f12c8-130">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f12c8-131">Section_Type</span><span class="sxs-lookup"><span data-stu-id="f12c8-131">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f12c8-132">指定相关属性的集合。</span><span class="sxs-lookup"><span data-stu-id="f12c8-132">Specifies a collection of related properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f12c8-133">属性</span><span class="sxs-lookup"><span data-stu-id="f12c8-133">Attributes</span></span>

|<span data-ttu-id="f12c8-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="f12c8-134">**Attribute**</span></span>|<span data-ttu-id="f12c8-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="f12c8-135">**Type**</span></span>|<span data-ttu-id="f12c8-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="f12c8-136">**Required**</span></span>|<span data-ttu-id="f12c8-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="f12c8-137">**Description**</span></span>|<span data-ttu-id="f12c8-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f12c8-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f12c8-139">FillStyle</span><span class="sxs-lookup"><span data-stu-id="f12c8-139">FillStyle</span></span>  <br/> |<span data-ttu-id="f12c8-140">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f12c8-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f12c8-141">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-141">optional</span></span>  <br/> |<span data-ttu-id="f12c8-142">样式从其继承填充格式的 StyleSheet 元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="f12c8-142">The ID of the StyleSheet element from which this style inherits fill formatting.</span></span>  <br/> |<span data-ttu-id="f12c8-143">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-144">ID</span><span class="sxs-lookup"><span data-stu-id="f12c8-144">ID</span></span>  <br/> |<span data-ttu-id="f12c8-145">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f12c8-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f12c8-146">必需</span><span class="sxs-lookup"><span data-stu-id="f12c8-146">required</span></span>  <br/> |<span data-ttu-id="f12c8-147">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f12c8-147">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="f12c8-148">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-149">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="f12c8-149">IsCustomName</span></span>  <br/> |<span data-ttu-id="f12c8-150">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="f12c8-150">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f12c8-151">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-151">optional</span></span>  <br/> |<span data-ttu-id="f12c8-152">指示用户是否已自定义该名称。</span><span class="sxs-lookup"><span data-stu-id="f12c8-152">Indicates whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="f12c8-153">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-153">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-154">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="f12c8-154">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="f12c8-155">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="f12c8-155">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f12c8-156">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-156">optional</span></span>  <br/> |<span data-ttu-id="f12c8-157">指示用户是否已自定义通用名称。</span><span class="sxs-lookup"><span data-stu-id="f12c8-157">Indicates whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="f12c8-158">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-158">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-159">LineStyle</span><span class="sxs-lookup"><span data-stu-id="f12c8-159">LineStyle</span></span>  <br/> |<span data-ttu-id="f12c8-160">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f12c8-160">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f12c8-161">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-161">optional</span></span>  <br/> |<span data-ttu-id="f12c8-162">样式继承线条格式的 StyleSheet 元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="f12c8-162">The ID of the StyleSheet element from which this style inherits line formatting.</span></span>  <br/> |<span data-ttu-id="f12c8-163">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-164">名称</span><span class="sxs-lookup"><span data-stu-id="f12c8-164">Name</span></span>  <br/> |<span data-ttu-id="f12c8-165">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f12c8-165">xsd:string</span></span>  <br/> |<span data-ttu-id="f12c8-166">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-166">optional</span></span>  <br/> |<span data-ttu-id="f12c8-167">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="f12c8-167">The name of the element.</span></span>  <br/> |<span data-ttu-id="f12c8-168">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-168">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-169">NameU</span><span class="sxs-lookup"><span data-stu-id="f12c8-169">NameU</span></span>  <br/> |<span data-ttu-id="f12c8-170">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f12c8-170">xsd:string</span></span>  <br/> |<span data-ttu-id="f12c8-171">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-171">optional</span></span>  <br/> |<span data-ttu-id="f12c8-172">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="f12c8-172">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="f12c8-173">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-173">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f12c8-174">TextStyle</span><span class="sxs-lookup"><span data-stu-id="f12c8-174">TextStyle</span></span>  <br/> |<span data-ttu-id="f12c8-175">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f12c8-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f12c8-176">可选</span><span class="sxs-lookup"><span data-stu-id="f12c8-176">optional</span></span>  <br/> |<span data-ttu-id="f12c8-177">样式从其继承文本格式的 StyleSheet 元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="f12c8-177">The ID of the StyleSheet element from which this style inherits text formatting.</span></span>  <br/> |<span data-ttu-id="f12c8-178">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f12c8-178">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

