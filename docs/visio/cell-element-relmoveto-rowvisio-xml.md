---
title: 'Xml (RelMoveTo 行)  (Visio Cell 元素) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8e91497c-0aa1-2021-9317-cf989e5b84a3
description: 包含形状的第一个顶点的 x 坐标或 y 坐标，或者路径中中断后的第一个顶点的 x 或 y 坐标（相对于形状的高度和宽度）。
ms.openlocfilehash: 6ec7990887ed59ae229e88b6ad02a7759c770700
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539402"
---
# <a name="cell-element-relmoveto-row-visio-xml"></a><span data-ttu-id="6df18-103">Xml (RelMoveTo 行)  (Visio Cell 元素) </span><span class="sxs-lookup"><span data-stu-id="6df18-103">Cell element (RelMoveTo Row) (Visio XML)</span></span>

<span data-ttu-id="6df18-104">包含形状的第一个顶点的 x 坐标或 y 坐标，或者路径中中断后的第一个顶点的 x 或 y 坐标（相对于形状的高度和宽度）。</span><span class="sxs-lookup"><span data-stu-id="6df18-104">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6df18-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6df18-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6df18-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6df18-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6df18-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="6df18-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6df18-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6df18-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6df18-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6df18-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6df18-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6df18-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6df18-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6df18-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6df18-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="6df18-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6df18-113">定义</span><span class="sxs-lookup"><span data-stu-id="6df18-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6df18-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6df18-114">Elements and attributes</span></span>

<span data-ttu-id="6df18-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6df18-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6df18-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6df18-116">Parent elements</span></span>

