---
title: 'Cell 元素 (RelLineTo 行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 44d369f0-ab37-75ca-727e-b421d6f95ba7
description: 包含直线段终顶点相对于形状的宽度和高度的 x 或 y 坐标。
ms.openlocfilehash: 1a3277eac2b0f759d3da6cb93b5339f97a5ac876
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539416"
---
# <a name="cell-element-rellineto-row-visio-xml"></a><span data-ttu-id="d6805-103">Cell 元素 (RelLineTo 行)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="d6805-103">Cell element (RelLineTo Row) (Visio XML)</span></span>

<span data-ttu-id="d6805-104">包含直线段终顶点相对于形状的宽度和高度的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d6805-104">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d6805-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d6805-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d6805-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d6805-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d6805-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d6805-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d6805-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d6805-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d6805-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d6805-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d6805-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d6805-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d6805-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d6805-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d6805-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="d6805-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d6805-113">定义</span><span class="sxs-lookup"><span data-stu-id="d6805-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d6805-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d6805-114">Elements and attributes</span></span>

<span data-ttu-id="d6805-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d6805-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d6805-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d6805-116">Parent elements</span></span>

|<span data-ttu-id="d6805-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d6805-117">**Element**</span></span>|<span data-ttu-id="d6805-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6805-118">**Type**</span></span>|<span data-ttu-id="d6805-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6805-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d6805-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="d6805-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d6805-121">RelLineTo_Type</span><span class="sxs-lookup"><span data-stu-id="d6805-121">RelLineTo_Type</span></span>](rellineto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d6805-122">包含直线段终顶点相对于形状的宽度和高度的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d6805-122">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d6805-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d6805-123">Child elements</span></span>

|<span data-ttu-id="d6805-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d6805-124">**Element**</span></span>|<span data-ttu-id="d6805-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6805-125">**Type**</span></span>|<span data-ttu-id="d6805-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6805-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d6805-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="d6805-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d6805-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="d6805-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d6805-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="d6805-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d6805-130">属性</span><span class="sxs-lookup"><span data-stu-id="d6805-130">Attributes</span></span>

|<span data-ttu-id="d6805-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="d6805-131">**Attribute**</span></span>|<span data-ttu-id="d6805-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6805-132">**Type**</span></span>|<span data-ttu-id="d6805-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="d6805-133">**Required**</span></span>|<span data-ttu-id="d6805-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="d6805-134">**Description**</span></span>|<span data-ttu-id="d6805-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d6805-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d6805-136">E</span><span class="sxs-lookup"><span data-stu-id="d6805-136">E</span></span>  <br/> |<span data-ttu-id="d6805-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d6805-137">xsd:string</span></span>  <br/> |<span data-ttu-id="d6805-138">可选</span><span class="sxs-lookup"><span data-stu-id="d6805-138">optional</span></span>  <br/> |<span data-ttu-id="d6805-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="d6805-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="d6805-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="d6805-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="d6805-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="d6805-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="d6805-142">F</span><span class="sxs-lookup"><span data-stu-id="d6805-142">F</span></span>  <br/> |<span data-ttu-id="d6805-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d6805-143">xsd:string</span></span>  <br/> |<span data-ttu-id="d6805-144">可选</span><span class="sxs-lookup"><span data-stu-id="d6805-144">optional</span></span>  <br/> | <span data-ttu-id="d6805-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="d6805-145">Represents the element's formula.</span></span> <span data-ttu-id="d6805-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="d6805-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="d6805-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="d6805-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="d6805-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="d6805-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="d6805-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="d6805-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="d6805-150">公式。</span><span class="sxs-lookup"><span data-stu-id="d6805-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="d6805-151">N</span><span class="sxs-lookup"><span data-stu-id="d6805-151">N</span></span>  <br/> |<span data-ttu-id="d6805-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d6805-152">xsd:string</span></span>  <br/> |<span data-ttu-id="d6805-153">必需</span><span class="sxs-lookup"><span data-stu-id="d6805-153">required</span></span>  <br/> |<span data-ttu-id="d6805-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d6805-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="d6805-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d6805-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="d6805-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="d6805-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="d6805-157">U</span><span class="sxs-lookup"><span data-stu-id="d6805-157">U</span></span>  <br/> |<span data-ttu-id="d6805-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d6805-158">xsd:string</span></span>  <br/> |<span data-ttu-id="d6805-159">可选</span><span class="sxs-lookup"><span data-stu-id="d6805-159">optional</span></span>  <br/> |<span data-ttu-id="d6805-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="d6805-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="d6805-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="d6805-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="d6805-162">V</span><span class="sxs-lookup"><span data-stu-id="d6805-162">V</span></span>  <br/> |<span data-ttu-id="d6805-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d6805-163">xsd:string</span></span>  <br/> |<span data-ttu-id="d6805-164">可选</span><span class="sxs-lookup"><span data-stu-id="d6805-164">optional</span></span>  <br/> |<span data-ttu-id="d6805-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d6805-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="d6805-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d6805-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d6805-167">备注</span><span class="sxs-lookup"><span data-stu-id="d6805-167">Remarks</span></span>

<span data-ttu-id="d6805-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="d6805-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="d6805-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="d6805-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="d6805-170">**值**</span><span class="sxs-lookup"><span data-stu-id="d6805-170">**Value**</span></span>|<span data-ttu-id="d6805-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6805-171">**Description**</span></span>|<span data-ttu-id="d6805-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d6805-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6805-173">X</span><span class="sxs-lookup"><span data-stu-id="d6805-173">X</span></span>  <br/> |<span data-ttu-id="d6805-174">直线段终顶点相对于形状宽度的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="d6805-174">The x-coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |[<span data-ttu-id="d6805-175">RelLineTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="d6805-175">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="d6805-176">Y</span><span class="sxs-lookup"><span data-stu-id="d6805-176">Y</span></span>  <br/> |<span data-ttu-id="d6805-177">直线段终顶点相对于形状高度的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d6805-177">The y-coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |[<span data-ttu-id="d6805-178">RelLineTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="d6805-178">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
   

