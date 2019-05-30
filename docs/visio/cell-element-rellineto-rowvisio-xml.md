---
title: Cell 元素 ("RelLineTo" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 44d369f0-ab37-75ca-727e-b421d6f95ba7
description: 包含相对于形状的宽度和高度的直线段终顶点的 x 坐标或 y 坐标。
ms.openlocfilehash: 1a3277eac2b0f759d3da6cb93b5339f97a5ac876
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539416"
---
# <a name="cell-element-rellineto-row-visio-xml"></a><span data-ttu-id="d73ee-103">Cell 元素 ("RelLineTo" 行) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d73ee-103">Cell element (RelLineTo Row) (Visio XML)</span></span>

<span data-ttu-id="d73ee-104">包含相对于形状的宽度和高度的直线段终顶点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d73ee-104">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d73ee-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d73ee-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d73ee-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d73ee-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d73ee-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d73ee-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d73ee-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d73ee-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d73ee-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d73ee-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d73ee-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="d73ee-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d73ee-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d73ee-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d73ee-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="d73ee-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d73ee-113">定义</span><span class="sxs-lookup"><span data-stu-id="d73ee-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d73ee-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d73ee-114">Elements and attributes</span></span>

<span data-ttu-id="d73ee-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d73ee-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d73ee-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d73ee-116">Parent elements</span></span>

|<span data-ttu-id="d73ee-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d73ee-117">**Element**</span></span>|<span data-ttu-id="d73ee-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d73ee-118">**Type**</span></span>|<span data-ttu-id="d73ee-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d73ee-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d73ee-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="d73ee-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d73ee-121">RelLineTo_Type</span><span class="sxs-lookup"><span data-stu-id="d73ee-121">RelLineTo_Type</span></span>](rellineto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d73ee-122">包含相对于形状的宽度和高度的直线段终顶点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d73ee-122">Contains x-or y-coordinates of the ending vertex of a straight line segment relative to a shape's width and height.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d73ee-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d73ee-123">Child elements</span></span>

|<span data-ttu-id="d73ee-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d73ee-124">**Element**</span></span>|<span data-ttu-id="d73ee-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d73ee-125">**Type**</span></span>|<span data-ttu-id="d73ee-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d73ee-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d73ee-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="d73ee-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d73ee-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="d73ee-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d73ee-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="d73ee-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d73ee-130">属性</span><span class="sxs-lookup"><span data-stu-id="d73ee-130">Attributes</span></span>

|<span data-ttu-id="d73ee-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="d73ee-131">**Attribute**</span></span>|<span data-ttu-id="d73ee-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="d73ee-132">**Type**</span></span>|<span data-ttu-id="d73ee-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="d73ee-133">**Required**</span></span>|<span data-ttu-id="d73ee-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="d73ee-134">**Description**</span></span>|<span data-ttu-id="d73ee-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d73ee-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d73ee-136">E</span><span class="sxs-lookup"><span data-stu-id="d73ee-136">E</span></span>  <br/> |<span data-ttu-id="d73ee-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d73ee-137">xsd:string</span></span>  <br/> |<span data-ttu-id="d73ee-138">可选</span><span class="sxs-lookup"><span data-stu-id="d73ee-138">optional</span></span>  <br/> |<span data-ttu-id="d73ee-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="d73ee-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="d73ee-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="d73ee-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="d73ee-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="d73ee-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="d73ee-142">F</span><span class="sxs-lookup"><span data-stu-id="d73ee-142">F</span></span>  <br/> |<span data-ttu-id="d73ee-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d73ee-143">xsd:string</span></span>  <br/> |<span data-ttu-id="d73ee-144">可选</span><span class="sxs-lookup"><span data-stu-id="d73ee-144">optional</span></span>  <br/> | <span data-ttu-id="d73ee-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="d73ee-145">Represents the element's formula.</span></span> <span data-ttu-id="d73ee-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="d73ee-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="d73ee-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="d73ee-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="d73ee-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="d73ee-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="d73ee-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="d73ee-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="d73ee-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="d73ee-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="d73ee-151">N</span><span class="sxs-lookup"><span data-stu-id="d73ee-151">N</span></span>  <br/> |<span data-ttu-id="d73ee-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d73ee-152">xsd:string</span></span>  <br/> |<span data-ttu-id="d73ee-153">必需</span><span class="sxs-lookup"><span data-stu-id="d73ee-153">required</span></span>  <br/> |<span data-ttu-id="d73ee-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d73ee-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="d73ee-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d73ee-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="d73ee-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="d73ee-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="d73ee-157">U</span><span class="sxs-lookup"><span data-stu-id="d73ee-157">U</span></span>  <br/> |<span data-ttu-id="d73ee-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d73ee-158">xsd:string</span></span>  <br/> |<span data-ttu-id="d73ee-159">可选</span><span class="sxs-lookup"><span data-stu-id="d73ee-159">optional</span></span>  <br/> |<span data-ttu-id="d73ee-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="d73ee-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="d73ee-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="d73ee-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="d73ee-162">部分</span><span class="sxs-lookup"><span data-stu-id="d73ee-162">V</span></span>  <br/> |<span data-ttu-id="d73ee-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d73ee-163">xsd:string</span></span>  <br/> |<span data-ttu-id="d73ee-164">可选</span><span class="sxs-lookup"><span data-stu-id="d73ee-164">optional</span></span>  <br/> |<span data-ttu-id="d73ee-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d73ee-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="d73ee-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d73ee-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d73ee-167">备注</span><span class="sxs-lookup"><span data-stu-id="d73ee-167">Remarks</span></span>

<span data-ttu-id="d73ee-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="d73ee-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="d73ee-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="d73ee-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="d73ee-170">**值**</span><span class="sxs-lookup"><span data-stu-id="d73ee-170">**Value**</span></span>|<span data-ttu-id="d73ee-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="d73ee-171">**Description**</span></span>|<span data-ttu-id="d73ee-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d73ee-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d73ee-173">X</span><span class="sxs-lookup"><span data-stu-id="d73ee-173">X</span></span>  <br/> |<span data-ttu-id="d73ee-174">直线线段终顶点相对于形状宽度的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="d73ee-174">The x-coordinate of the ending vertex of a straight line segment relative to the shape's width.</span></span>  <br/> |[<span data-ttu-id="d73ee-175">RelLineTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="d73ee-175">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="d73ee-176">Y</span><span class="sxs-lookup"><span data-stu-id="d73ee-176">Y</span></span>  <br/> |<span data-ttu-id="d73ee-177">直线线段终顶点相对于形状高度的 y 轴坐标值。</span><span class="sxs-lookup"><span data-stu-id="d73ee-177">The y-coordinate of the ending vertex of a straight line segment relative to the shape's height.</span></span>  <br/> |[<span data-ttu-id="d73ee-178">RelLineTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="d73ee-178">RelLineTo Row (Geometry Section)</span></span>](rellineto-row-geometry-section.md) <br/> |
   

