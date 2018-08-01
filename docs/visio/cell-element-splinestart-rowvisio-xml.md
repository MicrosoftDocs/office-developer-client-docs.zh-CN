---
title: 单元格元素 （SplineStart 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 021536b9-6724-4b8a-35c2-966e456e5232
description: 包含 x 坐标或 y 坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点或样条的度数。
ms.openlocfilehash: ed9c13d3ff376f1a13f17165c737a0a9f186d572
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779836"
---
# <a name="cell-element-splinestart-row-visio-xml"></a><span data-ttu-id="f9e24-103">单元格元素 （SplineStart 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f9e24-103">Cell element (SplineStart Row) ('Visio XML')</span></span>

<span data-ttu-id="f9e24-104">包含 x 坐标或 y 坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点或样条的度数。</span><span class="sxs-lookup"><span data-stu-id="f9e24-104">Contains x- or y-coordinates for a spline's second control point, its second knot, its first knot, the last knot, or the degree of the spline.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f9e24-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f9e24-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f9e24-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f9e24-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f9e24-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f9e24-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f9e24-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f9e24-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f9e24-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f9e24-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f9e24-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f9e24-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f9e24-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f9e24-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f9e24-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="f9e24-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f9e24-113">定义</span><span class="sxs-lookup"><span data-stu-id="f9e24-113">Definition</span></span>

