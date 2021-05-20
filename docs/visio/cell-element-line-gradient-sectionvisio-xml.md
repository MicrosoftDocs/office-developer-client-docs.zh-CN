---
title: 'Cell 元素 (Line Gradient Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8001249c-ea67-c5c0-3168-485400c43d8c
description: 包含线条渐变的渐变停点的颜色、透明度或位置。
ms.openlocfilehash: d8ac664285d24e47a142c22b1483e2ff435aef48
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539500"
---
# <a name="cell-element-line-gradient-section-visio-xml"></a><span data-ttu-id="894b7-103">Cell 元素 (Line Gradient Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="894b7-103">Cell element (Line Gradient Section) (Visio XML)</span></span>

<span data-ttu-id="894b7-104">包含线条渐变的渐变停点的颜色、透明度或位置。</span><span class="sxs-lookup"><span data-stu-id="894b7-104">Contains the color, transparency, or position of a gradient stop for a line gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="894b7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="894b7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="894b7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="894b7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="894b7-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="894b7-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="894b7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="894b7-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="894b7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="894b7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="894b7-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="894b7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="894b7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="894b7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="894b7-112">document.xml、master#.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="894b7-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="894b7-113">定义</span><span class="sxs-lookup"><span data-stu-id="894b7-113">Definition</span></span>

```XML
< xs:element name="Cell"  type="Cell_Type" minOccurs="0" maxOccurs="unbounded">
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="894b7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="894b7-114">Elements and attributes</span></span>

<span data-ttu-id="894b7-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="894b7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="894b7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="894b7-116">Parent elements</span></span>

|<span data-ttu-id="894b7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="894b7-117">**Element**</span></span>|<span data-ttu-id="894b7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="894b7-118">**Type**</span></span>|<span data-ttu-id="894b7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="894b7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="894b7-120">Row 元素 (Line Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="894b7-120">Row element (Line Gradient Section)</span></span>](row-element-line-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="894b7-121">LineGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="894b7-121">LineGradientRow_Type</span></span>](linegradientrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="894b7-122">包含线条渐变的渐变停点的颜色、透明度以及位置。</span><span class="sxs-lookup"><span data-stu-id="894b7-122">Contains the color, transparency, and position of a gradient stop for a line gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="894b7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="894b7-123">Child elements</span></span>

|<span data-ttu-id="894b7-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="894b7-124">**Element**</span></span>|<span data-ttu-id="894b7-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="894b7-125">**Type**</span></span>|<span data-ttu-id="894b7-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="894b7-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="894b7-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="894b7-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="894b7-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="894b7-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="894b7-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="894b7-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="894b7-130">属性</span><span class="sxs-lookup"><span data-stu-id="894b7-130">Attributes</span></span>

|<span data-ttu-id="894b7-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="894b7-131">**Attribute**</span></span>|<span data-ttu-id="894b7-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="894b7-132">**Type**</span></span>|<span data-ttu-id="894b7-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="894b7-133">**Required**</span></span>|<span data-ttu-id="894b7-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="894b7-134">**Description**</span></span>|<span data-ttu-id="894b7-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="894b7-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="894b7-136">E</span><span class="sxs-lookup"><span data-stu-id="894b7-136">E</span></span>  <br/> |<span data-ttu-id="894b7-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="894b7-137">xsd:string</span></span>  <br/> |<span data-ttu-id="894b7-138">可选</span><span class="sxs-lookup"><span data-stu-id="894b7-138">optional</span></span>  <br/> |<span data-ttu-id="894b7-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="894b7-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="894b7-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="894b7-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="894b7-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="894b7-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="894b7-142">F</span><span class="sxs-lookup"><span data-stu-id="894b7-142">F</span></span>  <br/> |<span data-ttu-id="894b7-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="894b7-143">xsd:string</span></span>  <br/> |<span data-ttu-id="894b7-144">可选</span><span class="sxs-lookup"><span data-stu-id="894b7-144">optional</span></span>  <br/> | <span data-ttu-id="894b7-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="894b7-145">Represents the element's formula.</span></span> <span data-ttu-id="894b7-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="894b7-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="894b7-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="894b7-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="894b7-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="894b7-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="894b7-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="894b7-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="894b7-150">公式。</span><span class="sxs-lookup"><span data-stu-id="894b7-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="894b7-151">N</span><span class="sxs-lookup"><span data-stu-id="894b7-151">N</span></span>  <br/> |<span data-ttu-id="894b7-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="894b7-152">xsd:string</span></span>  <br/> |<span data-ttu-id="894b7-153">必需</span><span class="sxs-lookup"><span data-stu-id="894b7-153">required</span></span>  <br/> |<span data-ttu-id="894b7-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="894b7-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="894b7-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="894b7-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="894b7-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="894b7-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="894b7-157">U</span><span class="sxs-lookup"><span data-stu-id="894b7-157">U</span></span>  <br/> |<span data-ttu-id="894b7-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="894b7-158">xsd:string</span></span>  <br/> |<span data-ttu-id="894b7-159">可选</span><span class="sxs-lookup"><span data-stu-id="894b7-159">optional</span></span>  <br/> |<span data-ttu-id="894b7-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="894b7-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="894b7-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="894b7-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="894b7-162">V</span><span class="sxs-lookup"><span data-stu-id="894b7-162">V</span></span>  <br/> |<span data-ttu-id="894b7-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="894b7-163">xsd:string</span></span>  <br/> |<span data-ttu-id="894b7-164">可选</span><span class="sxs-lookup"><span data-stu-id="894b7-164">optional</span></span>  <br/> |<span data-ttu-id="894b7-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="894b7-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="894b7-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="894b7-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="894b7-167">备注</span><span class="sxs-lookup"><span data-stu-id="894b7-167">Remarks</span></span>

<span data-ttu-id="894b7-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="894b7-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="894b7-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="894b7-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="894b7-170">**值**</span><span class="sxs-lookup"><span data-stu-id="894b7-170">**Value**</span></span>|<span data-ttu-id="894b7-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="894b7-171">**Description**</span></span>|<span data-ttu-id="894b7-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="894b7-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="894b7-173">GradientStopColor</span><span class="sxs-lookup"><span data-stu-id="894b7-173">GradientStopColor</span></span>  <br/> |<span data-ttu-id="894b7-174">渐变停点的颜色值。</span><span class="sxs-lookup"><span data-stu-id="894b7-174">The color value of the gradient stop.</span></span>  <br/> |[<span data-ttu-id="894b7-175">Gradient Stop Row (Line Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="894b7-175">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
|<span data-ttu-id="894b7-176">GradientStopColorTrans</span><span class="sxs-lookup"><span data-stu-id="894b7-176">GradientStopColorTrans</span></span>  <br/> |<span data-ttu-id="894b7-177">渐变停止颜色的透明度，以百分比表示。</span><span class="sxs-lookup"><span data-stu-id="894b7-177">The amount of transparency of the gradient stop color, as a percentage.</span></span>  <br/> |[<span data-ttu-id="894b7-178">Gradient Stop Row (Line Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="894b7-178">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
|<span data-ttu-id="894b7-179">GradientStopPosition</span><span class="sxs-lookup"><span data-stu-id="894b7-179">GradientStopPosition</span></span>  <br/> |<span data-ttu-id="894b7-180">渐变停点沿线条渐变方向的位置，以从渐变原点到渐变外边缘的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="894b7-180">The position of the gradient stop along the direction of the line gradient, as a percentage from the point of origin of the gradient to the outer edge of the gradient.</span></span>  <br/> |[<span data-ttu-id="894b7-181">Gradient Stop Row (Line Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="894b7-181">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
   

