---
title: 单元格元素 （Ellipse 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 210e6731-7c94-90b1-c7c4-635df974fdb6
description: 包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。
ms.openlocfilehash: 75c3cf86b7c8668b70915117e1fc70b07d2cef0b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394387"
---
# <a name="cell-element-ellipse-row-visio-xml"></a><span data-ttu-id="abccb-103">单元格元素 （Ellipse 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="abccb-103">Cell element (Ellipse Row) ('Visio XML')</span></span>

<span data-ttu-id="abccb-104">包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。</span><span class="sxs-lookup"><span data-stu-id="abccb-104">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="abccb-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="abccb-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="abccb-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="abccb-106">**Element type**</span></span> <br/> |[<span data-ttu-id="abccb-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="abccb-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="abccb-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="abccb-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="abccb-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="abccb-109">**Schema file**</span></span> <br/> |<span data-ttu-id="abccb-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="abccb-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="abccb-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="abccb-111">**Document parts**</span></span> <br/> |<span data-ttu-id="abccb-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="abccb-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="abccb-113">定义</span><span class="sxs-lookup"><span data-stu-id="abccb-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="abccb-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="abccb-114">Elements and attributes</span></span>

<span data-ttu-id="abccb-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="abccb-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="abccb-116">父元素</span><span class="sxs-lookup"><span data-stu-id="abccb-116">Parent elements</span></span>

