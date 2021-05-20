---
title: 'Cell 元素 (RelQuadBezTo 行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8b3aea70-a69f-a85e-83d8-c0fa2ee68836
description: 包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标或 y 坐标，或者曲线相对形状的宽度和高度的控制点的 x 坐标或 y 坐标。
ms.openlocfilehash: 7bdd55cfd5401c8455f09cf7d237117572d12723
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542385"
---
# <a name="cell-element-relquadbezto-row-visio-xml"></a><span data-ttu-id="83344-103">Cell 元素 (RelQuadBezTo 行)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="83344-103">Cell element (RelQuadBezTo Row) (Visio XML)</span></span>

<span data-ttu-id="83344-104">包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标或 y 坐标，或者曲线相对形状的宽度和高度的控制点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="83344-104">Contains the x- or y-coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height or the x- or y-coordinates of the control point of the curve relative shape's width and height.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="83344-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="83344-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="83344-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="83344-106">**Element type**</span></span> <br/> |[<span data-ttu-id="83344-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="83344-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="83344-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="83344-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="83344-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="83344-109">**Schema file**</span></span> <br/> |<span data-ttu-id="83344-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="83344-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="83344-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="83344-111">**Document parts**</span></span> <br/> |<span data-ttu-id="83344-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="83344-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="83344-113">定义</span><span class="sxs-lookup"><span data-stu-id="83344-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="83344-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="83344-114">Elements and attributes</span></span>

### <a name="parent-elements"></a><span data-ttu-id="83344-115">父元素</span><span class="sxs-lookup"><span data-stu-id="83344-115">Parent elements</span></span>

|<span data-ttu-id="83344-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="83344-116">**Element**</span></span>|<span data-ttu-id="83344-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="83344-117">**Type**</span></span>|<span data-ttu-id="83344-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="83344-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83344-119">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="83344-119">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="83344-120">RelQuadBezTo_Type</span><span class="sxs-lookup"><span data-stu-id="83344-120">RelQuadBezTo_Type</span></span>](relquadbezto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="83344-121">包含二次方贝塞尔曲线终点相对于形状的宽度和高度的 x 坐标或 y 坐标，或者曲线相对形状的宽度和高度的控制点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="83344-121">Contains the x- or y-coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height or the x- or y-coordinates of the control point of the curve relative shape's width and height.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="83344-122">子元素</span><span class="sxs-lookup"><span data-stu-id="83344-122">Child elements</span></span>

|<span data-ttu-id="83344-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="83344-123">**Element**</span></span>|<span data-ttu-id="83344-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="83344-124">**Type**</span></span>|<span data-ttu-id="83344-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="83344-125">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="83344-126">RefBy</span><span class="sxs-lookup"><span data-stu-id="83344-126">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="83344-127">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="83344-127">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="83344-128">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="83344-128">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="83344-129">属性</span><span class="sxs-lookup"><span data-stu-id="83344-129">Attributes</span></span>

