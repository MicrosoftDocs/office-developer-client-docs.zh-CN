---
title: 单元格元素 （RelQuadBezTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8b3aea70-a69f-a85e-83d8-c0fa2ee68836
description: 包含 x 坐标或 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点或曲线相对于形状的宽度和高度的控制点 x 或 y 坐标。
ms.openlocfilehash: 5f823e5930d3dad8bf6e20727e4b527493f89892
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779852"
---
# <a name="cell-element-relquadbezto-row-visio-xml"></a><span data-ttu-id="2325a-103">单元格元素 （RelQuadBezTo 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2325a-103">Cell element (RelQuadBezTo Row) ('Visio XML')</span></span>

<span data-ttu-id="2325a-104">包含 x 坐标或 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点或曲线相对于形状的宽度和高度的控制点 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="2325a-104">Contains the x- or y-coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height or the x- or y-coordinates of the control point of the curve relative shape's width and height.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2325a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2325a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2325a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2325a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2325a-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="2325a-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="2325a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2325a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="2325a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2325a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2325a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="2325a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="2325a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="2325a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="2325a-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="2325a-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2325a-113">定义</span><span class="sxs-lookup"><span data-stu-id="2325a-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2325a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2325a-114">Elements and attributes</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2325a-115">父元素</span><span class="sxs-lookup"><span data-stu-id="2325a-115">Parent elements</span></span>

|<span data-ttu-id="2325a-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="2325a-116">**Element**</span></span>|<span data-ttu-id="2325a-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="2325a-117">**Type**</span></span>|<span data-ttu-id="2325a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="2325a-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2325a-119">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="2325a-119">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="2325a-120">RelQuadBezTo_Type</span><span class="sxs-lookup"><span data-stu-id="2325a-120">RelQuadBezTo_Type</span></span>](relquadbezto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2325a-121">包含 x 坐标或 y 坐标的相对于形状的宽度和高度二次贝塞尔曲线的终结点或曲线相对于形状的宽度和高度的控制点 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="2325a-121">Contains the x- or y-coordinates of the endpoint of a quadratic Bézier curve relative to the shape's width and height or the x- or y-coordinates of the control point of the curve relative shape's width and height.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2325a-122">子元素</span><span class="sxs-lookup"><span data-stu-id="2325a-122">Child elements</span></span>

|<span data-ttu-id="2325a-123">**元素**</span><span class="sxs-lookup"><span data-stu-id="2325a-123">**Element**</span></span>|<span data-ttu-id="2325a-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="2325a-124">**Type**</span></span>|<span data-ttu-id="2325a-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="2325a-125">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2325a-126">RefBy</span><span class="sxs-lookup"><span data-stu-id="2325a-126">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2325a-127">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="2325a-127">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2325a-128">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="2325a-128">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2325a-129">Attributes</span><span class="sxs-lookup"><span data-stu-id="2325a-129">Attributes</span></span>

