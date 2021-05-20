---
title: 'Cell 元素 (PolyLineTo Row)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a62fbb51-e2a7-cdae-3516-5ce9ba30f26d
description: 包含折线或折线公式的最后一个点的 x 坐标或 y 坐标。
ms.openlocfilehash: b85784a41f4192895f17390f5473757c4bb09166
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539458"
---
# <a name="cell-element-polylineto-row-visio-xml"></a><span data-ttu-id="b7b3d-103">Cell 元素 (PolyLineTo Row)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="b7b3d-103">Cell element (PolyLineTo Row) (Visio XML)</span></span>

<span data-ttu-id="b7b3d-104">包含折线或折线公式的最后一个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-104">Contains x- or y-coordinates of the last point of a polyline or a polyline formula.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b7b3d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b7b3d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b7b3d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b7b3d-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="b7b3d-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b7b3d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b7b3d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b7b3d-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b7b3d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b7b3d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b7b3d-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="b7b3d-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b7b3d-113">定义</span><span class="sxs-lookup"><span data-stu-id="b7b3d-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b7b3d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b7b3d-114">Elements and attributes</span></span>

<span data-ttu-id="b7b3d-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b7b3d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b7b3d-116">Parent elements</span></span>

|<span data-ttu-id="b7b3d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-117">**Element**</span></span>|<span data-ttu-id="b7b3d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-118">**Type**</span></span>|<span data-ttu-id="b7b3d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b7b3d-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="b7b3d-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="b7b3d-121">PolylineTo_Type</span><span class="sxs-lookup"><span data-stu-id="b7b3d-121">PolylineTo_Type</span></span>](polylineto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b7b3d-122">包含折线或折线公式的最后一个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-122">Contains x- or y-coordinates of the last point of a polyline or a polyline formula.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b7b3d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b7b3d-123">Child elements</span></span>

|<span data-ttu-id="b7b3d-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-124">**Element**</span></span>|<span data-ttu-id="b7b3d-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-125">**Type**</span></span>|<span data-ttu-id="b7b3d-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b7b3d-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="b7b3d-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b7b3d-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="b7b3d-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b7b3d-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b7b3d-130">属性</span><span class="sxs-lookup"><span data-stu-id="b7b3d-130">Attributes</span></span>

|<span data-ttu-id="b7b3d-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-131">**Attribute**</span></span>|<span data-ttu-id="b7b3d-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-132">**Type**</span></span>|<span data-ttu-id="b7b3d-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-133">**Required**</span></span>|<span data-ttu-id="b7b3d-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-134">**Description**</span></span>|<span data-ttu-id="b7b3d-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7b3d-136">E</span><span class="sxs-lookup"><span data-stu-id="b7b3d-136">E</span></span>  <br/> |<span data-ttu-id="b7b3d-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b7b3d-137">xsd:string</span></span>  <br/> |<span data-ttu-id="b7b3d-138">可选</span><span class="sxs-lookup"><span data-stu-id="b7b3d-138">optional</span></span>  <br/> |<span data-ttu-id="b7b3d-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="b7b3d-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="b7b3d-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="b7b3d-142">F</span><span class="sxs-lookup"><span data-stu-id="b7b3d-142">F</span></span>  <br/> |<span data-ttu-id="b7b3d-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b7b3d-143">xsd:string</span></span>  <br/> |<span data-ttu-id="b7b3d-144">可选</span><span class="sxs-lookup"><span data-stu-id="b7b3d-144">optional</span></span>  <br/> | <span data-ttu-id="b7b3d-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-145">Represents the element's formula.</span></span> <span data-ttu-id="b7b3d-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="b7b3d-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="b7b3d-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="b7b3d-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="b7b3d-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="b7b3d-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="b7b3d-150">公式。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="b7b3d-151">N</span><span class="sxs-lookup"><span data-stu-id="b7b3d-151">N</span></span>  <br/> |<span data-ttu-id="b7b3d-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b7b3d-152">xsd:string</span></span>  <br/> |<span data-ttu-id="b7b3d-153">必需</span><span class="sxs-lookup"><span data-stu-id="b7b3d-153">required</span></span>  <br/> |<span data-ttu-id="b7b3d-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="b7b3d-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="b7b3d-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="b7b3d-157">U</span><span class="sxs-lookup"><span data-stu-id="b7b3d-157">U</span></span>  <br/> |<span data-ttu-id="b7b3d-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b7b3d-158">xsd:string</span></span>  <br/> |<span data-ttu-id="b7b3d-159">可选</span><span class="sxs-lookup"><span data-stu-id="b7b3d-159">optional</span></span>  <br/> |<span data-ttu-id="b7b3d-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="b7b3d-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="b7b3d-162">V</span><span class="sxs-lookup"><span data-stu-id="b7b3d-162">V</span></span>  <br/> |<span data-ttu-id="b7b3d-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="b7b3d-163">xsd:string</span></span>  <br/> |<span data-ttu-id="b7b3d-164">可选</span><span class="sxs-lookup"><span data-stu-id="b7b3d-164">optional</span></span>  <br/> |<span data-ttu-id="b7b3d-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="b7b3d-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b7b3d-167">备注</span><span class="sxs-lookup"><span data-stu-id="b7b3d-167">Remarks</span></span>

<span data-ttu-id="b7b3d-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="b7b3d-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="b7b3d-170">**值**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-170">**Value**</span></span>|<span data-ttu-id="b7b3d-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-171">**Description**</span></span>|<span data-ttu-id="b7b3d-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b7b3d-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7b3d-173">X</span><span class="sxs-lookup"><span data-stu-id="b7b3d-173">X</span></span>  <br/> |<span data-ttu-id="b7b3d-174">折线终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-174">The x-coordinate of the ending vertex of a polyline.</span></span>  <br/> |[<span data-ttu-id="b7b3d-175">PolylineTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b7b3d-175">PolylineTo Row (Geometry Section)</span></span>](polylineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="b7b3d-176">Y</span><span class="sxs-lookup"><span data-stu-id="b7b3d-176">Y</span></span>  <br/> |<span data-ttu-id="b7b3d-177">折线终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-177">The y-coordinate of the ending vertex of a polyline.</span></span>  <br/> |[<span data-ttu-id="b7b3d-178">PolylineTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b7b3d-178">PolylineTo Row (Geometry Section)</span></span>](polylineto-row-geometry-section.md) <br/> |
|<span data-ttu-id="b7b3d-179">A</span><span class="sxs-lookup"><span data-stu-id="b7b3d-179">A</span></span>  <br/> |<span data-ttu-id="b7b3d-180">折线公式。</span><span class="sxs-lookup"><span data-stu-id="b7b3d-180">The polyline formula.</span></span>  <br/> |[<span data-ttu-id="b7b3d-181">PolylineTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b7b3d-181">PolylineTo Row (Geometry Section)</span></span>](polylineto-row-geometry-section.md) <br/> |
   

