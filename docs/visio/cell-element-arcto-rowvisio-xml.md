---
title: 'ArcTo (XML)  (Visio中的 Cell 元素) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 69f1a0cc-90fe-4b49-653c-bba4a1a2b1b2
description: 包含圆弧的 x 坐标、y 坐标或弓形。
ms.openlocfilehash: 6d744366cda7db0f3950ed0962c7ba5bd01b8e36
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538821"
---
# <a name="cell-element-arcto-row-visio-xml"></a><span data-ttu-id="472d5-103">ArcTo (XML)  (Visio中的 Cell 元素) </span><span class="sxs-lookup"><span data-stu-id="472d5-103">Cell element (ArcTo Row) (Visio XML)</span></span>

<span data-ttu-id="472d5-104">包含圆弧的 x 坐标、y 坐标或弓形。</span><span class="sxs-lookup"><span data-stu-id="472d5-104">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="472d5-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="472d5-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="472d5-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="472d5-106">**Element type**</span></span> <br/> |[<span data-ttu-id="472d5-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="472d5-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="472d5-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="472d5-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="472d5-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="472d5-109">**Schema file**</span></span> <br/> |<span data-ttu-id="472d5-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="472d5-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="472d5-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="472d5-111">**Document parts**</span></span> <br/> |<span data-ttu-id="472d5-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="472d5-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="472d5-113">定义</span><span class="sxs-lookup"><span data-stu-id="472d5-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="472d5-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="472d5-114">Elements and attributes</span></span>

<span data-ttu-id="472d5-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="472d5-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="472d5-116">父元素</span><span class="sxs-lookup"><span data-stu-id="472d5-116">Parent elements</span></span>

|<span data-ttu-id="472d5-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="472d5-117">**Element**</span></span>|<span data-ttu-id="472d5-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="472d5-118">**Type**</span></span>|<span data-ttu-id="472d5-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="472d5-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="472d5-120">Geometry (Row) </span><span class="sxs-lookup"><span data-stu-id="472d5-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="472d5-121">ArcTo_Type</span><span class="sxs-lookup"><span data-stu-id="472d5-121">ArcTo_Type</span></span>](arcto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="472d5-122">包含圆弧的 x 坐标、y 坐标和弓。</span><span class="sxs-lookup"><span data-stu-id="472d5-122">Contains the x- and y-coordinates and bow of a circular arc.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="472d5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="472d5-123">Child elements</span></span>

|<span data-ttu-id="472d5-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="472d5-124">**Element**</span></span>|<span data-ttu-id="472d5-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="472d5-125">**Type**</span></span>|<span data-ttu-id="472d5-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="472d5-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="472d5-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="472d5-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="472d5-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="472d5-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="472d5-129">包含圆弧的 x 坐标、y 坐标或弓形。</span><span class="sxs-lookup"><span data-stu-id="472d5-129">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="472d5-130">属性</span><span class="sxs-lookup"><span data-stu-id="472d5-130">Attributes</span></span>

|<span data-ttu-id="472d5-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="472d5-131">**Attribute**</span></span>|<span data-ttu-id="472d5-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="472d5-132">**Type**</span></span>|<span data-ttu-id="472d5-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="472d5-133">**Required**</span></span>|<span data-ttu-id="472d5-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="472d5-134">**Description**</span></span>|<span data-ttu-id="472d5-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="472d5-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="472d5-136">E</span><span class="sxs-lookup"><span data-stu-id="472d5-136">E</span></span>  <br/> |<span data-ttu-id="472d5-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="472d5-137">xsd:string</span></span>  <br/> |<span data-ttu-id="472d5-138">可选</span><span class="sxs-lookup"><span data-stu-id="472d5-138">optional</span></span>  <br/> |<span data-ttu-id="472d5-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="472d5-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="472d5-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="472d5-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="472d5-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="472d5-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="472d5-142">F</span><span class="sxs-lookup"><span data-stu-id="472d5-142">F</span></span>  <br/> |<span data-ttu-id="472d5-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="472d5-143">xsd:string</span></span>  <br/> |<span data-ttu-id="472d5-144">可选</span><span class="sxs-lookup"><span data-stu-id="472d5-144">optional</span></span>  <br/> | <span data-ttu-id="472d5-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="472d5-145">Represents the element's formula.</span></span> <span data-ttu-id="472d5-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="472d5-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="472d5-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="472d5-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="472d5-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="472d5-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="472d5-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="472d5-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="472d5-150">公式。</span><span class="sxs-lookup"><span data-stu-id="472d5-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="472d5-151">N</span><span class="sxs-lookup"><span data-stu-id="472d5-151">N</span></span>  <br/> |<span data-ttu-id="472d5-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="472d5-152">xsd:string</span></span>  <br/> |<span data-ttu-id="472d5-153">必需</span><span class="sxs-lookup"><span data-stu-id="472d5-153">required</span></span>  <br/> |<span data-ttu-id="472d5-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="472d5-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="472d5-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="472d5-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="472d5-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="472d5-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="472d5-157">U</span><span class="sxs-lookup"><span data-stu-id="472d5-157">U</span></span>  <br/> |<span data-ttu-id="472d5-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="472d5-158">xsd:string</span></span>  <br/> |<span data-ttu-id="472d5-159">可选</span><span class="sxs-lookup"><span data-stu-id="472d5-159">optional</span></span>  <br/> |<span data-ttu-id="472d5-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="472d5-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="472d5-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="472d5-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="472d5-162">V</span><span class="sxs-lookup"><span data-stu-id="472d5-162">V</span></span>  <br/> |<span data-ttu-id="472d5-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="472d5-163">xsd:string</span></span>  <br/> |<span data-ttu-id="472d5-164">可选</span><span class="sxs-lookup"><span data-stu-id="472d5-164">optional</span></span>  <br/> |<span data-ttu-id="472d5-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="472d5-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="472d5-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="472d5-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="472d5-167">备注</span><span class="sxs-lookup"><span data-stu-id="472d5-167">Remarks</span></span>

<span data-ttu-id="472d5-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="472d5-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="472d5-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="472d5-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="472d5-170">**值**</span><span class="sxs-lookup"><span data-stu-id="472d5-170">**Value**</span></span>|<span data-ttu-id="472d5-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="472d5-171">**Description**</span></span>|<span data-ttu-id="472d5-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="472d5-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="472d5-173">A</span><span class="sxs-lookup"><span data-stu-id="472d5-173">A</span></span>  <br/> |<span data-ttu-id="472d5-174">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="472d5-174">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |[<span data-ttu-id="472d5-175">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="472d5-175">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="472d5-176">X</span><span class="sxs-lookup"><span data-stu-id="472d5-176">X</span></span>  <br/> |<span data-ttu-id="472d5-177">弧形终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="472d5-177">The x-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="472d5-178">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="472d5-178">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="472d5-179">Y</span><span class="sxs-lookup"><span data-stu-id="472d5-179">Y</span></span>  <br/> |<span data-ttu-id="472d5-180">弧形终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="472d5-180">The y-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="472d5-181">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="472d5-181">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
   

