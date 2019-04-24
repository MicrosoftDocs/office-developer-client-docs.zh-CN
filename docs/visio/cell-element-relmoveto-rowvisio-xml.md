---
title: Cell 元素 ("RelMoveTo" 行) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8e91497c-0aa1-2021-9317-cf989e5b84a3
description: 包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。
ms.openlocfilehash: cc81ea1b36541fe471807e83057e7aaaacb70d70
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339569"
---
# <a name="cell-element-relmoveto-row-visio-xml"></a><span data-ttu-id="4783e-103">Cell 元素 ("RelMoveTo" 行) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="4783e-103">Cell element (RelMoveTo Row) ('Visio XML')</span></span>

<span data-ttu-id="4783e-104">包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。</span><span class="sxs-lookup"><span data-stu-id="4783e-104">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4783e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4783e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4783e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4783e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4783e-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="4783e-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4783e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4783e-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4783e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4783e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4783e-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="4783e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4783e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4783e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4783e-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="4783e-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4783e-113">定义</span><span class="sxs-lookup"><span data-stu-id="4783e-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4783e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4783e-114">Elements and attributes</span></span>

<span data-ttu-id="4783e-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4783e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4783e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4783e-116">Parent elements</span></span>

|<span data-ttu-id="4783e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4783e-117">**Element**</span></span>|<span data-ttu-id="4783e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4783e-118">**Type**</span></span>|<span data-ttu-id="4783e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4783e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4783e-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="4783e-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="4783e-121">RelMoveTo_Type</span><span class="sxs-lookup"><span data-stu-id="4783e-121">RelMoveTo_Type</span></span>](relmoveto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4783e-122">包含形状的第一个顶点的 x 坐标或 y 坐标, 或路径中断开点后的第一个顶点的 x 坐标或 y 坐标 (相对于形状的高度和宽度)。</span><span class="sxs-lookup"><span data-stu-id="4783e-122">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4783e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4783e-123">Child elements</span></span>

|<span data-ttu-id="4783e-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4783e-124">**Element**</span></span>|<span data-ttu-id="4783e-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4783e-125">**Type**</span></span>|<span data-ttu-id="4783e-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4783e-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4783e-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="4783e-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4783e-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="4783e-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4783e-129">指定对页面的引用。</span><span class="sxs-lookup"><span data-stu-id="4783e-129">Specifies a reference to a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4783e-130">属性</span><span class="sxs-lookup"><span data-stu-id="4783e-130">Attributes</span></span>

|<span data-ttu-id="4783e-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="4783e-131">**Attribute**</span></span>|<span data-ttu-id="4783e-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="4783e-132">**Type**</span></span>|<span data-ttu-id="4783e-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="4783e-133">**Required**</span></span>|<span data-ttu-id="4783e-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="4783e-134">**Description**</span></span>|<span data-ttu-id="4783e-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4783e-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4783e-136">E</span><span class="sxs-lookup"><span data-stu-id="4783e-136">E</span></span>  <br/> |<span data-ttu-id="4783e-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4783e-137">xsd:string</span></span>  <br/> |<span data-ttu-id="4783e-138">可选</span><span class="sxs-lookup"><span data-stu-id="4783e-138">optional</span></span>  <br/> |<span data-ttu-id="4783e-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="4783e-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="4783e-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="4783e-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="4783e-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="4783e-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="4783e-142">F</span><span class="sxs-lookup"><span data-stu-id="4783e-142">F</span></span>  <br/> |<span data-ttu-id="4783e-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4783e-143">xsd:string</span></span>  <br/> |<span data-ttu-id="4783e-144">可选</span><span class="sxs-lookup"><span data-stu-id="4783e-144">optional</span></span>  <br/> | <span data-ttu-id="4783e-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="4783e-145">Represents the element's formula.</span></span> <span data-ttu-id="4783e-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="4783e-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="4783e-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="4783e-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="4783e-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="4783e-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="4783e-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="4783e-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="4783e-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="4783e-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="4783e-151">N</span><span class="sxs-lookup"><span data-stu-id="4783e-151">N</span></span>  <br/> |<span data-ttu-id="4783e-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4783e-152">xsd:string</span></span>  <br/> |<span data-ttu-id="4783e-153">必需</span><span class="sxs-lookup"><span data-stu-id="4783e-153">required</span></span>  <br/> |<span data-ttu-id="4783e-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="4783e-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="4783e-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="4783e-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="4783e-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="4783e-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="4783e-157">U</span><span class="sxs-lookup"><span data-stu-id="4783e-157">U</span></span>  <br/> |<span data-ttu-id="4783e-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4783e-158">xsd:string</span></span>  <br/> |<span data-ttu-id="4783e-159">可选</span><span class="sxs-lookup"><span data-stu-id="4783e-159">optional</span></span>  <br/> |<span data-ttu-id="4783e-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="4783e-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="4783e-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="4783e-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="4783e-162">部分</span><span class="sxs-lookup"><span data-stu-id="4783e-162">V</span></span>  <br/> |<span data-ttu-id="4783e-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4783e-163">xsd:string</span></span>  <br/> |<span data-ttu-id="4783e-164">可选</span><span class="sxs-lookup"><span data-stu-id="4783e-164">optional</span></span>  <br/> |<span data-ttu-id="4783e-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="4783e-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="4783e-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="4783e-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4783e-167">注解</span><span class="sxs-lookup"><span data-stu-id="4783e-167">Remarks</span></span>

<span data-ttu-id="4783e-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="4783e-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="4783e-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="4783e-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="4783e-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="4783e-170">**Value**</span></span>|<span data-ttu-id="4783e-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="4783e-171">**Description**</span></span>|<span data-ttu-id="4783e-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4783e-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4783e-173">X</span><span class="sxs-lookup"><span data-stu-id="4783e-173">X</span></span>  <br/> |<span data-ttu-id="4783e-174">如果**RelMoveTo**行是该内容中的第一行, 则**X**单元格表示形状的第一个顶点相对于形状宽度的 X 坐标。</span><span class="sxs-lookup"><span data-stu-id="4783e-174">If the **RelMoveTo** row is the first row in the section, the **X** cell represents the x-coordinate of the first vertex of a shape relative to the width of the shape.</span></span> <span data-ttu-id="4783e-175">如果**RelMoveTo**行出现在两行之间, 则**X**单元格表示路径中断开处后的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="4783e-175">If the **RelMoveTo** row appears between two rows, the **X** cell represents the x-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="4783e-176">RelMoveTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="4783e-176">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
|<span data-ttu-id="4783e-177">Y</span><span class="sxs-lookup"><span data-stu-id="4783e-177">Y</span></span>  <br/> |<span data-ttu-id="4783e-178">如果**RelMoveTo**行是该内容中的第一行, 则**Y**单元格表示形状的第一个顶点相对于形状的高度的 Y 坐标。</span><span class="sxs-lookup"><span data-stu-id="4783e-178">If the **RelMoveTo** row is the first row in the section, the **Y** cell represents the y-coordinate of the first vertex of a shape relative to the height of the shape.</span></span> <span data-ttu-id="4783e-179">如果**RelMoveTo**行出现在两行之间, 则**Y**单元格表示路径中断开处后的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="4783e-179">If the **RelMoveTo** row appears between two rows, the **Y** cell represents the y-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="4783e-180">RelMoveTo 行 ("Geometry" 部分)</span><span class="sxs-lookup"><span data-stu-id="4783e-180">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
   