```XML
<xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f9e24-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f9e24-114">Elements and attributes</span></span>

<span data-ttu-id="f9e24-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f9e24-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f9e24-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f9e24-116">Parent elements</span></span>

|<span data-ttu-id="f9e24-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9e24-117">**Element**</span></span>|<span data-ttu-id="f9e24-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9e24-118">**Type**</span></span>|<span data-ttu-id="f9e24-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9e24-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9e24-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="f9e24-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f9e24-121">SplineStart_Type</span><span class="sxs-lookup"><span data-stu-id="f9e24-121">SplineStart_Type</span></span>](splinestart_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9e24-122">包含 x 坐标或 y 坐标样条的第二个控制点、 它的第二个节点、 第一个节点、 最后一个节点或样条的度数。</span><span class="sxs-lookup"><span data-stu-id="f9e24-122">Contains x- or y-coordinates for a spline's second control point, its second knot, its first knot, the last knot, or the degree of the spline.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f9e24-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f9e24-123">Child elements</span></span>

|<span data-ttu-id="f9e24-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9e24-124">**Element**</span></span>|<span data-ttu-id="f9e24-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9e24-125">**Type**</span></span>|<span data-ttu-id="f9e24-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9e24-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9e24-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="f9e24-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f9e24-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="f9e24-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9e24-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="f9e24-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f9e24-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="f9e24-130">Attributes</span></span>

|<span data-ttu-id="f9e24-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="f9e24-131">**Attribute**</span></span>|<span data-ttu-id="f9e24-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9e24-132">**Type**</span></span>|<span data-ttu-id="f9e24-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="f9e24-133">**Required**</span></span>|<span data-ttu-id="f9e24-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9e24-134">**Description**</span></span>|<span data-ttu-id="f9e24-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f9e24-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f9e24-136">E</span><span class="sxs-lookup"><span data-stu-id="f9e24-136">E</span></span>  <br/> |<span data-ttu-id="f9e24-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9e24-137">xsd:string</span></span>  <br/> |<span data-ttu-id="f9e24-138">可选</span><span class="sxs-lookup"><span data-stu-id="f9e24-138">optional</span></span>  <br/> |<span data-ttu-id="f9e24-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="f9e24-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="f9e24-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="f9e24-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="f9e24-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f9e24-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="f9e24-142">F</span><span class="sxs-lookup"><span data-stu-id="f9e24-142">F</span></span>  <br/> |<span data-ttu-id="f9e24-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9e24-143">xsd:string</span></span>  <br/> |<span data-ttu-id="f9e24-144">可选</span><span class="sxs-lookup"><span data-stu-id="f9e24-144">optional</span></span>  <br/> | <span data-ttu-id="f9e24-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="f9e24-145">Represents the element's formula.</span></span> <span data-ttu-id="f9e24-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="f9e24-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="f9e24-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="f9e24-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="f9e24-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="f9e24-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="f9e24-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="f9e24-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="f9e24-150">公式。</span><span class="sxs-lookup"><span data-stu-id="f9e24-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="f9e24-151">N</span><span class="sxs-lookup"><span data-stu-id="f9e24-151">N</span></span>  <br/> |<span data-ttu-id="f9e24-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9e24-152">xsd:string</span></span>  <br/> |<span data-ttu-id="f9e24-153">必需</span><span class="sxs-lookup"><span data-stu-id="f9e24-153">required</span></span>  <br/> |<span data-ttu-id="f9e24-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f9e24-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="f9e24-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f9e24-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="f9e24-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="f9e24-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="f9e24-157">U</span><span class="sxs-lookup"><span data-stu-id="f9e24-157">U</span></span>  <br/> |<span data-ttu-id="f9e24-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9e24-158">xsd:string</span></span>  <br/> |<span data-ttu-id="f9e24-159">可选</span><span class="sxs-lookup"><span data-stu-id="f9e24-159">optional</span></span>  <br/> |<span data-ttu-id="f9e24-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="f9e24-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="f9e24-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="f9e24-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="f9e24-162">V</span><span class="sxs-lookup"><span data-stu-id="f9e24-162">V</span></span>  <br/> |<span data-ttu-id="f9e24-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9e24-163">xsd:string</span></span>  <br/> |<span data-ttu-id="f9e24-164">可选</span><span class="sxs-lookup"><span data-stu-id="f9e24-164">optional</span></span>  <br/> |<span data-ttu-id="f9e24-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f9e24-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="f9e24-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f9e24-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f9e24-167">说明</span><span class="sxs-lookup"><span data-stu-id="f9e24-167">Remarks</span></span>

<span data-ttu-id="f9e24-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="f9e24-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="f9e24-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="f9e24-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="f9e24-170">**值**</span><span class="sxs-lookup"><span data-stu-id="f9e24-170">**Value**</span></span>|<span data-ttu-id="f9e24-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9e24-171">**Description**</span></span>|<span data-ttu-id="f9e24-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="f9e24-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9e24-173">X</span><span class="sxs-lookup"><span data-stu-id="f9e24-173">X</span></span>  <br/> |<span data-ttu-id="f9e24-174">样条第二个控制点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="f9e24-174">The x-coordinate of a spline's second control point.</span></span>  <br/> |[<span data-ttu-id="f9e24-175">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f9e24-175">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f9e24-176">Y</span><span class="sxs-lookup"><span data-stu-id="f9e24-176">Y</span></span>  <br/> |<span data-ttu-id="f9e24-177">样条第二个控制点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="f9e24-177">The y-coordinate of a spline's second control point.</span></span>  <br/> |[<span data-ttu-id="f9e24-178">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f9e24-178">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f9e24-179">A</span><span class="sxs-lookup"><span data-stu-id="f9e24-179">A</span></span>  <br/> |<span data-ttu-id="f9e24-180">样条的第二个节点。</span><span class="sxs-lookup"><span data-stu-id="f9e24-180">The second knot of the spline.</span></span>  <br/> |[<span data-ttu-id="f9e24-181">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f9e24-181">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f9e24-182">B</span><span class="sxs-lookup"><span data-stu-id="f9e24-182">B</span></span>  <br/> |<span data-ttu-id="f9e24-183">样条的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="f9e24-183">The first knot of a spline.</span></span>  <br/> |[<span data-ttu-id="f9e24-184">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f9e24-184">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f9e24-185">C</span><span class="sxs-lookup"><span data-stu-id="f9e24-185">C</span></span>  <br/> |<span data-ttu-id="f9e24-186">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="f9e24-186">The last knot of a spline.</span></span>  <br/> |[<span data-ttu-id="f9e24-187">RelEllipticalArcTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="f9e24-187">RelEllipticalArcTo Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f9e24-188">D</span><span class="sxs-lookup"><span data-stu-id="f9e24-188">D</span></span>  <br/> |<span data-ttu-id="f9e24-189">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="f9e24-189">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |[<span data-ttu-id="f9e24-190">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f9e24-190">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
   