|<span data-ttu-id="2325a-130">**属性**</span><span class="sxs-lookup"><span data-stu-id="2325a-130">**Attribute**</span></span>|<span data-ttu-id="2325a-131">**类型**</span><span class="sxs-lookup"><span data-stu-id="2325a-131">**Type**</span></span>|<span data-ttu-id="2325a-132">**必需**</span><span class="sxs-lookup"><span data-stu-id="2325a-132">**Required**</span></span>|<span data-ttu-id="2325a-133">**说明**</span><span class="sxs-lookup"><span data-stu-id="2325a-133">**Description**</span></span>|<span data-ttu-id="2325a-134">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2325a-134">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2325a-135">E</span><span class="sxs-lookup"><span data-stu-id="2325a-135">E</span></span>  <br/> |<span data-ttu-id="2325a-136">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2325a-136">xsd:string</span></span>  <br/> |<span data-ttu-id="2325a-137">可选</span><span class="sxs-lookup"><span data-stu-id="2325a-137">optional</span></span>  <br/> |<span data-ttu-id="2325a-138">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="2325a-138">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="2325a-139">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="2325a-139">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="2325a-140">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="2325a-140">An error message string.</span></span>  <br/> |
|<span data-ttu-id="2325a-141">F</span><span class="sxs-lookup"><span data-stu-id="2325a-141">F</span></span>  <br/> |<span data-ttu-id="2325a-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2325a-142">xsd:string</span></span>  <br/> |<span data-ttu-id="2325a-143">可选</span><span class="sxs-lookup"><span data-stu-id="2325a-143">optional</span></span>  <br/> | <span data-ttu-id="2325a-144">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="2325a-144">Represents the element's formula.</span></span> <span data-ttu-id="2325a-145">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="2325a-145">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="2325a-146">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="2325a-146">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="2325a-147">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="2325a-147">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="2325a-148">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="2325a-148">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="2325a-149">公式。</span><span class="sxs-lookup"><span data-stu-id="2325a-149">A formula.</span></span>  <br/> |
|<span data-ttu-id="2325a-150">N</span><span class="sxs-lookup"><span data-stu-id="2325a-150">N</span></span>  <br/> |<span data-ttu-id="2325a-151">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2325a-151">xsd:string</span></span>  <br/> |<span data-ttu-id="2325a-152">必需</span><span class="sxs-lookup"><span data-stu-id="2325a-152">required</span></span>  <br/> |<span data-ttu-id="2325a-153">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="2325a-153">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="2325a-154">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="2325a-154">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="2325a-155">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="2325a-155">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="2325a-156">U</span><span class="sxs-lookup"><span data-stu-id="2325a-156">U</span></span>  <br/> |<span data-ttu-id="2325a-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2325a-157">xsd:string</span></span>  <br/> |<span data-ttu-id="2325a-158">可选</span><span class="sxs-lookup"><span data-stu-id="2325a-158">optional</span></span>  <br/> |<span data-ttu-id="2325a-159">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="2325a-159">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="2325a-160">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="2325a-160">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="2325a-161">V</span><span class="sxs-lookup"><span data-stu-id="2325a-161">V</span></span>  <br/> |<span data-ttu-id="2325a-162">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2325a-162">xsd:string</span></span>  <br/> |<span data-ttu-id="2325a-163">可选</span><span class="sxs-lookup"><span data-stu-id="2325a-163">optional</span></span>  <br/> |<span data-ttu-id="2325a-164">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2325a-164">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="2325a-165">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2325a-165">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2325a-166">说明</span><span class="sxs-lookup"><span data-stu-id="2325a-166">Remarks</span></span>

<span data-ttu-id="2325a-167">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="2325a-167">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="2325a-168">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="2325a-168">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="2325a-169">**值**</span><span class="sxs-lookup"><span data-stu-id="2325a-169">**Value**</span></span>|<span data-ttu-id="2325a-170">**说明**</span><span class="sxs-lookup"><span data-stu-id="2325a-170">**Description**</span></span>|<span data-ttu-id="2325a-171">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="2325a-171">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2325a-172">X</span><span class="sxs-lookup"><span data-stu-id="2325a-172">X</span></span>  <br/> |<span data-ttu-id="2325a-173">终顶点相对于形状的宽度二次贝塞尔曲线的 x 轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="2325a-173">The x-coordinate of the ending vertex of a quadratic Bézier curve relative to the width of the shape.</span></span>  <br/> |[<span data-ttu-id="2325a-174">RelQuadBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="2325a-174">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="2325a-175">Y</span><span class="sxs-lookup"><span data-stu-id="2325a-175">Y</span></span>  <br/> |<span data-ttu-id="2325a-176">终顶点相对于形状的高度二次贝塞尔曲线的 y 轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="2325a-176">The y-coordinate of the ending vertex of a quadratic Bézier curve relative to the height of the shape.</span></span>  <br/> |[<span data-ttu-id="2325a-177">RelQuadBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="2325a-177">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="2325a-178">A</span><span class="sxs-lookup"><span data-stu-id="2325a-178">A</span></span>  <br/> |<span data-ttu-id="2325a-179">相对于形状的宽度; 控制点的位于曲线的控件的 x 坐标弧形上某个点。是最好位于之间的开始和结束顶点的一半的控制点。</span><span class="sxs-lookup"><span data-stu-id="2325a-179">The x-coordinate of the curve's control point relative to the shape's width; a point on the arc. The control point is best located about halfway between the beginning and ending vertices of the arc.</span></span>  <br/> |[<span data-ttu-id="2325a-180">RelQuadBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="2325a-180">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
|<span data-ttu-id="2325a-181">B</span><span class="sxs-lookup"><span data-stu-id="2325a-181">B</span></span>  <br/> |<span data-ttu-id="2325a-182">相对于形状的高度控制点曲线的控件的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="2325a-182">The y-coordinate of a curve's control point relative to the shape's height.</span></span>  <br/> |[<span data-ttu-id="2325a-183">RelQuadBezTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="2325a-183">RelQuadBezTo Row (Geometry Section)</span></span>](relquadbezto-row-geometry-section.md) <br/> |
   

