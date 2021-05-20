---
title: 'SplineStart (XML)  (Visio的 Cell 元素) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 021536b9-6724-4b8a-35c2-966e456e5232
description: 包含样条的第二个控制点、其第二个节点、第一个节点、最后一个节点或样条的度数的 x 或 y 坐标。
ms.openlocfilehash: e3a99818d897af21e3064e0fc92d9d56ffcf5a15
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539353"
---
# <a name="cell-element-splinestart-row-visio-xml"></a><span data-ttu-id="f4dca-103">SplineStart (XML)  (Visio的 Cell 元素) </span><span class="sxs-lookup"><span data-stu-id="f4dca-103">Cell element (SplineStart Row) (Visio XML)</span></span>

<span data-ttu-id="f4dca-104">包含样条的第二个控制点、其第二个节点、第一个节点、最后一个节点或样条的度数的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="f4dca-104">Contains x- or y-coordinates for a spline's second control point, its second knot, its first knot, the last knot, or the degree of the spline.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f4dca-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f4dca-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f4dca-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f4dca-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f4dca-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f4dca-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f4dca-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f4dca-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f4dca-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f4dca-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f4dca-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f4dca-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f4dca-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f4dca-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f4dca-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="f4dca-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f4dca-113">定义</span><span class="sxs-lookup"><span data-stu-id="f4dca-113">Definition</span></span>

