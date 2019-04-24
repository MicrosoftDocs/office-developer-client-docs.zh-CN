---
title: StyleSheet 元素 (StyleSheets_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 323e1ccd-8ddd-46d3-1032-5d68d01cf4bd
description: 表示在文档中定义的样式。
ms.openlocfilehash: af1f8270be28e7edabf22d93471517531f5cc226
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329797"
---
# <a name="stylesheet-element-stylesheetstype-complextype-visio-xml"></a><span data-ttu-id="4ae85-103">StyleSheet 元素 (StyleSheets_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="4ae85-103">StyleSheet element (StyleSheets_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="4ae85-104">表示在文档中定义的样式。</span><span class="sxs-lookup"><span data-stu-id="4ae85-104">Represents a style defined in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4ae85-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4ae85-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4ae85-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4ae85-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4ae85-107">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="4ae85-107">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4ae85-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4ae85-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4ae85-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4ae85-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4ae85-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="4ae85-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4ae85-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4ae85-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4ae85-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="4ae85-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4ae85-113">定义</span><span class="sxs-lookup"><span data-stu-id="4ae85-113">Definition</span></span>

```XML
< xs:element name="StyleSheet" Type="StyleSheet_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4ae85-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4ae85-114">Elements and attributes</span></span>

<span data-ttu-id="4ae85-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4ae85-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4ae85-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4ae85-116">Parent elements</span></span>

|<span data-ttu-id="4ae85-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4ae85-117">**Element**</span></span>|<span data-ttu-id="4ae85-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ae85-118">**Type**</span></span>|<span data-ttu-id="4ae85-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ae85-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4ae85-120">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="4ae85-120">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4ae85-121">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="4ae85-121">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ae85-122">包含文档的**样式表**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="4ae85-122">Contains a collection of **StyleSheet** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4ae85-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4ae85-123">Child elements</span></span>

|<span data-ttu-id="4ae85-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4ae85-124">**Element**</span></span>|<span data-ttu-id="4ae85-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ae85-125">**Type**</span></span>|<span data-ttu-id="4ae85-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ae85-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4ae85-127">Cell</span><span class="sxs-lookup"><span data-stu-id="4ae85-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="4ae85-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="4ae85-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ae85-129">指定一个属性。</span><span class="sxs-lookup"><span data-stu-id="4ae85-129">Specifies a single property.</span></span>  <br/> |
|[<span data-ttu-id="4ae85-130">Section</span><span class="sxs-lookup"><span data-stu-id="4ae85-130">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4ae85-131">Section_Type</span><span class="sxs-lookup"><span data-stu-id="4ae85-131">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ae85-132">指定相关属性的集合。</span><span class="sxs-lookup"><span data-stu-id="4ae85-132">Specifies a collection of related properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4ae85-133">属性</span><span class="sxs-lookup"><span data-stu-id="4ae85-133">Attributes</span></span>

|<span data-ttu-id="4ae85-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="4ae85-134">**Attribute**</span></span>|<span data-ttu-id="4ae85-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ae85-135">**Type**</span></span>|<span data-ttu-id="4ae85-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="4ae85-136">**Required**</span></span>|<span data-ttu-id="4ae85-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="4ae85-137">**Description**</span></span>|<span data-ttu-id="4ae85-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4ae85-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ae85-139">FillStyle</span><span class="sxs-lookup"><span data-stu-id="4ae85-139">FillStyle</span></span>  <br/> |<span data-ttu-id="4ae85-140">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ae85-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ae85-141">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-141">optional</span></span>  <br/> |<span data-ttu-id="4ae85-142">此样式从中继承填充格式的样式表元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae85-142">The ID of the StyleSheet element from which this style inherits fill formatting.</span></span>  <br/> |<span data-ttu-id="4ae85-143">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-144">ID</span><span class="sxs-lookup"><span data-stu-id="4ae85-144">ID</span></span>  <br/> |<span data-ttu-id="4ae85-145">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ae85-145">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ae85-146">必需</span><span class="sxs-lookup"><span data-stu-id="4ae85-146">required</span></span>  <br/> |<span data-ttu-id="4ae85-147">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae85-147">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="4ae85-148">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-149">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="4ae85-149">IsCustomName</span></span>  <br/> |<span data-ttu-id="4ae85-150">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="4ae85-150">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4ae85-151">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-151">optional</span></span>  <br/> |<span data-ttu-id="4ae85-152">指示该名称是否已由用户自定义。</span><span class="sxs-lookup"><span data-stu-id="4ae85-152">Indicates whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="4ae85-153">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-153">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-154">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="4ae85-154">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="4ae85-155">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="4ae85-155">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4ae85-156">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-156">optional</span></span>  <br/> |<span data-ttu-id="4ae85-157">指示是否已由用户自定义通用名称。</span><span class="sxs-lookup"><span data-stu-id="4ae85-157">Indicates whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="4ae85-158">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-158">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-159">LineStyle</span><span class="sxs-lookup"><span data-stu-id="4ae85-159">LineStyle</span></span>  <br/> |<span data-ttu-id="4ae85-160">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ae85-160">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ae85-161">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-161">optional</span></span>  <br/> |<span data-ttu-id="4ae85-162">样式表元素的 ID, 此样式从该元素继承行格式设置。</span><span class="sxs-lookup"><span data-stu-id="4ae85-162">The ID of the StyleSheet element from which this style inherits line formatting.</span></span>  <br/> |<span data-ttu-id="4ae85-163">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-164">名称</span><span class="sxs-lookup"><span data-stu-id="4ae85-164">Name</span></span>  <br/> |<span data-ttu-id="4ae85-165">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4ae85-165">xsd:string</span></span>  <br/> |<span data-ttu-id="4ae85-166">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-166">optional</span></span>  <br/> |<span data-ttu-id="4ae85-167">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="4ae85-167">The name of the element.</span></span>  <br/> |<span data-ttu-id="4ae85-168">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-168">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-169">NameU</span><span class="sxs-lookup"><span data-stu-id="4ae85-169">NameU</span></span>  <br/> |<span data-ttu-id="4ae85-170">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4ae85-170">xsd:string</span></span>  <br/> |<span data-ttu-id="4ae85-171">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-171">optional</span></span>  <br/> |<span data-ttu-id="4ae85-172">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="4ae85-172">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="4ae85-173">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-173">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4ae85-174">TextStyle</span><span class="sxs-lookup"><span data-stu-id="4ae85-174">TextStyle</span></span>  <br/> |<span data-ttu-id="4ae85-175">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4ae85-175">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4ae85-176">可选</span><span class="sxs-lookup"><span data-stu-id="4ae85-176">optional</span></span>  <br/> |<span data-ttu-id="4ae85-177">此样式从中继承文本格式的样式表元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae85-177">The ID of the StyleSheet element from which this style inherits text formatting.</span></span>  <br/> |<span data-ttu-id="4ae85-178">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4ae85-178">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

