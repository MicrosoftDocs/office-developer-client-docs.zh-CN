---
title: 单元格元素 （ArcTo 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 69f1a0cc-90fe-4b49-653c-bba4a1a2b1b2
description: 包含的 x 坐标、 y 坐标或圆弧弓。
ms.openlocfilehash: a51cf775f787a34aa8f5de6f6cf90ffc230f3500
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779812"
---
# <a name="cell-element-arcto-row-visio-xml"></a><span data-ttu-id="d1f57-103">单元格元素 （ArcTo 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d1f57-103">Cell element (ArcTo Row) ('Visio XML')</span></span>

<span data-ttu-id="d1f57-104">包含的 x 坐标、 y 坐标或圆弧弓。</span><span class="sxs-lookup"><span data-stu-id="d1f57-104">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d1f57-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d1f57-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d1f57-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d1f57-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d1f57-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d1f57-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d1f57-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d1f57-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d1f57-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d1f57-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d1f57-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d1f57-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d1f57-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d1f57-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d1f57-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="d1f57-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d1f57-113">定义</span><span class="sxs-lookup"><span data-stu-id="d1f57-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d1f57-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d1f57-114">Elements and attributes</span></span>

<span data-ttu-id="d1f57-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d1f57-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d1f57-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d1f57-116">Parent elements</span></span>

|<span data-ttu-id="d1f57-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1f57-117">**Element**</span></span>|<span data-ttu-id="d1f57-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1f57-118">**Type**</span></span>|<span data-ttu-id="d1f57-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1f57-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d1f57-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="d1f57-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d1f57-121">ArcTo_Type</span><span class="sxs-lookup"><span data-stu-id="d1f57-121">ArcTo_Type</span></span>](arcto_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1f57-122">包含的 x 坐标和 y 坐标和弓圆弧。</span><span class="sxs-lookup"><span data-stu-id="d1f57-122">Contains the x- and y-coordinates and bow of a circular arc.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d1f57-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d1f57-123">Child elements</span></span>

|<span data-ttu-id="d1f57-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1f57-124">**Element**</span></span>|<span data-ttu-id="d1f57-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1f57-125">**Type**</span></span>|<span data-ttu-id="d1f57-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1f57-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d1f57-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="d1f57-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1f57-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="d1f57-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1f57-129">包含的 x 坐标、 y 坐标或圆弧弓。</span><span class="sxs-lookup"><span data-stu-id="d1f57-129">Contains the x coordinate, y coordinate, or bow of a circular arc.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d1f57-130">属性</span><span class="sxs-lookup"><span data-stu-id="d1f57-130">Attributes</span></span>

|<span data-ttu-id="d1f57-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="d1f57-131">**Attribute**</span></span>|<span data-ttu-id="d1f57-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1f57-132">**Type**</span></span>|<span data-ttu-id="d1f57-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="d1f57-133">**Required**</span></span>|<span data-ttu-id="d1f57-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1f57-134">**Description**</span></span>|<span data-ttu-id="d1f57-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d1f57-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1f57-136">E</span><span class="sxs-lookup"><span data-stu-id="d1f57-136">E</span></span>  <br/> |<span data-ttu-id="d1f57-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1f57-137">xsd:string</span></span>  <br/> |<span data-ttu-id="d1f57-138">可选</span><span class="sxs-lookup"><span data-stu-id="d1f57-138">optional</span></span>  <br/> |<span data-ttu-id="d1f57-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="d1f57-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="d1f57-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="d1f57-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="d1f57-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="d1f57-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="d1f57-142">F</span><span class="sxs-lookup"><span data-stu-id="d1f57-142">F</span></span>  <br/> |<span data-ttu-id="d1f57-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1f57-143">xsd:string</span></span>  <br/> |<span data-ttu-id="d1f57-144">可选</span><span class="sxs-lookup"><span data-stu-id="d1f57-144">optional</span></span>  <br/> | <span data-ttu-id="d1f57-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="d1f57-145">Represents the element's formula.</span></span> <span data-ttu-id="d1f57-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="d1f57-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="d1f57-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="d1f57-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="d1f57-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="d1f57-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="d1f57-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="d1f57-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="d1f57-150">公式。</span><span class="sxs-lookup"><span data-stu-id="d1f57-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="d1f57-151">N</span><span class="sxs-lookup"><span data-stu-id="d1f57-151">N</span></span>  <br/> |<span data-ttu-id="d1f57-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1f57-152">xsd:string</span></span>  <br/> |<span data-ttu-id="d1f57-153">必需</span><span class="sxs-lookup"><span data-stu-id="d1f57-153">required</span></span>  <br/> |<span data-ttu-id="d1f57-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d1f57-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="d1f57-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="d1f57-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="d1f57-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="d1f57-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="d1f57-157">U</span><span class="sxs-lookup"><span data-stu-id="d1f57-157">U</span></span>  <br/> |<span data-ttu-id="d1f57-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1f57-158">xsd:string</span></span>  <br/> |<span data-ttu-id="d1f57-159">可选</span><span class="sxs-lookup"><span data-stu-id="d1f57-159">optional</span></span>  <br/> |<span data-ttu-id="d1f57-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="d1f57-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="d1f57-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="d1f57-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="d1f57-162">V</span><span class="sxs-lookup"><span data-stu-id="d1f57-162">V</span></span>  <br/> |<span data-ttu-id="d1f57-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1f57-163">xsd:string</span></span>  <br/> |<span data-ttu-id="d1f57-164">可选</span><span class="sxs-lookup"><span data-stu-id="d1f57-164">optional</span></span>  <br/> |<span data-ttu-id="d1f57-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d1f57-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="d1f57-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="d1f57-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1f57-167">备注</span><span class="sxs-lookup"><span data-stu-id="d1f57-167">Remarks</span></span>

<span data-ttu-id="d1f57-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="d1f57-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="d1f57-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="d1f57-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="d1f57-170">**值**</span><span class="sxs-lookup"><span data-stu-id="d1f57-170">**Value**</span></span>|<span data-ttu-id="d1f57-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1f57-171">**Description**</span></span>|<span data-ttu-id="d1f57-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d1f57-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1f57-173">A</span><span class="sxs-lookup"><span data-stu-id="d1f57-173">A</span></span>  <br/> |<span data-ttu-id="d1f57-174">从弧形的中点到对应的弦的中点的距离。</span><span class="sxs-lookup"><span data-stu-id="d1f57-174">The distance from the arc's midpoint to the midpoint of its chord.</span></span>  <br/> |[<span data-ttu-id="d1f57-175">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="d1f57-175">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="d1f57-176">X</span><span class="sxs-lookup"><span data-stu-id="d1f57-176">X</span></span>  <br/> |<span data-ttu-id="d1f57-177">弧形终顶点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="d1f57-177">The x-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="d1f57-178">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="d1f57-178">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
|<span data-ttu-id="d1f57-179">Y</span><span class="sxs-lookup"><span data-stu-id="d1f57-179">Y</span></span>  <br/> |<span data-ttu-id="d1f57-180">弧形终顶点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="d1f57-180">The y-coordinate of the ending vertex of an arc.</span></span>  <br/> |[<span data-ttu-id="d1f57-181">ArcTo Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="d1f57-181">ArcTo Row (Geometry Section)</span></span>](arcto-row-geometry-section.md) <br/> |
   

