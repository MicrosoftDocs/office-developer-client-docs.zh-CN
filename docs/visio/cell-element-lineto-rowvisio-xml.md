---
title: 'Cell 元素 (LineTo 行)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 64f2494d-2de7-6bc5-0db4-91b952bdcb5e
description: 包含直线段终顶点的 x 或 y 坐标。
ms.openlocfilehash: 4b1628549e659712a1c2e79ae0fbf53d594e18f9
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539507"
---
# <a name="cell-element-lineto-row-visio-xml"></a><span data-ttu-id="3f3c4-103">Cell 元素 (LineTo 行)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="3f3c4-103">Cell element (LineTo Row) (Visio XML)</span></span>

<span data-ttu-id="3f3c4-104">包含直线段终顶点的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-104">Contains x-or y-coordinates of the ending vertex of a straight line segment.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="3f3c4-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="3f3c4-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3f3c4-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-106">**Element type**</span></span> <br/> |[<span data-ttu-id="3f3c4-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="3f3c4-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="3f3c4-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="3f3c4-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-109">**Schema file**</span></span> <br/> |<span data-ttu-id="3f3c4-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="3f3c4-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="3f3c4-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-111">**Document parts**</span></span> <br/> |<span data-ttu-id="3f3c4-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="3f3c4-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3f3c4-113">定义</span><span class="sxs-lookup"><span data-stu-id="3f3c4-113">Definition</span></span>

```XML
< xs:element name="Cell"  type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3f3c4-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3f3c4-114">Elements and attributes</span></span>

<span data-ttu-id="3f3c4-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="3f3c4-116">父元素</span><span class="sxs-lookup"><span data-stu-id="3f3c4-116">Parent elements</span></span>

|<span data-ttu-id="3f3c4-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-117">**Element**</span></span>|<span data-ttu-id="3f3c4-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-118">**Type**</span></span>|<span data-ttu-id="3f3c4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3f3c4-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="3f3c4-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="3f3c4-121">LineTo_Type</span><span class="sxs-lookup"><span data-stu-id="3f3c4-121">LineTo_Type</span></span>](lineto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="3f3c4-122">包含直线段终顶点的 x 或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-122">Contains x-or y-coordinates of the ending vertex of a straight line segment.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="3f3c4-123">子元素</span><span class="sxs-lookup"><span data-stu-id="3f3c4-123">Child elements</span></span>

|<span data-ttu-id="3f3c4-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-124">**Element**</span></span>|<span data-ttu-id="3f3c4-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-125">**Type**</span></span>|<span data-ttu-id="3f3c4-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3f3c4-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="3f3c4-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3f3c4-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="3f3c4-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="3f3c4-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="3f3c4-130">属性</span><span class="sxs-lookup"><span data-stu-id="3f3c4-130">Attributes</span></span>

|<span data-ttu-id="3f3c4-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-131">**Attribute**</span></span>|<span data-ttu-id="3f3c4-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-132">**Type**</span></span>|<span data-ttu-id="3f3c4-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-133">**Required**</span></span>|<span data-ttu-id="3f3c4-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-134">**Description**</span></span>|<span data-ttu-id="3f3c4-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f3c4-136">E</span><span class="sxs-lookup"><span data-stu-id="3f3c4-136">E</span></span>  <br/> |<span data-ttu-id="3f3c4-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="3f3c4-137">xsd:string</span></span>  <br/> |<span data-ttu-id="3f3c4-138">可选</span><span class="sxs-lookup"><span data-stu-id="3f3c4-138">optional</span></span>  <br/> |<span data-ttu-id="3f3c4-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="3f3c4-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="3f3c4-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="3f3c4-142">F</span><span class="sxs-lookup"><span data-stu-id="3f3c4-142">F</span></span>  <br/> |<span data-ttu-id="3f3c4-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="3f3c4-143">xsd:string</span></span>  <br/> |<span data-ttu-id="3f3c4-144">可选</span><span class="sxs-lookup"><span data-stu-id="3f3c4-144">optional</span></span>  <br/> | <span data-ttu-id="3f3c4-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-145">Represents the element's formula.</span></span> <span data-ttu-id="3f3c4-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="3f3c4-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="3f3c4-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="3f3c4-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="3f3c4-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="3f3c4-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="3f3c4-150">公式。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="3f3c4-151">N</span><span class="sxs-lookup"><span data-stu-id="3f3c4-151">N</span></span>  <br/> |<span data-ttu-id="3f3c4-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="3f3c4-152">xsd:string</span></span>  <br/> |<span data-ttu-id="3f3c4-153">必需</span><span class="sxs-lookup"><span data-stu-id="3f3c4-153">required</span></span>  <br/> |<span data-ttu-id="3f3c4-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="3f3c4-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="3f3c4-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="3f3c4-157">U</span><span class="sxs-lookup"><span data-stu-id="3f3c4-157">U</span></span>  <br/> |<span data-ttu-id="3f3c4-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="3f3c4-158">xsd:string</span></span>  <br/> |<span data-ttu-id="3f3c4-159">可选</span><span class="sxs-lookup"><span data-stu-id="3f3c4-159">optional</span></span>  <br/> |<span data-ttu-id="3f3c4-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="3f3c4-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="3f3c4-162">V</span><span class="sxs-lookup"><span data-stu-id="3f3c4-162">V</span></span>  <br/> |<span data-ttu-id="3f3c4-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="3f3c4-163">xsd:string</span></span>  <br/> |<span data-ttu-id="3f3c4-164">可选</span><span class="sxs-lookup"><span data-stu-id="3f3c4-164">optional</span></span>  <br/> |<span data-ttu-id="3f3c4-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="3f3c4-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3f3c4-167">备注</span><span class="sxs-lookup"><span data-stu-id="3f3c4-167">Remarks</span></span>

<span data-ttu-id="3f3c4-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="3f3c4-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="3f3c4-170">**值**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-170">**Value**</span></span>|<span data-ttu-id="3f3c4-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-171">**Description**</span></span>|<span data-ttu-id="3f3c4-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="3f3c4-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f3c4-173">X</span><span class="sxs-lookup"><span data-stu-id="3f3c4-173">X</span></span>  <br/> |<span data-ttu-id="3f3c4-174">直线段终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-174">The x-coordinate of the ending vertex of a straight line segment.</span></span>  <br/> |[<span data-ttu-id="3f3c4-175">LineTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="3f3c4-175">LineTo Row (Geometry Section)</span></span>](lineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="3f3c4-176">Y</span><span class="sxs-lookup"><span data-stu-id="3f3c4-176">Y</span></span>  <br/> |<span data-ttu-id="3f3c4-177">直线段终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="3f3c4-177">The y-coordinate of the ending vertex of a straight line segment.</span></span>  <br/> |[<span data-ttu-id="3f3c4-178">LineTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="3f3c4-178">LineTo Row (Geometry Section)</span></span>](lineto-row-geometry-section.md) <br/> |
   

