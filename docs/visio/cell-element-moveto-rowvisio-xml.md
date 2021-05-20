---
title: 'Cell 元素 (MoveTo 行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b3b2a08f-07a0-5f1c-4910-503229927816
description: 包含形状的第一个顶点的 x 坐标或 y 坐标，或表示路径中中断后的第一个顶点的 x 或 y 坐标。
ms.openlocfilehash: f0cbe7170bf4462b9aece211a149af396c132766
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539514"
---
# <a name="cell-element-moveto-row-visio-xml"></a><span data-ttu-id="fd8bd-103">Cell 元素 (MoveTo 行)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="fd8bd-103">Cell element (MoveTo Row) (Visio XML)</span></span>

<span data-ttu-id="fd8bd-104">包含形状的第一个顶点的 x 坐标或 y 坐标，或表示路径中中断后的第一个顶点的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-104">Contains the x- or y-coordinates of the first vertex of a shape, or represents the x- or y-coordinates of the first vertex after a break in a path.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fd8bd-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fd8bd-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fd8bd-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fd8bd-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="fd8bd-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fd8bd-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fd8bd-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fd8bd-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="fd8bd-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fd8bd-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fd8bd-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="fd8bd-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fd8bd-113">定义</span><span class="sxs-lookup"><span data-stu-id="fd8bd-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fd8bd-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fd8bd-114">Elements and attributes</span></span>

<span data-ttu-id="fd8bd-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fd8bd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fd8bd-116">Parent elements</span></span>

|<span data-ttu-id="fd8bd-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-117">**Element**</span></span>|<span data-ttu-id="fd8bd-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-118">**Type**</span></span>|<span data-ttu-id="fd8bd-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fd8bd-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="fd8bd-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="fd8bd-121">MoveTo_Type</span><span class="sxs-lookup"><span data-stu-id="fd8bd-121">MoveTo_Type</span></span>](moveto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fd8bd-122">包含形状的第一个顶点的 x 坐标或 y 坐标，或表示路径中中断后的第一个顶点的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-122">Contains the x- or y-coordinates of the first vertex of a shape, or represents the x- or y-coordinates of the first vertex after a break in a path.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fd8bd-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fd8bd-123">Child elements</span></span>

|<span data-ttu-id="fd8bd-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-124">**Element**</span></span>|<span data-ttu-id="fd8bd-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-125">**Type**</span></span>|<span data-ttu-id="fd8bd-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fd8bd-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="fd8bd-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fd8bd-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="fd8bd-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fd8bd-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="fd8bd-130">属性</span><span class="sxs-lookup"><span data-stu-id="fd8bd-130">Attributes</span></span>

|<span data-ttu-id="fd8bd-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-131">**Attribute**</span></span>|<span data-ttu-id="fd8bd-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-132">**Type**</span></span>|<span data-ttu-id="fd8bd-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-133">**Required**</span></span>|<span data-ttu-id="fd8bd-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-134">**Description**</span></span>|<span data-ttu-id="fd8bd-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd8bd-136">E</span><span class="sxs-lookup"><span data-stu-id="fd8bd-136">E</span></span>  <br/> |<span data-ttu-id="fd8bd-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd8bd-137">xsd:string</span></span>  <br/> |<span data-ttu-id="fd8bd-138">可选</span><span class="sxs-lookup"><span data-stu-id="fd8bd-138">optional</span></span>  <br/> |<span data-ttu-id="fd8bd-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="fd8bd-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="fd8bd-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="fd8bd-142">F</span><span class="sxs-lookup"><span data-stu-id="fd8bd-142">F</span></span>  <br/> |<span data-ttu-id="fd8bd-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd8bd-143">xsd:string</span></span>  <br/> |<span data-ttu-id="fd8bd-144">可选</span><span class="sxs-lookup"><span data-stu-id="fd8bd-144">optional</span></span>  <br/> | <span data-ttu-id="fd8bd-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-145">Represents the element's formula.</span></span> <span data-ttu-id="fd8bd-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="fd8bd-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="fd8bd-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="fd8bd-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="fd8bd-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="fd8bd-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="fd8bd-150">公式。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="fd8bd-151">N</span><span class="sxs-lookup"><span data-stu-id="fd8bd-151">N</span></span>  <br/> |<span data-ttu-id="fd8bd-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd8bd-152">xsd:string</span></span>  <br/> |<span data-ttu-id="fd8bd-153">必需</span><span class="sxs-lookup"><span data-stu-id="fd8bd-153">required</span></span>  <br/> |<span data-ttu-id="fd8bd-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="fd8bd-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="fd8bd-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="fd8bd-157">U</span><span class="sxs-lookup"><span data-stu-id="fd8bd-157">U</span></span>  <br/> |<span data-ttu-id="fd8bd-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd8bd-158">xsd:string</span></span>  <br/> |<span data-ttu-id="fd8bd-159">可选</span><span class="sxs-lookup"><span data-stu-id="fd8bd-159">optional</span></span>  <br/> |<span data-ttu-id="fd8bd-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="fd8bd-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="fd8bd-162">V</span><span class="sxs-lookup"><span data-stu-id="fd8bd-162">V</span></span>  <br/> |<span data-ttu-id="fd8bd-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd8bd-163">xsd:string</span></span>  <br/> |<span data-ttu-id="fd8bd-164">可选</span><span class="sxs-lookup"><span data-stu-id="fd8bd-164">optional</span></span>  <br/> |<span data-ttu-id="fd8bd-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="fd8bd-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fd8bd-167">备注</span><span class="sxs-lookup"><span data-stu-id="fd8bd-167">Remarks</span></span>

<span data-ttu-id="fd8bd-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="fd8bd-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="fd8bd-170">**值**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-170">**Value**</span></span>|<span data-ttu-id="fd8bd-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-171">**Description**</span></span>|<span data-ttu-id="fd8bd-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="fd8bd-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd8bd-173">X</span><span class="sxs-lookup"><span data-stu-id="fd8bd-173">X</span></span>  <br/> |<span data-ttu-id="fd8bd-174">如果 **MoveTo** 行是内容的第一行，则 **X** 单元格表示形状的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-174">If the **MoveTo** row is the first row in the section, the **X** cell represents the x-coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="fd8bd-175">如果 **MoveTo 行** 出现在两行之间， **则 X** 单元格表示路径中断开处后的第一个顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-175">If the **MoveTo** row appears between two rows, the **X** cell represents the x-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="fd8bd-176">MoveTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="fd8bd-176">MoveTo Row (Geometry Section)</span></span>](moveto-row-geometry-section.md) <br/> |
|<span data-ttu-id="fd8bd-177">Y</span><span class="sxs-lookup"><span data-stu-id="fd8bd-177">Y</span></span>  <br/> |<span data-ttu-id="fd8bd-178">如果 **MoveTo** 行是内容的第一行，则 **Y** 单元格表示形状的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-178">If the **MoveTo** row is the first row in the section, the **Y** cell represents the y-coordinate of the first vertex of a shape.</span></span> <span data-ttu-id="fd8bd-179">如果 **MoveTo** 行出现在两行之间， **则 Y** 单元格表示路径中中断后的第一个顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="fd8bd-179">If the **MoveTo** row appears between two rows, the **Y** cell represents the y-coordinate of the first vertex after the break in the path.</span></span>  <br/> |[<span data-ttu-id="fd8bd-180">MoveTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="fd8bd-180">MoveTo Row (Geometry Section)</span></span>](moveto-row-geometry-section.md) <br/> |
   

