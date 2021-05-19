---
title: 'Cell 元素 (Ellipse Row)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 210e6731-7c94-90b1-c7c4-635df974fdb6
description: 包含椭圆的中心点和椭圆上的两个点的 x 坐标或 y 坐标。
ms.openlocfilehash: a2dde9cdc731595bfc8df646ab984cfbfb9db379
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541867"
---
# <a name="cell-element-ellipse-row-visio-xml"></a><span data-ttu-id="bfe06-103">Cell 元素 (Ellipse Row)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="bfe06-103">Cell element (Ellipse Row) (Visio XML)</span></span>

<span data-ttu-id="bfe06-104">包含椭圆的中心点和椭圆上的两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="bfe06-104">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="bfe06-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="bfe06-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bfe06-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="bfe06-106">**Element type**</span></span> <br/> |[<span data-ttu-id="bfe06-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="bfe06-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="bfe06-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bfe06-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="bfe06-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bfe06-109">**Schema file**</span></span> <br/> |<span data-ttu-id="bfe06-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="bfe06-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="bfe06-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="bfe06-111">**Document parts**</span></span> <br/> |<span data-ttu-id="bfe06-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="bfe06-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bfe06-113">定义</span><span class="sxs-lookup"><span data-stu-id="bfe06-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bfe06-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bfe06-114">Elements and attributes</span></span>

<span data-ttu-id="bfe06-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="bfe06-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="bfe06-116">父元素</span><span class="sxs-lookup"><span data-stu-id="bfe06-116">Parent elements</span></span>

|<span data-ttu-id="bfe06-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="bfe06-117">**Element**</span></span>|<span data-ttu-id="bfe06-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="bfe06-118">**Type**</span></span>|<span data-ttu-id="bfe06-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="bfe06-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bfe06-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="bfe06-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="bfe06-121">Ellipse_Type</span><span class="sxs-lookup"><span data-stu-id="bfe06-121">Ellipse_Type</span></span>](ellipse_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bfe06-122">包含椭圆的中心点和椭圆上的两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="bfe06-122">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="bfe06-123">子元素</span><span class="sxs-lookup"><span data-stu-id="bfe06-123">Child elements</span></span>

|<span data-ttu-id="bfe06-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="bfe06-124">**Element**</span></span>|<span data-ttu-id="bfe06-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="bfe06-125">**Type**</span></span>|<span data-ttu-id="bfe06-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="bfe06-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bfe06-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="bfe06-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bfe06-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="bfe06-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bfe06-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="bfe06-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="bfe06-130">属性</span><span class="sxs-lookup"><span data-stu-id="bfe06-130">Attributes</span></span>

|<span data-ttu-id="bfe06-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="bfe06-131">**Attribute**</span></span>|<span data-ttu-id="bfe06-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="bfe06-132">**Type**</span></span>|<span data-ttu-id="bfe06-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="bfe06-133">**Required**</span></span>|<span data-ttu-id="bfe06-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="bfe06-134">**Description**</span></span>|<span data-ttu-id="bfe06-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="bfe06-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bfe06-136">E</span><span class="sxs-lookup"><span data-stu-id="bfe06-136">E</span></span>  <br/> |<span data-ttu-id="bfe06-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="bfe06-137">xsd:string</span></span>  <br/> |<span data-ttu-id="bfe06-138">可选</span><span class="sxs-lookup"><span data-stu-id="bfe06-138">optional</span></span>  <br/> |<span data-ttu-id="bfe06-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="bfe06-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="bfe06-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="bfe06-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="bfe06-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="bfe06-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="bfe06-142">F</span><span class="sxs-lookup"><span data-stu-id="bfe06-142">F</span></span>  <br/> |<span data-ttu-id="bfe06-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="bfe06-143">xsd:string</span></span>  <br/> |<span data-ttu-id="bfe06-144">可选</span><span class="sxs-lookup"><span data-stu-id="bfe06-144">optional</span></span>  <br/> | <span data-ttu-id="bfe06-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="bfe06-145">Represents the element's formula.</span></span> <span data-ttu-id="bfe06-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="bfe06-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="bfe06-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="bfe06-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="bfe06-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="bfe06-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="bfe06-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="bfe06-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="bfe06-150">公式。</span><span class="sxs-lookup"><span data-stu-id="bfe06-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="bfe06-151">N</span><span class="sxs-lookup"><span data-stu-id="bfe06-151">N</span></span>  <br/> |<span data-ttu-id="bfe06-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="bfe06-152">xsd:string</span></span>  <br/> |<span data-ttu-id="bfe06-153">必需</span><span class="sxs-lookup"><span data-stu-id="bfe06-153">required</span></span>  <br/> |<span data-ttu-id="bfe06-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="bfe06-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="bfe06-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="bfe06-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="bfe06-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="bfe06-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="bfe06-157">U</span><span class="sxs-lookup"><span data-stu-id="bfe06-157">U</span></span>  <br/> |<span data-ttu-id="bfe06-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="bfe06-158">xsd:string</span></span>  <br/> |<span data-ttu-id="bfe06-159">可选</span><span class="sxs-lookup"><span data-stu-id="bfe06-159">optional</span></span>  <br/> |<span data-ttu-id="bfe06-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="bfe06-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="bfe06-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="bfe06-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="bfe06-162">V</span><span class="sxs-lookup"><span data-stu-id="bfe06-162">V</span></span>  <br/> |<span data-ttu-id="bfe06-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="bfe06-163">xsd:string</span></span>  <br/> |<span data-ttu-id="bfe06-164">可选</span><span class="sxs-lookup"><span data-stu-id="bfe06-164">optional</span></span>  <br/> |<span data-ttu-id="bfe06-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="bfe06-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="bfe06-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="bfe06-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bfe06-167">备注</span><span class="sxs-lookup"><span data-stu-id="bfe06-167">Remarks</span></span>

<span data-ttu-id="bfe06-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="bfe06-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="bfe06-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="bfe06-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="bfe06-170">**值**</span><span class="sxs-lookup"><span data-stu-id="bfe06-170">**Value**</span></span>|<span data-ttu-id="bfe06-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="bfe06-171">**Description**</span></span>|<span data-ttu-id="bfe06-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="bfe06-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bfe06-173">X</span><span class="sxs-lookup"><span data-stu-id="bfe06-173">X</span></span>  <br/> |<span data-ttu-id="bfe06-174">中心点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="bfe06-174">The x-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="bfe06-175">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-175">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="bfe06-176">Y</span><span class="sxs-lookup"><span data-stu-id="bfe06-176">Y</span></span>  <br/> |<span data-ttu-id="bfe06-177">中心点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="bfe06-177">The y-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="bfe06-178">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-178">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="bfe06-179">A</span><span class="sxs-lookup"><span data-stu-id="bfe06-179">A</span></span>  <br/> |<span data-ttu-id="bfe06-180">椭圆上第一个点的 x 坐标;与 B 单元格所代表的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="bfe06-180">The x-coordinate of the first point on the ellipse; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="bfe06-181">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-181">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="bfe06-182">B</span><span class="sxs-lookup"><span data-stu-id="bfe06-182">B</span></span>  <br/> |<span data-ttu-id="bfe06-183">椭圆上第一个点的 y 坐标;与由 A 单元格表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="bfe06-183">The y-coordinate of the first point on the ellipse; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="bfe06-184">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-184">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="bfe06-185">C</span><span class="sxs-lookup"><span data-stu-id="bfe06-185">C</span></span>  <br/> |<span data-ttu-id="bfe06-186">椭圆上第二个点的 x 坐标;与由 D 单元格表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="bfe06-186">The x-coordinate of the second point on the ellipse; paired with y-coordinate represented by the D cell.</span></span>  <br/> |[<span data-ttu-id="bfe06-187">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-187">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="bfe06-188">D</span><span class="sxs-lookup"><span data-stu-id="bfe06-188">D</span></span>  <br/> |<span data-ttu-id="bfe06-189">椭圆上第二个点的 y 坐标;与 C 单元格表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="bfe06-189">The y-coordinate of the second point on the ellipse; paired with y-coordinate represented by the C cell.</span></span>  <br/> |[<span data-ttu-id="bfe06-190">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="bfe06-190">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
   

