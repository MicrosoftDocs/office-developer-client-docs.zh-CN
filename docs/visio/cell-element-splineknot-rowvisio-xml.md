---
title: 单元格元素 （SplineKnot 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 61faf0d6-c0a2-9350-8712-7a450591afad
description: 包含 x 坐标或 y 坐标样条控制点或样条节点。
ms.openlocfilehash: 14a62fba7d900f1d15a21b4a348c9affda6cad05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779842"
---
# <a name="cell-element-splineknot-row-visio-xml"></a><span data-ttu-id="7a768-103">单元格元素 （SplineKnot 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7a768-103">Cell element (SplineKnot Row) ('Visio XML')</span></span>

<span data-ttu-id="7a768-104">包含 x 坐标或 y 坐标样条控制点或样条节点。</span><span class="sxs-lookup"><span data-stu-id="7a768-104">Contains x- or y-coordinates for a spline's control point or a spline's knot.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7a768-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7a768-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7a768-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7a768-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7a768-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="7a768-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7a768-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7a768-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7a768-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7a768-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7a768-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7a768-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7a768-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7a768-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7a768-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="7a768-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7a768-113">定义</span><span class="sxs-lookup"><span data-stu-id="7a768-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7a768-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7a768-114">Elements and attributes</span></span>

<span data-ttu-id="7a768-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7a768-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7a768-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7a768-116">Parent elements</span></span>

|<span data-ttu-id="7a768-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7a768-117">**Element**</span></span>|<span data-ttu-id="7a768-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7a768-118">**Type**</span></span>|<span data-ttu-id="7a768-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a768-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7a768-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="7a768-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="7a768-121">SplineKot_Type</span><span class="sxs-lookup"><span data-stu-id="7a768-121">SplineKot_Type</span></span>](splineknot_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7a768-122">包含 x 坐标或 y 坐标样条控制点或样条节点。</span><span class="sxs-lookup"><span data-stu-id="7a768-122">Contains x- or y-coordinates for a spline's control point or a spline's knot.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7a768-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7a768-123">Child elements</span></span>

|<span data-ttu-id="7a768-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="7a768-124">**Element**</span></span>|<span data-ttu-id="7a768-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="7a768-125">**Type**</span></span>|<span data-ttu-id="7a768-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a768-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7a768-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="7a768-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7a768-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="7a768-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7a768-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="7a768-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="7a768-130">属性</span><span class="sxs-lookup"><span data-stu-id="7a768-130">Attributes</span></span>

|<span data-ttu-id="7a768-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="7a768-131">**Attribute**</span></span>|<span data-ttu-id="7a768-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="7a768-132">**Type**</span></span>|<span data-ttu-id="7a768-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="7a768-133">**Required**</span></span>|<span data-ttu-id="7a768-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a768-134">**Description**</span></span>|<span data-ttu-id="7a768-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7a768-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a768-136">E</span><span class="sxs-lookup"><span data-stu-id="7a768-136">E</span></span>  <br/> |<span data-ttu-id="7a768-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7a768-137">xsd:string</span></span>  <br/> |<span data-ttu-id="7a768-138">可选</span><span class="sxs-lookup"><span data-stu-id="7a768-138">optional</span></span>  <br/> |<span data-ttu-id="7a768-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="7a768-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="7a768-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="7a768-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="7a768-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="7a768-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="7a768-142">F</span><span class="sxs-lookup"><span data-stu-id="7a768-142">F</span></span>  <br/> |<span data-ttu-id="7a768-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7a768-143">xsd:string</span></span>  <br/> |<span data-ttu-id="7a768-144">可选</span><span class="sxs-lookup"><span data-stu-id="7a768-144">optional</span></span>  <br/> | <span data-ttu-id="7a768-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="7a768-145">Represents the element's formula.</span></span> <span data-ttu-id="7a768-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="7a768-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="7a768-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="7a768-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="7a768-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="7a768-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="7a768-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="7a768-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="7a768-150">公式。</span><span class="sxs-lookup"><span data-stu-id="7a768-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="7a768-151">N</span><span class="sxs-lookup"><span data-stu-id="7a768-151">N</span></span>  <br/> |<span data-ttu-id="7a768-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7a768-152">xsd:string</span></span>  <br/> |<span data-ttu-id="7a768-153">必需</span><span class="sxs-lookup"><span data-stu-id="7a768-153">required</span></span>  <br/> |<span data-ttu-id="7a768-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7a768-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="7a768-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7a768-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="7a768-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="7a768-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="7a768-157">U</span><span class="sxs-lookup"><span data-stu-id="7a768-157">U</span></span>  <br/> |<span data-ttu-id="7a768-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7a768-158">xsd:string</span></span>  <br/> |<span data-ttu-id="7a768-159">可选</span><span class="sxs-lookup"><span data-stu-id="7a768-159">optional</span></span>  <br/> |<span data-ttu-id="7a768-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="7a768-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="7a768-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="7a768-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="7a768-162">V</span><span class="sxs-lookup"><span data-stu-id="7a768-162">V</span></span>  <br/> |<span data-ttu-id="7a768-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="7a768-163">xsd:string</span></span>  <br/> |<span data-ttu-id="7a768-164">可选</span><span class="sxs-lookup"><span data-stu-id="7a768-164">optional</span></span>  <br/> |<span data-ttu-id="7a768-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7a768-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="7a768-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7a768-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7a768-167">备注</span><span class="sxs-lookup"><span data-stu-id="7a768-167">Remarks</span></span>

<span data-ttu-id="7a768-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="7a768-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="7a768-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="7a768-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="7a768-170">**值**</span><span class="sxs-lookup"><span data-stu-id="7a768-170">**Value**</span></span>|<span data-ttu-id="7a768-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="7a768-171">**Description**</span></span>|<span data-ttu-id="7a768-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7a768-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a768-173">X</span><span class="sxs-lookup"><span data-stu-id="7a768-173">X</span></span>  <br/> |<span data-ttu-id="7a768-174">控制点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="7a768-174">The x-coordinate of a control point.</span></span>  <br/> |[<span data-ttu-id="7a768-175">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7a768-175">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
|<span data-ttu-id="7a768-176">Y</span><span class="sxs-lookup"><span data-stu-id="7a768-176">Y</span></span>  <br/> |<span data-ttu-id="7a768-177">控制点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="7a768-177">The y-coordinate of a control point.</span></span>  <br/> |[<span data-ttu-id="7a768-178">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7a768-178">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
|<span data-ttu-id="7a768-179">A</span><span class="sxs-lookup"><span data-stu-id="7a768-179">A</span></span>  <br/> |<span data-ttu-id="7a768-180">样条的节点之一（最后一个节点或前两个节点除外）。</span><span class="sxs-lookup"><span data-stu-id="7a768-180">One of the spline's knots (other than the last one or the first two).</span></span>  <br/> |[<span data-ttu-id="7a768-181">SplineKnot Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="7a768-181">SplineKnot Row (Geometry Section)</span></span>](splineknot-row-geometry-section.md) <br/> |
   