|<span data-ttu-id="abccb-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="abccb-117">**Element**</span></span>|<span data-ttu-id="abccb-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="abccb-118">**Type**</span></span>|<span data-ttu-id="abccb-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="abccb-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="abccb-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="abccb-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="abccb-121">Ellipse_Type</span><span class="sxs-lookup"><span data-stu-id="abccb-121">Ellipse_Type</span></span>](ellipse_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="abccb-122">包含 x 坐标或 y 坐标的椭圆中心点和椭圆上的两个点。</span><span class="sxs-lookup"><span data-stu-id="abccb-122">Contains the x- or y-coordinates of the ellipse's center point and two points on the ellipse.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="abccb-123">子元素</span><span class="sxs-lookup"><span data-stu-id="abccb-123">Child elements</span></span>

|<span data-ttu-id="abccb-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="abccb-124">**Element**</span></span>|<span data-ttu-id="abccb-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="abccb-125">**Type**</span></span>|<span data-ttu-id="abccb-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="abccb-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="abccb-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="abccb-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="abccb-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="abccb-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="abccb-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="abccb-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="abccb-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="abccb-130">Attributes</span></span>

|<span data-ttu-id="abccb-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="abccb-131">**Attribute**</span></span>|<span data-ttu-id="abccb-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="abccb-132">**Type**</span></span>|<span data-ttu-id="abccb-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="abccb-133">**Required**</span></span>|<span data-ttu-id="abccb-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="abccb-134">**Description**</span></span>|<span data-ttu-id="abccb-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="abccb-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="abccb-136">E</span><span class="sxs-lookup"><span data-stu-id="abccb-136">E</span></span>  <br/> |<span data-ttu-id="abccb-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="abccb-137">xsd:string</span></span>  <br/> |<span data-ttu-id="abccb-138">可选</span><span class="sxs-lookup"><span data-stu-id="abccb-138">optional</span></span>  <br/> |<span data-ttu-id="abccb-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="abccb-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="abccb-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="abccb-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="abccb-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="abccb-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="abccb-142">F</span><span class="sxs-lookup"><span data-stu-id="abccb-142">F</span></span>  <br/> |<span data-ttu-id="abccb-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="abccb-143">xsd:string</span></span>  <br/> |<span data-ttu-id="abccb-144">可选</span><span class="sxs-lookup"><span data-stu-id="abccb-144">optional</span></span>  <br/> | <span data-ttu-id="abccb-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="abccb-145">Represents the element's formula.</span></span> <span data-ttu-id="abccb-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="abccb-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="abccb-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="abccb-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="abccb-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="abccb-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="abccb-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="abccb-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="abccb-150">公式。</span><span class="sxs-lookup"><span data-stu-id="abccb-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="abccb-151">N</span><span class="sxs-lookup"><span data-stu-id="abccb-151">N</span></span>  <br/> |<span data-ttu-id="abccb-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="abccb-152">xsd:string</span></span>  <br/> |<span data-ttu-id="abccb-153">必需</span><span class="sxs-lookup"><span data-stu-id="abccb-153">required</span></span>  <br/> |<span data-ttu-id="abccb-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="abccb-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="abccb-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="abccb-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="abccb-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="abccb-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="abccb-157">U</span><span class="sxs-lookup"><span data-stu-id="abccb-157">U</span></span>  <br/> |<span data-ttu-id="abccb-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="abccb-158">xsd:string</span></span>  <br/> |<span data-ttu-id="abccb-159">可选</span><span class="sxs-lookup"><span data-stu-id="abccb-159">optional</span></span>  <br/> |<span data-ttu-id="abccb-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="abccb-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="abccb-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="abccb-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="abccb-162">V</span><span class="sxs-lookup"><span data-stu-id="abccb-162">V</span></span>  <br/> |<span data-ttu-id="abccb-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="abccb-163">xsd:string</span></span>  <br/> |<span data-ttu-id="abccb-164">可选</span><span class="sxs-lookup"><span data-stu-id="abccb-164">optional</span></span>  <br/> |<span data-ttu-id="abccb-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="abccb-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="abccb-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="abccb-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="abccb-167">说明</span><span class="sxs-lookup"><span data-stu-id="abccb-167">Remarks</span></span>

<span data-ttu-id="abccb-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="abccb-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="abccb-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="abccb-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="abccb-170">**值**</span><span class="sxs-lookup"><span data-stu-id="abccb-170">**Value**</span></span>|<span data-ttu-id="abccb-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="abccb-171">**Description**</span></span>|<span data-ttu-id="abccb-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="abccb-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abccb-173">X</span><span class="sxs-lookup"><span data-stu-id="abccb-173">X</span></span>  <br/> |<span data-ttu-id="abccb-174">中心点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="abccb-174">The x-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="abccb-175">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-175">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="abccb-176">Y</span><span class="sxs-lookup"><span data-stu-id="abccb-176">Y</span></span>  <br/> |<span data-ttu-id="abccb-177">中心点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="abccb-177">The y-coordinate of the center point.</span></span>  <br/> |[<span data-ttu-id="abccb-178">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-178">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="abccb-179">A</span><span class="sxs-lookup"><span data-stu-id="abccb-179">A</span></span>  <br/> |<span data-ttu-id="abccb-180">椭圆; 上的第一个点的 x 坐标与 B 单元格所表示的 y 轴坐标配对。</span><span class="sxs-lookup"><span data-stu-id="abccb-180">The x-coordinate of the first point on the ellipse; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="abccb-181">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-181">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="abccb-182">B</span><span class="sxs-lookup"><span data-stu-id="abccb-182">B</span></span>  <br/> |<span data-ttu-id="abccb-183">个椭圆; 上的第一个点的 y 坐标与 A 单元格所表示的 x 轴坐标配对。</span><span class="sxs-lookup"><span data-stu-id="abccb-183">The y-coordinate of the first point on the ellipse; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="abccb-184">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-184">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="abccb-185">C</span><span class="sxs-lookup"><span data-stu-id="abccb-185">C</span></span>  <br/> |<span data-ttu-id="abccb-186">椭圆; 上第二个点的 x 坐标与 D 单元格所表示的 y 轴坐标配对。</span><span class="sxs-lookup"><span data-stu-id="abccb-186">The x-coordinate of the second point on the ellipse; paired with y-coordinate represented by the D cell.</span></span>  <br/> |[<span data-ttu-id="abccb-187">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-187">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
|<span data-ttu-id="abccb-188">D</span><span class="sxs-lookup"><span data-stu-id="abccb-188">D</span></span>  <br/> |<span data-ttu-id="abccb-189">个椭圆; 上第二个点的 y 坐标与 C 单元格所表示的 y 轴坐标配对。</span><span class="sxs-lookup"><span data-stu-id="abccb-189">The y-coordinate of the second point on the ellipse; paired with y-coordinate represented by the C cell.</span></span>  <br/> |[<span data-ttu-id="abccb-190">Ellipse Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="abccb-190">Ellipse Row (Geometry Section)</span></span>](ellipse-row-geometry-section.md) <br/> |
   

