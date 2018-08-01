---
title: 单元格元素 （RelMoveTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8e91497c-0aa1-2021-9317-cf989e5b84a3
description: 包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。
ms.openlocfilehash: 9cfc4c1a811598dea72c1487b56edd876d82e257
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779848"
---
# <a name="cell-element-relmoveto-row-visio-xml"></a><span data-ttu-id="07435-103">单元格元素 （RelMoveTo 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="07435-103">Cell element (RelMoveTo Row) ('Visio XML')</span></span>

<span data-ttu-id="07435-104">包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。</span><span class="sxs-lookup"><span data-stu-id="07435-104">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="07435-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="07435-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="07435-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="07435-106">**Element type**</span></span> <br/> |[<span data-ttu-id="07435-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="07435-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="07435-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="07435-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="07435-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="07435-109">**Schema file**</span></span> <br/> |<span data-ttu-id="07435-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="07435-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="07435-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="07435-111">**Document parts**</span></span> <br/> |<span data-ttu-id="07435-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="07435-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="07435-113">定义</span><span class="sxs-lookup"><span data-stu-id="07435-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="07435-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="07435-114">Elements and attributes</span></span>

<span data-ttu-id="07435-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="07435-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="07435-116">父元素</span><span class="sxs-lookup"><span data-stu-id="07435-116">Parent elements</span></span>

|<span data-ttu-id="07435-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="07435-117">**Element**</span></span>|<span data-ttu-id="07435-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="07435-118">**Type**</span></span>|<span data-ttu-id="07435-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="07435-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07435-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="07435-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="07435-121">RelMoveTo_Type</span><span class="sxs-lookup"><span data-stu-id="07435-121">RelMoveTo_Type</span></span>](relmoveto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07435-122">包含后的高度和宽度的形状的相对路径中断开的 x 坐标或 y 坐标形状的第一个顶点的 x 坐标或 y 坐标的第一个顶点。</span><span class="sxs-lookup"><span data-stu-id="07435-122">Contains the x- or y-coordinates of the first vertex of a shape, or the x- or y-coordinates of the first vertex after a break in a path, relative to the height and width of the shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="07435-123">子元素</span><span class="sxs-lookup"><span data-stu-id="07435-123">Child elements</span></span>

|<span data-ttu-id="07435-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="07435-124">**Element**</span></span>|<span data-ttu-id="07435-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="07435-125">**Type**</span></span>|<span data-ttu-id="07435-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="07435-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07435-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="07435-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="07435-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="07435-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07435-129">指定向页面的引用。</span><span class="sxs-lookup"><span data-stu-id="07435-129">Specifies a reference to a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="07435-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="07435-130">Attributes</span></span>

|<span data-ttu-id="07435-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="07435-131">**Attribute**</span></span>|<span data-ttu-id="07435-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="07435-132">**Type**</span></span>|<span data-ttu-id="07435-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="07435-133">**Required**</span></span>|<span data-ttu-id="07435-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="07435-134">**Description**</span></span>|<span data-ttu-id="07435-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="07435-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07435-136">E</span><span class="sxs-lookup"><span data-stu-id="07435-136">E</span></span>  <br/> |<span data-ttu-id="07435-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07435-137">xsd:string</span></span>  <br/> |<span data-ttu-id="07435-138">可选</span><span class="sxs-lookup"><span data-stu-id="07435-138">optional</span></span>  <br/> |<span data-ttu-id="07435-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="07435-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="07435-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="07435-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="07435-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="07435-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="07435-142">F</span><span class="sxs-lookup"><span data-stu-id="07435-142">F</span></span>  <br/> |<span data-ttu-id="07435-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07435-143">xsd:string</span></span>  <br/> |<span data-ttu-id="07435-144">可选</span><span class="sxs-lookup"><span data-stu-id="07435-144">optional</span></span>  <br/> | <span data-ttu-id="07435-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="07435-145">Represents the element's formula.</span></span> <span data-ttu-id="07435-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="07435-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="07435-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="07435-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="07435-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="07435-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="07435-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="07435-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="07435-150">公式。</span><span class="sxs-lookup"><span data-stu-id="07435-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="07435-151">N</span><span class="sxs-lookup"><span data-stu-id="07435-151">N</span></span>  <br/> |<span data-ttu-id="07435-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07435-152">xsd:string</span></span>  <br/> |<span data-ttu-id="07435-153">必需</span><span class="sxs-lookup"><span data-stu-id="07435-153">required</span></span>  <br/> |<span data-ttu-id="07435-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="07435-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="07435-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="07435-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="07435-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="07435-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="07435-157">U</span><span class="sxs-lookup"><span data-stu-id="07435-157">U</span></span>  <br/> |<span data-ttu-id="07435-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07435-158">xsd:string</span></span>  <br/> |<span data-ttu-id="07435-159">可选</span><span class="sxs-lookup"><span data-stu-id="07435-159">optional</span></span>  <br/> |<span data-ttu-id="07435-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="07435-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="07435-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="07435-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="07435-162">V</span><span class="sxs-lookup"><span data-stu-id="07435-162">V</span></span>  <br/> |<span data-ttu-id="07435-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07435-163">xsd:string</span></span>  <br/> |<span data-ttu-id="07435-164">可选</span><span class="sxs-lookup"><span data-stu-id="07435-164">optional</span></span>  <br/> |<span data-ttu-id="07435-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="07435-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="07435-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="07435-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07435-167">说明</span><span class="sxs-lookup"><span data-stu-id="07435-167">Remarks</span></span>

<span data-ttu-id="07435-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="07435-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="07435-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="07435-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="07435-170">**值**</span><span class="sxs-lookup"><span data-stu-id="07435-170">**Value**</span></span>|<span data-ttu-id="07435-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="07435-171">**Description**</span></span>|<span data-ttu-id="07435-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="07435-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07435-173">X</span><span class="sxs-lookup"><span data-stu-id="07435-173">X</span></span>  <br/> |<span data-ttu-id="07435-174">如果**RelMoveTo**行是该节中的第一行，则**X**单元格表示形状相对于形状的宽度的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="07435-174">If the **RelMoveTo** row is the first row in the section, the **X** cell represents the x-coordinate of the first vertex of a shape relative to the width of the shape.</span></span> <span data-ttu-id="07435-175">如果**RelMoveTo**行出现在两行之间，则**X**单元格后路径中断开表示的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="07435-175">If the **RelMoveTo** row appears between two rows, the **X** cell represents the x-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="07435-176">RelMoveTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="07435-176">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
|<span data-ttu-id="07435-177">Y</span><span class="sxs-lookup"><span data-stu-id="07435-177">Y</span></span>  <br/> |<span data-ttu-id="07435-178">如果**RelMoveTo**行是该节中的第一行，则**Y**单元格表示形状相对于形状的高度的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="07435-178">If the **RelMoveTo** row is the first row in the section, the **Y** cell represents the y-coordinate of the first vertex of a shape relative to the height of the shape.</span></span> <span data-ttu-id="07435-179">如果**RelMoveTo**行出现在两行之间，则**Y**单元格后路径中断开表示的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="07435-179">If the **RelMoveTo** row appears between two rows, the **Y** cell represents the y-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="07435-180">RelMoveTo 行（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="07435-180">RelMoveTo Row (Geometry Section)</span></span>](relmoveto-row-geometry-section.md) <br/> |
   

