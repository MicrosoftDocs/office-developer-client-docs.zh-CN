---
title: 单元格元素 （ArcTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 69f1a0cc-90fe-4b49-653c-bba4a1a2b1b2
description: 包含的 x 坐标、 y 坐标或圆弧弓。
ms.openlocfilehash: 709251c40299425d59df97fc0c48901bb0204167
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393059"
---
# <a name="cell-element-arcto-row-visio-xml"></a><span data-ttu-id="f41d2-103">单元格元素 （ArcTo 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f41d2-103">Cell element (ArcTo Row) ('Visio XML')</span></span>

<span data-ttu-id="f41d2-104">包含的 x 坐标、 y 坐标或圆弧弓。</span><span class="sxs-lookup"><span data-stu-id="f41d2-104">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f41d2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f41d2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f41d2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f41d2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f41d2-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f41d2-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f41d2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f41d2-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f41d2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f41d2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f41d2-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f41d2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f41d2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f41d2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f41d2-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="f41d2-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f41d2-113">定义</span><span class="sxs-lookup"><span data-stu-id="f41d2-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f41d2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f41d2-114">Elements and attributes</span></span>

<span data-ttu-id="f41d2-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f41d2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f41d2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f41d2-116">Parent elements</span></span>

|<span data-ttu-id="f41d2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f41d2-117">**Element**</span></span>|<span data-ttu-id="f41d2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f41d2-118">**Type**</span></span>|<span data-ttu-id="f41d2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f41d2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f41d2-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="f41d2-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f41d2-121">ArcTo_Type</span><span class="sxs-lookup"><span data-stu-id="f41d2-121">ArcTo_Type</span></span>](arcto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f41d2-122">包含圆弧的 x 坐标、y 坐标和弓。</span><span class="sxs-lookup"><span data-stu-id="f41d2-122">Contains the x- and y-coordinates and bow of a circular arc.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f41d2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f41d2-123">Child elements</span></span>

|<span data-ttu-id="f41d2-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f41d2-124">**Element**</span></span>|<span data-ttu-id="f41d2-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f41d2-125">**Type**</span></span>|<span data-ttu-id="f41d2-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f41d2-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f41d2-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="f41d2-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f41d2-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="f41d2-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f41d2-129">包含的 x 坐标、 y 坐标或圆弧弓。</span><span class="sxs-lookup"><span data-stu-id="f41d2-129">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f41d2-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="f41d2-130">Attributes</span></span>

|<span data-ttu-id="f41d2-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="f41d2-131">**Attribute**</span></span>|<span data-ttu-id="f41d2-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="f41d2-132">**Type**</span></span>|<span data-ttu-id="f41d2-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="f41d2-133">**Required**</span></span>|<span data-ttu-id="f41d2-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="f41d2-134">**Description**</span></span>|<span data-ttu-id="f41d2-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f41d2-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f41d2-136">E</span><span class="sxs-lookup"><span data-stu-id="f41d2-136">E</span></span>  <br/> |<span data-ttu-id="f41d2-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f41d2-137">xsd:string</span></span>  <br/> |<span data-ttu-id="f41d2-138">可选</span><span class="sxs-lookup"><span data-stu-id="f41d2-138">optional</span></span>  <br/> |<span data-ttu-id="f41d2-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="f41d2-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="f41d2-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="f41d2-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="f41d2-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f41d2-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="f41d2-142">F</span><span class="sxs-lookup"><span data-stu-id="f41d2-142">F</span></span>  <br/> |<span data-ttu-id="f41d2-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f41d2-143">xsd:string</span></span>  <br/> |<span data-ttu-id="f41d2-144">可选</span><span class="sxs-lookup"><span data-stu-id="f41d2-144">optional</span></span>  <br/> | <span data-ttu-id="f41d2-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="f41d2-145">Represents the element's formula.</span></span> <span data-ttu-id="f41d2-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="f41d2-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="f41d2-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="f41d2-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="f41d2-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="f41d2-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="f41d2-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="f41d2-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="f41d2-150">公式。</span><span class="sxs-lookup"><span data-stu-id="f41d2-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="f41d2-151">N</span><span class="sxs-lookup"><span data-stu-id="f41d2-151">N</span></span>  <br/> |<span data-ttu-id="f41d2-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f41d2-152">xsd:string</span></span>  <br/> |<span data-ttu-id="f41d2-153">必需</span><span class="sxs-lookup"><span data-stu-id="f41d2-153">required</span></span>  <br/> |<span data-ttu-id="f41d2-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f41d2-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="f41d2-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f41d2-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="f41d2-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="f41d2-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="f41d2-157">U</span><span class="sxs-lookup"><span data-stu-id="f41d2-157">U</span></span>  <br/> |<span data-ttu-id="f41d2-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f41d2-158">xsd:string</span></span>  <br/> |<span data-ttu-id="f41d2-159">可选</span><span class="sxs-lookup"><span data-stu-id="f41d2-159">optional</span></span>  <br/> |<span data-ttu-id="f41d2-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="f41d2-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="f41d2-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="f41d2-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="f41d2-162">V</span><span class="sxs-lookup"><span data-stu-id="f41d2-162">V</span></span>  <br/> |<span data-ttu-id="f41d2-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f41d2-163">xsd:string</span></span>  <br/> |<span data-ttu-id="f41d2-164">可选</span><span class="sxs-lookup"><span data-stu-id="f41d2-164">optional</span></span>  <br/> |<span data-ttu-id="f41d2-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f41d2-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="f41d2-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f41d2-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f41d2-167">说明</span><span class="sxs-lookup"><span data-stu-id="f41d2-167">Remarks</span></span>

<span data-ttu-id="f41d2-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="f41d2-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="f41d2-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="f41d2-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="f41d2-170">**值**</span><span class="sxs-lookup"><span data-stu-id="f41d2-170">**Value**</span></span>|<span data-ttu-id="f41d2-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="f41d2-171">**Description**</span></span>|<span data-ttu-id="f41d2-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="f41d2-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f41d2-173">A</span><span class="sxs-lookup"><span data-stu-id="f41d2-173">A</span></span>  <br/> |<span data-ttu-id="f41d2-174">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="f41d2-174">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |[<span data-ttu-id="f41d2-175">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f41d2-175">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="f41d2-176">X</span><span class="sxs-lookup"><span data-stu-id="f41d2-176">X</span></span>  <br/> |<span data-ttu-id="f41d2-177">弧形终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="f41d2-177">The x-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="f41d2-178">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f41d2-178">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="f41d2-179">Y</span><span class="sxs-lookup"><span data-stu-id="f41d2-179">Y</span></span>  <br/> |<span data-ttu-id="f41d2-180">弧形终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="f41d2-180">The y-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="f41d2-181">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="f41d2-181">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
   