|<span data-ttu-id="83344-130">**属性**</span><span class="sxs-lookup"><span data-stu-id="83344-130">**Attribute**</span></span>|<span data-ttu-id="83344-131">**类型**</span><span class="sxs-lookup"><span data-stu-id="83344-131">**Type**</span></span>|<span data-ttu-id="83344-132">**必需**</span><span class="sxs-lookup"><span data-stu-id="83344-132">**Required**</span></span>|<span data-ttu-id="83344-133">**描述**</span><span class="sxs-lookup"><span data-stu-id="83344-133">**Description**</span></span>|<span data-ttu-id="83344-134">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="83344-134">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83344-135">E</span><span class="sxs-lookup"><span data-stu-id="83344-135">E</span></span>  <br/> |<span data-ttu-id="83344-136">xsd：string</span><span class="sxs-lookup"><span data-stu-id="83344-136">xsd:string</span></span>  <br/> |<span data-ttu-id="83344-137">可选</span><span class="sxs-lookup"><span data-stu-id="83344-137">optional</span></span>  <br/> |<span data-ttu-id="83344-138">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="83344-138">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="83344-139">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="83344-139">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="83344-140">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="83344-140">An error message string.</span></span>  <br/> |
|<span data-ttu-id="83344-141">F</span><span class="sxs-lookup"><span data-stu-id="83344-141">F</span></span>  <br/> |<span data-ttu-id="83344-142">xsd：string</span><span class="sxs-lookup"><span data-stu-id="83344-142">xsd:string</span></span>  <br/> |<span data-ttu-id="83344-143">可选</span><span class="sxs-lookup"><span data-stu-id="83344-143">optional</span></span>  <br/> | <span data-ttu-id="83344-144">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="83344-144">Represents the element's formula.</span></span> <span data-ttu-id="83344-145">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="83344-145">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="83344-146">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="83344-146">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="83344-147">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="83344-147">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="83344-148">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="83344-148">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="83344-149">公式。</span><span class="sxs-lookup"><span data-stu-id="83344-149">A formula.</span></span>  <br/> |
|<span data-ttu-id="83344-150">N</span><span class="sxs-lookup"><span data-stu-id="83344-150">N</span></span>  <br/> |<span data-ttu-id="83344-151">xsd：string</span><span class="sxs-lookup"><span data-stu-id="83344-151">xsd:string</span></span>  <br/> |<span data-ttu-id="83344-152">必需</span><span class="sxs-lookup"><span data-stu-id="83344-152">required</span></span>  <br/> |<span data-ttu-id="83344-153">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="83344-153">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="83344-154">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="83344-154">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="83344-155">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="83344-155">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="83344-156">U</span><span class="sxs-lookup"><span data-stu-id="83344-156">U</span></span>  <br/> |<span data-ttu-id="83344-157">xsd：string</span><span class="sxs-lookup"><span data-stu-id="83344-157">xsd:string</span></span>  <br/> |<span data-ttu-id="83344-158">可选</span><span class="sxs-lookup"><span data-stu-id="83344-158">optional</span></span>  <br/> |<span data-ttu-id="83344-159">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="83344-159">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="83344-160">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="83344-160">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="83344-161">V</span><span class="sxs-lookup"><span data-stu-id="83344-161">V</span></span>  <br/> |<span data-ttu-id="83344-162">xsd：string</span><span class="sxs-lookup"><span data-stu-id="83344-162">xsd:string</span></span>  <br/> |<span data-ttu-id="83344-163">可选</span><span class="sxs-lookup"><span data-stu-id="83344-163">optional</span></span>  <br/> |<span data-ttu-id="83344-164">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="83344-164">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="83344-165">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="83344-165">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="83344-166">备注</span><span class="sxs-lookup"><span data-stu-id="83344-166">Remarks</span></span>

<span data-ttu-id="83344-167">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="83344-167">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="83344-168">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="83344-168">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="83344-169">**值**</span><span class="sxs-lookup"><span data-stu-id="83344-169">**Value**</span></span>|<span data-ttu-id="83344-170">**说明**</span><span class="sxs-lookup"><span data-stu-id="83344-170">**Description**</span></span>|<span data-ttu-id="83344-171">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="83344-171">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83344-172">X</span><span class="sxs-lookup"><span data-stu-id="83344-172">X</span></span>  <br/> |<span data-ttu-id="83344-173">二次方贝塞尔曲线的终顶点相对于形状宽度的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="83344-173">The x-coordinate of the ending vertex of a quadratic Bézier curve relative to the width of the shape.</span></span>  <br/> |[<span data-ttu-id="83344-174">RelQuadBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="83344-174">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="83344-175">Y</span><span class="sxs-lookup"><span data-stu-id="83344-175">Y</span></span>  <br/> |<span data-ttu-id="83344-176">二次方贝塞尔曲线的终顶点相对于形状高度的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="83344-176">The y-coordinate of the ending vertex of a quadratic Bézier curve relative to the height of the shape.</span></span>  <br/> |[<span data-ttu-id="83344-177">RelQuadBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="83344-177">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="83344-178">A</span><span class="sxs-lookup"><span data-stu-id="83344-178">A</span></span>  <br/> |<span data-ttu-id="83344-179">曲线控制点相对于形状宽度的 x 坐标;弧形上的点。控制点最好位于弧形的开始顶点和结束顶点之间的一半左右。</span><span class="sxs-lookup"><span data-stu-id="83344-179">The x-coordinate of the curve's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc.</span></span>  <br/> |[<span data-ttu-id="83344-180">RelQuadBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="83344-180">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="83344-181">B</span><span class="sxs-lookup"><span data-stu-id="83344-181">B</span></span>  <br/> |<span data-ttu-id="83344-182">曲线控制点相对于形状高度的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="83344-182">The y-coordinate of a curve's control point relative to the shape's height.</span></span>  <br/> |[<span data-ttu-id="83344-183">RelQuadBezTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="83344-183">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
   