|<span data-ttu-id="6df18-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6df18-117">**Element**</span></span>|<span data-ttu-id="6df18-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6df18-118">**Type**</span></span>|<span data-ttu-id="6df18-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6df18-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6df18-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="6df18-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="6df18-121">RelMoveTo_Type</span><span class="sxs-lookup"><span data-stu-id="6df18-121">RelMoveTo_Type</span></span>](relmoveto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6df18-122">包含形状的第一个顶点的 x 坐标或 y 坐标，或者路径中中断后的第一个顶点的 x 或 y 坐标（相对于形状的高度和宽度）。</span><span class="sxs-lookup"><span data-stu-id="6df18-122">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6df18-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6df18-123">Child elements</span></span>

|<span data-ttu-id="6df18-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="6df18-124">**Element**</span></span>|<span data-ttu-id="6df18-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="6df18-125">**Type**</span></span>|<span data-ttu-id="6df18-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="6df18-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6df18-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="6df18-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6df18-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="6df18-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6df18-129">指定对页面的引用。</span><span class="sxs-lookup"><span data-stu-id="6df18-129">Specifies a reference to a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="6df18-130">属性</span><span class="sxs-lookup"><span data-stu-id="6df18-130">Attributes</span></span>

|<span data-ttu-id="6df18-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="6df18-131">**Attribute**</span></span>|<span data-ttu-id="6df18-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="6df18-132">**Type**</span></span>|<span data-ttu-id="6df18-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="6df18-133">**Required**</span></span>|<span data-ttu-id="6df18-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="6df18-134">**Description**</span></span>|<span data-ttu-id="6df18-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6df18-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6df18-136">E</span><span class="sxs-lookup"><span data-stu-id="6df18-136">E</span></span>  <br/> |<span data-ttu-id="6df18-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6df18-137">xsd:string</span></span>  <br/> |<span data-ttu-id="6df18-138">可选</span><span class="sxs-lookup"><span data-stu-id="6df18-138">optional</span></span>  <br/> |<span data-ttu-id="6df18-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="6df18-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="6df18-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="6df18-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="6df18-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="6df18-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="6df18-142">F</span><span class="sxs-lookup"><span data-stu-id="6df18-142">F</span></span>  <br/> |<span data-ttu-id="6df18-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6df18-143">xsd:string</span></span>  <br/> |<span data-ttu-id="6df18-144">可选</span><span class="sxs-lookup"><span data-stu-id="6df18-144">optional</span></span>  <br/> | <span data-ttu-id="6df18-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="6df18-145">Represents the element's formula.</span></span> <span data-ttu-id="6df18-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="6df18-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="6df18-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="6df18-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="6df18-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="6df18-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="6df18-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="6df18-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="6df18-150">公式。</span><span class="sxs-lookup"><span data-stu-id="6df18-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="6df18-151">N</span><span class="sxs-lookup"><span data-stu-id="6df18-151">N</span></span>  <br/> |<span data-ttu-id="6df18-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6df18-152">xsd:string</span></span>  <br/> |<span data-ttu-id="6df18-153">必需</span><span class="sxs-lookup"><span data-stu-id="6df18-153">required</span></span>  <br/> |<span data-ttu-id="6df18-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="6df18-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="6df18-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="6df18-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="6df18-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="6df18-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="6df18-157">U</span><span class="sxs-lookup"><span data-stu-id="6df18-157">U</span></span>  <br/> |<span data-ttu-id="6df18-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6df18-158">xsd:string</span></span>  <br/> |<span data-ttu-id="6df18-159">可选</span><span class="sxs-lookup"><span data-stu-id="6df18-159">optional</span></span>  <br/> |<span data-ttu-id="6df18-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="6df18-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="6df18-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="6df18-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="6df18-162">V</span><span class="sxs-lookup"><span data-stu-id="6df18-162">V</span></span>  <br/> |<span data-ttu-id="6df18-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6df18-163">xsd:string</span></span>  <br/> |<span data-ttu-id="6df18-164">可选</span><span class="sxs-lookup"><span data-stu-id="6df18-164">optional</span></span>  <br/> |<span data-ttu-id="6df18-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="6df18-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="6df18-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="6df18-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6df18-167">备注</span><span class="sxs-lookup"><span data-stu-id="6df18-167">Remarks</span></span>

<span data-ttu-id="6df18-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="6df18-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="6df18-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6df18-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="6df18-170">**值**</span><span class="sxs-lookup"><span data-stu-id="6df18-170">**Value**</span></span>|<span data-ttu-id="6df18-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="6df18-171">**Description**</span></span>|<span data-ttu-id="6df18-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="6df18-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6df18-173">X</span><span class="sxs-lookup"><span data-stu-id="6df18-173">X</span></span>  <br/> |<span data-ttu-id="6df18-174">如果 **RelMoveTo** 行是该内容的第一行， **则 X** 单元格代表形状的第一个顶点相对于形状宽度的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="6df18-174">If the **RelMoveTo** row is the first row in the section, the **X** cell represents the x-coordinate of the first vertex of a shape relative to the width of the shape.</span></span> <span data-ttu-id="6df18-175">如果 **RelMoveTo** 行出现在两行之间， **则 X** 单元格表示路径中断开处后的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="6df18-175">If the **RelMoveTo** row appears between two rows, the **X** cell represents the x-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="6df18-176">RelMoveTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="6df18-176">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
|<span data-ttu-id="6df18-177">Y</span><span class="sxs-lookup"><span data-stu-id="6df18-177">Y</span></span>  <br/> |<span data-ttu-id="6df18-178">如果 **RelMoveTo** 行是该内容的第一行， **则 Y** 单元格表示形状的第一个顶点相对于形状高度的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="6df18-178">If the **RelMoveTo** row is the first row in the section, the **Y** cell represents the y-coordinate of the first vertex of a shape relative to the height of the shape.</span></span> <span data-ttu-id="6df18-179">如果 **RelMoveTo** 行出现在两行之间， **则 Y** 单元格表示路径中中断后的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="6df18-179">If the **RelMoveTo** row appears between two rows, the **Y** cell represents the y-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="6df18-180">RelMoveTo Row (Geometry Section) </span><span class="sxs-lookup"><span data-stu-id="6df18-180">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
   

