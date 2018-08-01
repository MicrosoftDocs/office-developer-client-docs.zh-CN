---
title: 单元格元素 （RelLineTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 44d369f0-ab37-75ca-727e-b421d6f95ba7
description: 包含 x-或相对于形状的宽度和高度直线段终顶点的 y 坐标。
ms.openlocfilehash: 73930b15a62a483b38da4791511f735ac81bb1a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779858"
---
# <a name="cell-element-rellineto-row-visio-xml"></a><span data-ttu-id="48c7a-103">单元格元素 （RelLineTo 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="48c7a-103">Cell element (RelLineTo Row) ('Visio XML')</span></span>

<span data-ttu-id="48c7a-104">包含 x-或相对于形状的宽度和高度直线段终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="48c7a-104">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="48c7a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="48c7a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="48c7a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="48c7a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="48c7a-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="48c7a-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="48c7a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="48c7a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="48c7a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="48c7a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="48c7a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="48c7a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="48c7a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="48c7a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="48c7a-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="48c7a-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="48c7a-113">定义</span><span class="sxs-lookup"><span data-stu-id="48c7a-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="48c7a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="48c7a-114">Elements and attributes</span></span>

<span data-ttu-id="48c7a-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="48c7a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="48c7a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="48c7a-116">Parent elements</span></span>

|<span data-ttu-id="48c7a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="48c7a-117">**Element**</span></span>|<span data-ttu-id="48c7a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="48c7a-118">**Type**</span></span>|<span data-ttu-id="48c7a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="48c7a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48c7a-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="48c7a-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="48c7a-121">RelLineTo_Type</span><span class="sxs-lookup"><span data-stu-id="48c7a-121">RelLineTo_Type</span></span>](rellineto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48c7a-122">包含 x-或相对于形状的宽度和高度直线段终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="48c7a-122">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="48c7a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="48c7a-123">Child elements</span></span>

|<span data-ttu-id="48c7a-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="48c7a-124">**Element**</span></span>|<span data-ttu-id="48c7a-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="48c7a-125">**Type**</span></span>|<span data-ttu-id="48c7a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="48c7a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48c7a-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="48c7a-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="48c7a-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="48c7a-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48c7a-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="48c7a-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="48c7a-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="48c7a-130">Attributes</span></span>

|<span data-ttu-id="48c7a-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="48c7a-131">**Attribute**</span></span>|<span data-ttu-id="48c7a-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="48c7a-132">**Type**</span></span>|<span data-ttu-id="48c7a-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="48c7a-133">**Required**</span></span>|<span data-ttu-id="48c7a-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="48c7a-134">**Description**</span></span>|<span data-ttu-id="48c7a-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="48c7a-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48c7a-136">E</span><span class="sxs-lookup"><span data-stu-id="48c7a-136">E</span></span>  <br/> |<span data-ttu-id="48c7a-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48c7a-137">xsd:string</span></span>  <br/> |<span data-ttu-id="48c7a-138">可选</span><span class="sxs-lookup"><span data-stu-id="48c7a-138">optional</span></span>  <br/> |<span data-ttu-id="48c7a-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="48c7a-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="48c7a-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="48c7a-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="48c7a-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="48c7a-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="48c7a-142">F</span><span class="sxs-lookup"><span data-stu-id="48c7a-142">F</span></span>  <br/> |<span data-ttu-id="48c7a-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48c7a-143">xsd:string</span></span>  <br/> |<span data-ttu-id="48c7a-144">可选</span><span class="sxs-lookup"><span data-stu-id="48c7a-144">optional</span></span>  <br/> | <span data-ttu-id="48c7a-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-145">Represents the element's formula.</span></span> <span data-ttu-id="48c7a-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="48c7a-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="48c7a-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="48c7a-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="48c7a-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="48c7a-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="48c7a-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="48c7a-150">公式。</span><span class="sxs-lookup"><span data-stu-id="48c7a-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="48c7a-151">N</span><span class="sxs-lookup"><span data-stu-id="48c7a-151">N</span></span>  <br/> |<span data-ttu-id="48c7a-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48c7a-152">xsd:string</span></span>  <br/> |<span data-ttu-id="48c7a-153">必需</span><span class="sxs-lookup"><span data-stu-id="48c7a-153">required</span></span>  <br/> |<span data-ttu-id="48c7a-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="48c7a-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="48c7a-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="48c7a-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="48c7a-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="48c7a-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="48c7a-157">U</span><span class="sxs-lookup"><span data-stu-id="48c7a-157">U</span></span>  <br/> |<span data-ttu-id="48c7a-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48c7a-158">xsd:string</span></span>  <br/> |<span data-ttu-id="48c7a-159">可选</span><span class="sxs-lookup"><span data-stu-id="48c7a-159">optional</span></span>  <br/> |<span data-ttu-id="48c7a-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="48c7a-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="48c7a-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="48c7a-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="48c7a-162">V</span><span class="sxs-lookup"><span data-stu-id="48c7a-162">V</span></span>  <br/> |<span data-ttu-id="48c7a-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48c7a-163">xsd:string</span></span>  <br/> |<span data-ttu-id="48c7a-164">可选</span><span class="sxs-lookup"><span data-stu-id="48c7a-164">optional</span></span>  <br/> |<span data-ttu-id="48c7a-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="48c7a-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="48c7a-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="48c7a-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48c7a-167">说明</span><span class="sxs-lookup"><span data-stu-id="48c7a-167">Remarks</span></span>

<span data-ttu-id="48c7a-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="48c7a-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="48c7a-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="48c7a-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="48c7a-170">**值**</span><span class="sxs-lookup"><span data-stu-id="48c7a-170">**Value**</span></span>|<span data-ttu-id="48c7a-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="48c7a-171">**Description**</span></span>|<span data-ttu-id="48c7a-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="48c7a-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48c7a-173">X</span><span class="sxs-lookup"><span data-stu-id="48c7a-173">X</span></span>  <br/> |<span data-ttu-id="48c7a-174">相对于形状的宽度直线段终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="48c7a-174">The x-coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |[<span data-ttu-id="48c7a-175">RelLineTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="48c7a-175">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="48c7a-176">Y</span><span class="sxs-lookup"><span data-stu-id="48c7a-176">Y</span></span>  <br/> |<span data-ttu-id="48c7a-177">相对于形状的高度直线段终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="48c7a-177">The y-coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |[<span data-ttu-id="48c7a-178">RelLineTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="48c7a-178">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
   

