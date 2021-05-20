---
title: 'Cell 元素 (Fill Gradient Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d085f83a-f77b-9bf9-07dc-4561b83e288c
description: 包含填充渐变的渐变停点的颜色、透明度以及位置。
ms.openlocfilehash: 998c63d5273c39601e5b7293ae03eebbc3b467b2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539549"
---
# <a name="cell-element-fill-gradient-section-visio-xml"></a><span data-ttu-id="e16a0-103">Cell 元素 (Fill Gradient Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="e16a0-103">Cell element (Fill Gradient Section) (Visio XML)</span></span>

<span data-ttu-id="e16a0-104">包含填充渐变的渐变停点的颜色、透明度以及位置。</span><span class="sxs-lookup"><span data-stu-id="e16a0-104">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e16a0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e16a0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e16a0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e16a0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e16a0-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="e16a0-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e16a0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e16a0-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e16a0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e16a0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e16a0-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="e16a0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e16a0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e16a0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e16a0-112">document.xml、master#.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="e16a0-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e16a0-113">定义</span><span class="sxs-lookup"><span data-stu-id="e16a0-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e16a0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e16a0-114">Elements and attributes</span></span>

<span data-ttu-id="e16a0-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e16a0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e16a0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e16a0-116">Parent elements</span></span>

|<span data-ttu-id="e16a0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e16a0-117">**Element**</span></span>|<span data-ttu-id="e16a0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e16a0-118">**Type**</span></span>|<span data-ttu-id="e16a0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e16a0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e16a0-120">FillGradient (Row 元素) </span><span class="sxs-lookup"><span data-stu-id="e16a0-120">Row element (FillGradient Section)</span></span>](row-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="e16a0-121">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="e16a0-121">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e16a0-122">包含填充渐变的渐变停点的颜色、透明度以及位置。</span><span class="sxs-lookup"><span data-stu-id="e16a0-122">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e16a0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e16a0-123">Child elements</span></span>

|<span data-ttu-id="e16a0-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="e16a0-124">**Element**</span></span>|<span data-ttu-id="e16a0-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e16a0-125">**Type**</span></span>|<span data-ttu-id="e16a0-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="e16a0-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e16a0-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="e16a0-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e16a0-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="e16a0-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e16a0-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="e16a0-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="e16a0-130">属性</span><span class="sxs-lookup"><span data-stu-id="e16a0-130">Attributes</span></span>

|<span data-ttu-id="e16a0-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="e16a0-131">**Attribute**</span></span>|<span data-ttu-id="e16a0-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="e16a0-132">**Type**</span></span>|<span data-ttu-id="e16a0-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="e16a0-133">**Required**</span></span>|<span data-ttu-id="e16a0-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="e16a0-134">**Description**</span></span>|<span data-ttu-id="e16a0-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e16a0-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e16a0-136">E</span><span class="sxs-lookup"><span data-stu-id="e16a0-136">E</span></span>  <br/> |<span data-ttu-id="e16a0-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e16a0-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e16a0-138">可选</span><span class="sxs-lookup"><span data-stu-id="e16a0-138">optional</span></span>  <br/> |<span data-ttu-id="e16a0-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="e16a0-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="e16a0-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="e16a0-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="e16a0-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="e16a0-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="e16a0-142">F</span><span class="sxs-lookup"><span data-stu-id="e16a0-142">F</span></span>  <br/> |<span data-ttu-id="e16a0-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e16a0-143">xsd:string</span></span>  <br/> |<span data-ttu-id="e16a0-144">可选</span><span class="sxs-lookup"><span data-stu-id="e16a0-144">optional</span></span>  <br/> | <span data-ttu-id="e16a0-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="e16a0-145">Represents the element's formula.</span></span> <span data-ttu-id="e16a0-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="e16a0-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="e16a0-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="e16a0-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="e16a0-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="e16a0-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="e16a0-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="e16a0-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="e16a0-150">公式。</span><span class="sxs-lookup"><span data-stu-id="e16a0-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="e16a0-151">N</span><span class="sxs-lookup"><span data-stu-id="e16a0-151">N</span></span>  <br/> |<span data-ttu-id="e16a0-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e16a0-152">xsd:string</span></span>  <br/> |<span data-ttu-id="e16a0-153">必需</span><span class="sxs-lookup"><span data-stu-id="e16a0-153">required</span></span>  <br/> |<span data-ttu-id="e16a0-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="e16a0-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="e16a0-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="e16a0-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="e16a0-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="e16a0-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="e16a0-157">U</span><span class="sxs-lookup"><span data-stu-id="e16a0-157">U</span></span>  <br/> |<span data-ttu-id="e16a0-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e16a0-158">xsd:string</span></span>  <br/> |<span data-ttu-id="e16a0-159">可选</span><span class="sxs-lookup"><span data-stu-id="e16a0-159">optional</span></span>  <br/> |<span data-ttu-id="e16a0-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="e16a0-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="e16a0-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="e16a0-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="e16a0-162">V</span><span class="sxs-lookup"><span data-stu-id="e16a0-162">V</span></span>  <br/> |<span data-ttu-id="e16a0-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e16a0-163">xsd:string</span></span>  <br/> |<span data-ttu-id="e16a0-164">可选</span><span class="sxs-lookup"><span data-stu-id="e16a0-164">optional</span></span>  <br/> |<span data-ttu-id="e16a0-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="e16a0-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="e16a0-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="e16a0-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e16a0-167">备注</span><span class="sxs-lookup"><span data-stu-id="e16a0-167">Remarks</span></span>

<span data-ttu-id="e16a0-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="e16a0-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="e16a0-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e16a0-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="e16a0-170">**值**</span><span class="sxs-lookup"><span data-stu-id="e16a0-170">**Value**</span></span>|<span data-ttu-id="e16a0-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="e16a0-171">**Description**</span></span>|<span data-ttu-id="e16a0-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e16a0-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e16a0-173">GradientStopColor</span><span class="sxs-lookup"><span data-stu-id="e16a0-173">GradientStopColor</span></span>  <br/> |<span data-ttu-id="e16a0-174">渐变停点的颜色值。</span><span class="sxs-lookup"><span data-stu-id="e16a0-174">The color value of the gradient stop.</span></span> <span data-ttu-id="e16a0-175">此值可以表示为文档调色板中颜色的索引号，或者使用 **RGB、THEMEVAL** 或 **HSL** 函数表示。</span><span class="sxs-lookup"><span data-stu-id="e16a0-175">This value can be expressed as the index number of a color in the document palette or by using the **RGB**, **THEMEVAL**, or **HSL** functions.</span></span>  <br/> |[<span data-ttu-id="e16a0-176">Gradient Stop Row (Fill Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="e16a0-176">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="e16a0-177">GradientStopColorTrans</span><span class="sxs-lookup"><span data-stu-id="e16a0-177">GradientStopColorTrans</span></span>  <br/> |<span data-ttu-id="e16a0-178">渐变颜色停止点的透明度，以百分比表示。</span><span class="sxs-lookup"><span data-stu-id="e16a0-178">The amount of transparency of the gradient color stop, as a percentage.</span></span>  <br/> |[<span data-ttu-id="e16a0-179">Gradient Stop Row (Fill Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="e16a0-179">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="e16a0-180">GradientStopPosition</span><span class="sxs-lookup"><span data-stu-id="e16a0-180">GradientStopPosition</span></span>  <br/> |<span data-ttu-id="e16a0-181">渐变停点沿线条渐变方向的位置，以从渐变原点到渐变外边缘的百分比表示。</span><span class="sxs-lookup"><span data-stu-id="e16a0-181">The position of the gradient stop along the direction of the line gradient, as a percentage from the point of origin of the gradient to the outer edge of the gradient.</span></span>  <br/> |[<span data-ttu-id="e16a0-182">Gradient Stop Row (Fill Gradient Section) </span><span class="sxs-lookup"><span data-stu-id="e16a0-182">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
   

