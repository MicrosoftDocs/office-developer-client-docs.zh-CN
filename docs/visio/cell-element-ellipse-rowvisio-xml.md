---
title: Cell 元素 ("椭圆形" 行) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 210e6731-7c94-90b1-c7c4-635df974fdb6
description: 包含椭圆中心点的 x 坐标或 y 坐标以及椭圆上的两个点。
ms.openlocfilehash: 75c3cf86b7c8668b70915117e1fc70b07d2cef0b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356117"
---
# <a name="cell-element-ellipse-row-visio-xml"></a><span data-ttu-id="77727-103">Cell 元素 ("椭圆形" 行) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="77727-103">Cell element (Ellipse Row) ('Visio XML')</span></span>

<span data-ttu-id="77727-104">包含椭圆中心点的 x 坐标或 y 坐标以及椭圆上的两个点。</span><span class="sxs-lookup"><span data-stu-id="77727-104">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="77727-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="77727-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="77727-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="77727-106">**Element type**</span></span> <br/> |[<span data-ttu-id="77727-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="77727-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="77727-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="77727-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="77727-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="77727-109">**Schema file**</span></span> <br/> |<span data-ttu-id="77727-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="77727-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="77727-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="77727-111">**Document parts**</span></span> <br/> |<span data-ttu-id="77727-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="77727-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="77727-113">定义</span><span class="sxs-lookup"><span data-stu-id="77727-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="77727-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="77727-114">Elements and attributes</span></span>

<span data-ttu-id="77727-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="77727-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="77727-116">父元素</span><span class="sxs-lookup"><span data-stu-id="77727-116">Parent elements</span></span>

|<span data-ttu-id="77727-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="77727-117">**Element**</span></span>|<span data-ttu-id="77727-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="77727-118">**Type**</span></span>|<span data-ttu-id="77727-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="77727-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="77727-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="77727-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="77727-121">Ellipse_Type</span><span class="sxs-lookup"><span data-stu-id="77727-121">Ellipse_Type</span></span>](ellipse_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="77727-122">包含椭圆中心点的 x 坐标或 y 坐标以及椭圆上的两个点。</span><span class="sxs-lookup"><span data-stu-id="77727-122">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="77727-123">子元素</span><span class="sxs-lookup"><span data-stu-id="77727-123">Child elements</span></span>

|<span data-ttu-id="77727-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="77727-124">**Element**</span></span>|<span data-ttu-id="77727-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="77727-125">**Type**</span></span>|<span data-ttu-id="77727-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="77727-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="77727-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="77727-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="77727-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="77727-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="77727-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="77727-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="77727-130">属性</span><span class="sxs-lookup"><span data-stu-id="77727-130">Attributes</span></span>

|<span data-ttu-id="77727-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="77727-131">**Attribute**</span></span>|<span data-ttu-id="77727-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="77727-132">**Type**</span></span>|<span data-ttu-id="77727-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="77727-133">**Required**</span></span>|<span data-ttu-id="77727-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="77727-134">**Description**</span></span>|<span data-ttu-id="77727-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="77727-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77727-136">E</span><span class="sxs-lookup"><span data-stu-id="77727-136">E</span></span>  <br/> |<span data-ttu-id="77727-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="77727-137">xsd:string</span></span>  <br/> |<span data-ttu-id="77727-138">可选</span><span class="sxs-lookup"><span data-stu-id="77727-138">optional</span></span>  <br/> |<span data-ttu-id="77727-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="77727-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="77727-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="77727-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="77727-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="77727-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="77727-142">F</span><span class="sxs-lookup"><span data-stu-id="77727-142">F</span></span>  <br/> |<span data-ttu-id="77727-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="77727-143">xsd:string</span></span>  <br/> |<span data-ttu-id="77727-144">可选</span><span class="sxs-lookup"><span data-stu-id="77727-144">optional</span></span>  <br/> | <span data-ttu-id="77727-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="77727-145">Represents the element's formula.</span></span> <span data-ttu-id="77727-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="77727-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="77727-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="77727-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="77727-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="77727-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="77727-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="77727-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="77727-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="77727-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="77727-151">N</span><span class="sxs-lookup"><span data-stu-id="77727-151">N</span></span>  <br/> |<span data-ttu-id="77727-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="77727-152">xsd:string</span></span>  <br/> |<span data-ttu-id="77727-153">必需</span><span class="sxs-lookup"><span data-stu-id="77727-153">required</span></span>  <br/> |<span data-ttu-id="77727-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="77727-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="77727-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="77727-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="77727-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="77727-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="77727-157">U</span><span class="sxs-lookup"><span data-stu-id="77727-157">U</span></span>  <br/> |<span data-ttu-id="77727-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="77727-158">xsd:string</span></span>  <br/> |<span data-ttu-id="77727-159">可选</span><span class="sxs-lookup"><span data-stu-id="77727-159">optional</span></span>  <br/> |<span data-ttu-id="77727-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="77727-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="77727-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="77727-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="77727-162">部分</span><span class="sxs-lookup"><span data-stu-id="77727-162">V</span></span>  <br/> |<span data-ttu-id="77727-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="77727-163">xsd:string</span></span>  <br/> |<span data-ttu-id="77727-164">可选</span><span class="sxs-lookup"><span data-stu-id="77727-164">optional</span></span>  <br/> |<span data-ttu-id="77727-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="77727-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="77727-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="77727-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="77727-167">注解</span><span class="sxs-lookup"><span data-stu-id="77727-167">Remarks</span></span>

<span data-ttu-id="77727-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="77727-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="77727-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="77727-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="77727-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="77727-170">**Value**</span></span>|<span data-ttu-id="77727-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="77727-171">**Description**</span></span>|<span data-ttu-id="77727-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="77727-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77727-173">X</span><span class="sxs-lookup"><span data-stu-id="77727-173">X</span></span>  <br/> |<span data-ttu-id="77727-174">中心点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="77727-174">The x-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="77727-175">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-175">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="77727-176">Y</span><span class="sxs-lookup"><span data-stu-id="77727-176">Y</span></span>  <br/> |<span data-ttu-id="77727-177">中心点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="77727-177">The y-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="77727-178">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-178">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="77727-179">A</span><span class="sxs-lookup"><span data-stu-id="77727-179">A</span></span>  <br/> |<span data-ttu-id="77727-180">椭圆上第一个点的 x 坐标;与 B 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="77727-180">The x-coordinate of the first point on the ellipse; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="77727-181">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-181">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="77727-182">B</span><span class="sxs-lookup"><span data-stu-id="77727-182">B</span></span>  <br/> |<span data-ttu-id="77727-183">椭圆上第一个点的 y 坐标;与 A 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="77727-183">The y-coordinate of the first point on the ellipse; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="77727-184">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-184">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="77727-185">C</span><span class="sxs-lookup"><span data-stu-id="77727-185">C</span></span>  <br/> |<span data-ttu-id="77727-186">椭圆上第二个点的 x 坐标;与 D 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="77727-186">The x-coordinate of the second point on the ellipse; paired with y-coordinate represented by the D cell.</span></span>  <br/> |[<span data-ttu-id="77727-187">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-187">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="77727-188">D</span><span class="sxs-lookup"><span data-stu-id="77727-188">D</span></span>  <br/> |<span data-ttu-id="77727-189">椭圆上第二个点的 y 坐标;与 C 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="77727-189">The y-coordinate of the second point on the ellipse; paired with y-coordinate represented by the C cell.</span></span>  <br/> |[<span data-ttu-id="77727-190">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="77727-190">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
   

