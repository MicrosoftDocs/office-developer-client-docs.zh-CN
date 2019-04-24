---
title: Cell 元素 ("ArcTo" 行) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 69f1a0cc-90fe-4b49-653c-bba4a1a2b1b2
description: 包含 x 坐标、y 坐标或圆弧的曲线。
ms.openlocfilehash: 709251c40299425d59df97fc0c48901bb0204167
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356132"
---
# <a name="cell-element-arcto-row-visio-xml"></a><span data-ttu-id="cb0b7-103">Cell 元素 ("ArcTo" 行) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="cb0b7-103">Cell element (ArcTo Row) ('Visio XML')</span></span>

<span data-ttu-id="cb0b7-104">包含 x 坐标、y 坐标或圆弧的曲线。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-104">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="cb0b7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="cb0b7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cb0b7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="cb0b7-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="cb0b7-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="cb0b7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="cb0b7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="cb0b7-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="cb0b7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="cb0b7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="cb0b7-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="cb0b7-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="cb0b7-113">定义</span><span class="sxs-lookup"><span data-stu-id="cb0b7-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="cb0b7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="cb0b7-114">Elements and attributes</span></span>

<span data-ttu-id="cb0b7-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="cb0b7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="cb0b7-116">Parent elements</span></span>

|<span data-ttu-id="cb0b7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-117">**Element**</span></span>|<span data-ttu-id="cb0b7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-118">**Type**</span></span>|<span data-ttu-id="cb0b7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="cb0b7-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="cb0b7-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="cb0b7-121">ArcTo_Type</span><span class="sxs-lookup"><span data-stu-id="cb0b7-121">ArcTo_Type</span></span>](arcto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="cb0b7-122">包含圆弧的 x 坐标、y 坐标和弓。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-122">Contains the x- and y-coordinates and bow of a circular arc.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="cb0b7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="cb0b7-123">Child elements</span></span>

|<span data-ttu-id="cb0b7-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-124">**Element**</span></span>|<span data-ttu-id="cb0b7-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-125">**Type**</span></span>|<span data-ttu-id="cb0b7-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="cb0b7-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="cb0b7-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="cb0b7-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="cb0b7-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="cb0b7-129">包含 x 坐标、y 坐标或圆弧的曲线。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-129">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="cb0b7-130">属性</span><span class="sxs-lookup"><span data-stu-id="cb0b7-130">Attributes</span></span>

|<span data-ttu-id="cb0b7-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-131">**Attribute**</span></span>|<span data-ttu-id="cb0b7-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-132">**Type**</span></span>|<span data-ttu-id="cb0b7-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-133">**Required**</span></span>|<span data-ttu-id="cb0b7-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-134">**Description**</span></span>|<span data-ttu-id="cb0b7-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cb0b7-136">E</span><span class="sxs-lookup"><span data-stu-id="cb0b7-136">E</span></span>  <br/> |<span data-ttu-id="cb0b7-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb0b7-137">xsd:string</span></span>  <br/> |<span data-ttu-id="cb0b7-138">可选</span><span class="sxs-lookup"><span data-stu-id="cb0b7-138">optional</span></span>  <br/> |<span data-ttu-id="cb0b7-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="cb0b7-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="cb0b7-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="cb0b7-142">F</span><span class="sxs-lookup"><span data-stu-id="cb0b7-142">F</span></span>  <br/> |<span data-ttu-id="cb0b7-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb0b7-143">xsd:string</span></span>  <br/> |<span data-ttu-id="cb0b7-144">可选</span><span class="sxs-lookup"><span data-stu-id="cb0b7-144">optional</span></span>  <br/> | <span data-ttu-id="cb0b7-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-145">Represents the element's formula.</span></span> <span data-ttu-id="cb0b7-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="cb0b7-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="cb0b7-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="cb0b7-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="cb0b7-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="cb0b7-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="cb0b7-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="cb0b7-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="cb0b7-151">N</span><span class="sxs-lookup"><span data-stu-id="cb0b7-151">N</span></span>  <br/> |<span data-ttu-id="cb0b7-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb0b7-152">xsd:string</span></span>  <br/> |<span data-ttu-id="cb0b7-153">必需</span><span class="sxs-lookup"><span data-stu-id="cb0b7-153">required</span></span>  <br/> |<span data-ttu-id="cb0b7-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="cb0b7-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="cb0b7-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="cb0b7-157">U</span><span class="sxs-lookup"><span data-stu-id="cb0b7-157">U</span></span>  <br/> |<span data-ttu-id="cb0b7-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb0b7-158">xsd:string</span></span>  <br/> |<span data-ttu-id="cb0b7-159">可选</span><span class="sxs-lookup"><span data-stu-id="cb0b7-159">optional</span></span>  <br/> |<span data-ttu-id="cb0b7-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="cb0b7-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="cb0b7-162">部分</span><span class="sxs-lookup"><span data-stu-id="cb0b7-162">V</span></span>  <br/> |<span data-ttu-id="cb0b7-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cb0b7-163">xsd:string</span></span>  <br/> |<span data-ttu-id="cb0b7-164">可选</span><span class="sxs-lookup"><span data-stu-id="cb0b7-164">optional</span></span>  <br/> |<span data-ttu-id="cb0b7-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="cb0b7-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cb0b7-167">注解</span><span class="sxs-lookup"><span data-stu-id="cb0b7-167">Remarks</span></span>

<span data-ttu-id="cb0b7-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="cb0b7-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="cb0b7-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-170">**Value**</span></span>|<span data-ttu-id="cb0b7-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-171">**Description**</span></span>|<span data-ttu-id="cb0b7-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cb0b7-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb0b7-173">A</span><span class="sxs-lookup"><span data-stu-id="cb0b7-173">A</span></span>  <br/> |<span data-ttu-id="cb0b7-174">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-174">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |[<span data-ttu-id="cb0b7-175">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="cb0b7-175">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="cb0b7-176">X</span><span class="sxs-lookup"><span data-stu-id="cb0b7-176">X</span></span>  <br/> |<span data-ttu-id="cb0b7-177">弧形终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-177">The x-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="cb0b7-178">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="cb0b7-178">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="cb0b7-179">Y</span><span class="sxs-lookup"><span data-stu-id="cb0b7-179">Y</span></span>  <br/> |<span data-ttu-id="cb0b7-180">弧形终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="cb0b7-180">The y-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="cb0b7-181">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="cb0b7-181">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
   

