---
title: Cell 元素 ("ArcTo" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 69f1a0cc-90fe-4b49-653c-bba4a1a2b1b2
description: 包含 x 坐标、y 坐标或圆弧的曲线。
ms.openlocfilehash: 6d744366cda7db0f3950ed0962c7ba5bd01b8e36
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538821"
---
# <a name="cell-element-arcto-row-visio-xml"></a><span data-ttu-id="9c2b1-103">Cell 元素 ("ArcTo" 行) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9c2b1-103">Cell element (ArcTo Row) (Visio XML)</span></span>

<span data-ttu-id="9c2b1-104">包含 x 坐标、y 坐标或圆弧的曲线。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-104">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9c2b1-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9c2b1-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9c2b1-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9c2b1-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="9c2b1-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9c2b1-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9c2b1-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9c2b1-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="9c2b1-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9c2b1-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9c2b1-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="9c2b1-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9c2b1-113">定义</span><span class="sxs-lookup"><span data-stu-id="9c2b1-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9c2b1-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9c2b1-114">Elements and attributes</span></span>

<span data-ttu-id="9c2b1-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9c2b1-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9c2b1-116">Parent elements</span></span>

|<span data-ttu-id="9c2b1-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-117">**Element**</span></span>|<span data-ttu-id="9c2b1-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-118">**Type**</span></span>|<span data-ttu-id="9c2b1-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9c2b1-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="9c2b1-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="9c2b1-121">ArcTo_Type</span><span class="sxs-lookup"><span data-stu-id="9c2b1-121">ArcTo_Type</span></span>](arcto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9c2b1-122">包含圆弧的 x 坐标、y 坐标和弓。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-122">Contains the x- and y-coordinates and bow of a circular arc.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9c2b1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9c2b1-123">Child elements</span></span>

|<span data-ttu-id="9c2b1-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-124">**Element**</span></span>|<span data-ttu-id="9c2b1-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-125">**Type**</span></span>|<span data-ttu-id="9c2b1-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9c2b1-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="9c2b1-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9c2b1-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="9c2b1-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9c2b1-129">包含 x 坐标、y 坐标或圆弧的曲线。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-129">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="9c2b1-130">属性</span><span class="sxs-lookup"><span data-stu-id="9c2b1-130">Attributes</span></span>

|<span data-ttu-id="9c2b1-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-131">**Attribute**</span></span>|<span data-ttu-id="9c2b1-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-132">**Type**</span></span>|<span data-ttu-id="9c2b1-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-133">**Required**</span></span>|<span data-ttu-id="9c2b1-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-134">**Description**</span></span>|<span data-ttu-id="9c2b1-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c2b1-136">E</span><span class="sxs-lookup"><span data-stu-id="9c2b1-136">E</span></span>  <br/> |<span data-ttu-id="9c2b1-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9c2b1-137">xsd:string</span></span>  <br/> |<span data-ttu-id="9c2b1-138">可选</span><span class="sxs-lookup"><span data-stu-id="9c2b1-138">optional</span></span>  <br/> |<span data-ttu-id="9c2b1-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="9c2b1-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="9c2b1-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="9c2b1-142">F</span><span class="sxs-lookup"><span data-stu-id="9c2b1-142">F</span></span>  <br/> |<span data-ttu-id="9c2b1-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9c2b1-143">xsd:string</span></span>  <br/> |<span data-ttu-id="9c2b1-144">可选</span><span class="sxs-lookup"><span data-stu-id="9c2b1-144">optional</span></span>  <br/> | <span data-ttu-id="9c2b1-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-145">Represents the element's formula.</span></span> <span data-ttu-id="9c2b1-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="9c2b1-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="9c2b1-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="9c2b1-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="9c2b1-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="9c2b1-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="9c2b1-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="9c2b1-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="9c2b1-151">N</span><span class="sxs-lookup"><span data-stu-id="9c2b1-151">N</span></span>  <br/> |<span data-ttu-id="9c2b1-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9c2b1-152">xsd:string</span></span>  <br/> |<span data-ttu-id="9c2b1-153">必需</span><span class="sxs-lookup"><span data-stu-id="9c2b1-153">required</span></span>  <br/> |<span data-ttu-id="9c2b1-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="9c2b1-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="9c2b1-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="9c2b1-157">U</span><span class="sxs-lookup"><span data-stu-id="9c2b1-157">U</span></span>  <br/> |<span data-ttu-id="9c2b1-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9c2b1-158">xsd:string</span></span>  <br/> |<span data-ttu-id="9c2b1-159">可选</span><span class="sxs-lookup"><span data-stu-id="9c2b1-159">optional</span></span>  <br/> |<span data-ttu-id="9c2b1-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="9c2b1-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="9c2b1-162">部分</span><span class="sxs-lookup"><span data-stu-id="9c2b1-162">V</span></span>  <br/> |<span data-ttu-id="9c2b1-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9c2b1-163">xsd:string</span></span>  <br/> |<span data-ttu-id="9c2b1-164">可选</span><span class="sxs-lookup"><span data-stu-id="9c2b1-164">optional</span></span>  <br/> |<span data-ttu-id="9c2b1-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="9c2b1-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9c2b1-167">备注</span><span class="sxs-lookup"><span data-stu-id="9c2b1-167">Remarks</span></span>

<span data-ttu-id="9c2b1-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="9c2b1-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="9c2b1-170">**值**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-170">**Value**</span></span>|<span data-ttu-id="9c2b1-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-171">**Description**</span></span>|<span data-ttu-id="9c2b1-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9c2b1-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c2b1-173">A</span><span class="sxs-lookup"><span data-stu-id="9c2b1-173">A</span></span>  <br/> |<span data-ttu-id="9c2b1-174">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-174">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |[<span data-ttu-id="9c2b1-175">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="9c2b1-175">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="9c2b1-176">X</span><span class="sxs-lookup"><span data-stu-id="9c2b1-176">X</span></span>  <br/> |<span data-ttu-id="9c2b1-177">弧形终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-177">The x-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="9c2b1-178">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="9c2b1-178">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="9c2b1-179">Y</span><span class="sxs-lookup"><span data-stu-id="9c2b1-179">Y</span></span>  <br/> |<span data-ttu-id="9c2b1-180">弧形终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="9c2b1-180">The y-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="9c2b1-181">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="9c2b1-181">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
   