```XML
<xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f4dca-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f4dca-114">Elements and attributes</span></span>

<span data-ttu-id="f4dca-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f4dca-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f4dca-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f4dca-116">Parent elements</span></span>

|<span data-ttu-id="f4dca-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f4dca-117">**Element**</span></span>|<span data-ttu-id="f4dca-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f4dca-118">**Type**</span></span>|<span data-ttu-id="f4dca-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4dca-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f4dca-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="f4dca-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f4dca-121">SplineStart_Type</span><span class="sxs-lookup"><span data-stu-id="f4dca-121">SplineStart_Type</span></span>](splinestart_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f4dca-122">包含样条的第二个控制点、其第二个节点、第一个节点、最后一个节点或样条的度数的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="f4dca-122">Contains x- or y-coordinates for a spline's second control point, its second knot, its first knot, the last knot, or the degree of the spline.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f4dca-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f4dca-123">Child elements</span></span>

|<span data-ttu-id="f4dca-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f4dca-124">**Element**</span></span>|<span data-ttu-id="f4dca-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f4dca-125">**Type**</span></span>|<span data-ttu-id="f4dca-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4dca-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f4dca-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="f4dca-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f4dca-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="f4dca-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f4dca-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="f4dca-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f4dca-130">属性</span><span class="sxs-lookup"><span data-stu-id="f4dca-130">Attributes</span></span>

|<span data-ttu-id="f4dca-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="f4dca-131">**Attribute**</span></span>|<span data-ttu-id="f4dca-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="f4dca-132">**Type**</span></span>|<span data-ttu-id="f4dca-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="f4dca-133">**Required**</span></span>|<span data-ttu-id="f4dca-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="f4dca-134">**Description**</span></span>|<span data-ttu-id="f4dca-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f4dca-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4dca-136">E</span><span class="sxs-lookup"><span data-stu-id="f4dca-136">E</span></span>  <br/> |<span data-ttu-id="f4dca-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f4dca-137">xsd:string</span></span>  <br/> |<span data-ttu-id="f4dca-138">可选</span><span class="sxs-lookup"><span data-stu-id="f4dca-138">optional</span></span>  <br/> |<span data-ttu-id="f4dca-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="f4dca-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="f4dca-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="f4dca-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="f4dca-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f4dca-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="f4dca-142">F</span><span class="sxs-lookup"><span data-stu-id="f4dca-142">F</span></span>  <br/> |<span data-ttu-id="f4dca-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f4dca-143">xsd:string</span></span>  <br/> |<span data-ttu-id="f4dca-144">可选</span><span class="sxs-lookup"><span data-stu-id="f4dca-144">optional</span></span>  <br/> | <span data-ttu-id="f4dca-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="f4dca-145">Represents the element's formula.</span></span> <span data-ttu-id="f4dca-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="f4dca-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="f4dca-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="f4dca-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="f4dca-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="f4dca-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="f4dca-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="f4dca-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="f4dca-150">公式。</span><span class="sxs-lookup"><span data-stu-id="f4dca-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="f4dca-151">N</span><span class="sxs-lookup"><span data-stu-id="f4dca-151">N</span></span>  <br/> |<span data-ttu-id="f4dca-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f4dca-152">xsd:string</span></span>  <br/> |<span data-ttu-id="f4dca-153">必需</span><span class="sxs-lookup"><span data-stu-id="f4dca-153">required</span></span>  <br/> |<span data-ttu-id="f4dca-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f4dca-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="f4dca-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f4dca-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="f4dca-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="f4dca-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="f4dca-157">U</span><span class="sxs-lookup"><span data-stu-id="f4dca-157">U</span></span>  <br/> |<span data-ttu-id="f4dca-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f4dca-158">xsd:string</span></span>  <br/> |<span data-ttu-id="f4dca-159">可选</span><span class="sxs-lookup"><span data-stu-id="f4dca-159">optional</span></span>  <br/> |<span data-ttu-id="f4dca-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="f4dca-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="f4dca-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="f4dca-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="f4dca-162">V</span><span class="sxs-lookup"><span data-stu-id="f4dca-162">V</span></span>  <br/> |<span data-ttu-id="f4dca-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="f4dca-163">xsd:string</span></span>  <br/> |<span data-ttu-id="f4dca-164">可选</span><span class="sxs-lookup"><span data-stu-id="f4dca-164">optional</span></span>  <br/> |<span data-ttu-id="f4dca-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f4dca-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="f4dca-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f4dca-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f4dca-167">备注</span><span class="sxs-lookup"><span data-stu-id="f4dca-167">Remarks</span></span>

<span data-ttu-id="f4dca-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="f4dca-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="f4dca-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f4dca-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="f4dca-170">**值**</span><span class="sxs-lookup"><span data-stu-id="f4dca-170">**Value**</span></span>|<span data-ttu-id="f4dca-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="f4dca-171">**Description**</span></span>|<span data-ttu-id="f4dca-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f4dca-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4dca-173">X</span><span class="sxs-lookup"><span data-stu-id="f4dca-173">X</span></span>  <br/> |<span data-ttu-id="f4dca-174">样条第二个控制点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="f4dca-174">The x-coordinate of a spline's second control point.</span></span>  <br/> |[<span data-ttu-id="f4dca-175">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f4dca-175">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f4dca-176">Y</span><span class="sxs-lookup"><span data-stu-id="f4dca-176">Y</span></span>  <br/> |<span data-ttu-id="f4dca-177">样条第二个控制点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="f4dca-177">The y-coordinate of a spline's second control point.</span></span>  <br/> |[<span data-ttu-id="f4dca-178">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f4dca-178">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f4dca-179">A</span><span class="sxs-lookup"><span data-stu-id="f4dca-179">A</span></span>  <br/> |<span data-ttu-id="f4dca-180">样条的第二个节点。</span><span class="sxs-lookup"><span data-stu-id="f4dca-180">The second knot of the spline.</span></span>  <br/> |[<span data-ttu-id="f4dca-181">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f4dca-181">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f4dca-182">B</span><span class="sxs-lookup"><span data-stu-id="f4dca-182">B</span></span>  <br/> |<span data-ttu-id="f4dca-183">样条的第一个节点。</span><span class="sxs-lookup"><span data-stu-id="f4dca-183">The first knot of a spline.</span></span>  <br/> |[<span data-ttu-id="f4dca-184">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f4dca-184">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f4dca-185">C</span><span class="sxs-lookup"><span data-stu-id="f4dca-185">C</span></span>  <br/> |<span data-ttu-id="f4dca-186">样条的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="f4dca-186">The last knot of a spline.</span></span>  <br/> |[<span data-ttu-id="f4dca-187">RelEllipticalArcTo "Geometry" (行) </span><span class="sxs-lookup"><span data-stu-id="f4dca-187">RelEllipticalArcTo Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
|<span data-ttu-id="f4dca-188">D</span><span class="sxs-lookup"><span data-stu-id="f4dca-188">D</span></span>  <br/> |<span data-ttu-id="f4dca-189">样条的角度（从 1 到 25 的整数）。</span><span class="sxs-lookup"><span data-stu-id="f4dca-189">The degree of a spline (an integer from 1 to 25).</span></span>  <br/> |[<span data-ttu-id="f4dca-190">SplineStart Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f4dca-190">SplineStart Row (Geometry Section)</span></span>](splinestart-row-geometry-section.md) <br/> |
   

