---
title: 'Cell 元素 (SplineKnot 行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 61faf0d6-c0a2-9350-8712-7a450591afad
description: 包含样条的控制点或样条节点的 x 坐标或 y 坐标。
ms.openlocfilehash: 4eb6e2ce47adae20738c0d210ad2dc30f362200d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539367"
---
# <a name="cell-element-splineknot-row-visio-xml"></a><span data-ttu-id="7547b-103">Cell 元素 (SplineKnot 行)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="7547b-103">Cell element (SplineKnot Row) (Visio XML)</span></span>

<span data-ttu-id="7547b-104">包含样条的控制点或样条节点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="7547b-104">Contains x- or y-coordinates for a spline's control point or a spline's knot.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7547b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7547b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7547b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7547b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7547b-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="7547b-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7547b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7547b-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7547b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7547b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7547b-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7547b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7547b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7547b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7547b-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="7547b-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7547b-113">定义</span><span class="sxs-lookup"><span data-stu-id="7547b-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7547b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7547b-114">Elements and attributes</span></span>

<span data-ttu-id="7547b-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7547b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7547b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7547b-116">Parent elements</span></span>

|<span data-ttu-id="7547b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7547b-117">**Element**</span></span>|<span data-ttu-id="7547b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7547b-118">**Type**</span></span>|<span data-ttu-id="7547b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7547b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7547b-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="7547b-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="7547b-121">SplineKot_Type</span><span class="sxs-lookup"><span data-stu-id="7547b-121">SplineKot_Type</span></span>](splineknot_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7547b-122">包含样条的控制点或样条节点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="7547b-122">Contains x- or y-coordinates for a spline's control point or a spline's knot.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7547b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7547b-123">Child elements</span></span>

|<span data-ttu-id="7547b-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="7547b-124">**Element**</span></span>|<span data-ttu-id="7547b-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="7547b-125">**Type**</span></span>|<span data-ttu-id="7547b-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="7547b-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7547b-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="7547b-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7547b-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="7547b-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7547b-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="7547b-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="7547b-130">属性</span><span class="sxs-lookup"><span data-stu-id="7547b-130">Attributes</span></span>

|<span data-ttu-id="7547b-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="7547b-131">**Attribute**</span></span>|<span data-ttu-id="7547b-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="7547b-132">**Type**</span></span>|<span data-ttu-id="7547b-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="7547b-133">**Required**</span></span>|<span data-ttu-id="7547b-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="7547b-134">**Description**</span></span>|<span data-ttu-id="7547b-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7547b-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7547b-136">E</span><span class="sxs-lookup"><span data-stu-id="7547b-136">E</span></span>  <br/> |<span data-ttu-id="7547b-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7547b-137">xsd:string</span></span>  <br/> |<span data-ttu-id="7547b-138">可选</span><span class="sxs-lookup"><span data-stu-id="7547b-138">optional</span></span>  <br/> |<span data-ttu-id="7547b-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="7547b-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="7547b-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="7547b-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="7547b-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="7547b-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="7547b-142">F</span><span class="sxs-lookup"><span data-stu-id="7547b-142">F</span></span>  <br/> |<span data-ttu-id="7547b-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7547b-143">xsd:string</span></span>  <br/> |<span data-ttu-id="7547b-144">可选</span><span class="sxs-lookup"><span data-stu-id="7547b-144">optional</span></span>  <br/> | <span data-ttu-id="7547b-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="7547b-145">Represents the element's formula.</span></span> <span data-ttu-id="7547b-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="7547b-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="7547b-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="7547b-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="7547b-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="7547b-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="7547b-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="7547b-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="7547b-150">公式。</span><span class="sxs-lookup"><span data-stu-id="7547b-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="7547b-151">N</span><span class="sxs-lookup"><span data-stu-id="7547b-151">N</span></span>  <br/> |<span data-ttu-id="7547b-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7547b-152">xsd:string</span></span>  <br/> |<span data-ttu-id="7547b-153">必需</span><span class="sxs-lookup"><span data-stu-id="7547b-153">required</span></span>  <br/> |<span data-ttu-id="7547b-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7547b-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="7547b-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7547b-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="7547b-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="7547b-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="7547b-157">U</span><span class="sxs-lookup"><span data-stu-id="7547b-157">U</span></span>  <br/> |<span data-ttu-id="7547b-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7547b-158">xsd:string</span></span>  <br/> |<span data-ttu-id="7547b-159">可选</span><span class="sxs-lookup"><span data-stu-id="7547b-159">optional</span></span>  <br/> |<span data-ttu-id="7547b-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="7547b-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="7547b-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="7547b-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="7547b-162">V</span><span class="sxs-lookup"><span data-stu-id="7547b-162">V</span></span>  <br/> |<span data-ttu-id="7547b-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7547b-163">xsd:string</span></span>  <br/> |<span data-ttu-id="7547b-164">可选</span><span class="sxs-lookup"><span data-stu-id="7547b-164">optional</span></span>  <br/> |<span data-ttu-id="7547b-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7547b-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="7547b-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7547b-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7547b-167">备注</span><span class="sxs-lookup"><span data-stu-id="7547b-167">Remarks</span></span>

<span data-ttu-id="7547b-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="7547b-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="7547b-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="7547b-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="7547b-170">**值**</span><span class="sxs-lookup"><span data-stu-id="7547b-170">**Value**</span></span>|<span data-ttu-id="7547b-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="7547b-171">**Description**</span></span>|<span data-ttu-id="7547b-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7547b-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7547b-173">X</span><span class="sxs-lookup"><span data-stu-id="7547b-173">X</span></span>  <br/> |<span data-ttu-id="7547b-174">控制点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="7547b-174">The x-coordinate of a control point.</span></span>  <br/> |[<span data-ttu-id="7547b-175">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7547b-175">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
|<span data-ttu-id="7547b-176">Y</span><span class="sxs-lookup"><span data-stu-id="7547b-176">Y</span></span>  <br/> |<span data-ttu-id="7547b-177">控制点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="7547b-177">The y-coordinate of a control point.</span></span>  <br/> |[<span data-ttu-id="7547b-178">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7547b-178">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
|<span data-ttu-id="7547b-179">A</span><span class="sxs-lookup"><span data-stu-id="7547b-179">A</span></span>  <br/> |<span data-ttu-id="7547b-180">样条的节点之一（最后一个节点或前两个节点除外）。</span><span class="sxs-lookup"><span data-stu-id="7547b-180">One of the spline's knots (other than the last one or the first two).</span></span>  <br/> |[<span data-ttu-id="7547b-181">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7547b-181">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
   

