---
title: 单元格元素 （填充渐变部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d085f83a-f77b-9bf9-07dc-4561b83e288c
description: 包含颜色、 透明度和渐变填充的渐变光圈的位置。
ms.openlocfilehash: c5366d1d3fcf5a4cd453bc62467353b940e89792
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779826"
---
# <a name="cell-element-fill-gradient-section-visio-xml"></a><span data-ttu-id="8cdd0-103">单元格元素 （填充渐变部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8cdd0-103">Cell element (Fill Gradient Section) ('Visio XML')</span></span>

<span data-ttu-id="8cdd0-104">包含颜色、 透明度和渐变填充的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-104">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8cdd0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8cdd0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8cdd0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8cdd0-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="8cdd0-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8cdd0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8cdd0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8cdd0-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="8cdd0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8cdd0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8cdd0-112">document.xml，母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="8cdd0-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8cdd0-113">定义</span><span class="sxs-lookup"><span data-stu-id="8cdd0-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8cdd0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8cdd0-114">Elements and attributes</span></span>

<span data-ttu-id="8cdd0-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8cdd0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8cdd0-116">Parent elements</span></span>

|<span data-ttu-id="8cdd0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-117">**Element**</span></span>|<span data-ttu-id="8cdd0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-118">**Type**</span></span>|<span data-ttu-id="8cdd0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8cdd0-120">Row 元素 （FillGradient 部分）</span><span class="sxs-lookup"><span data-stu-id="8cdd0-120">Row element (FillGradient Section)</span></span>](row-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="8cdd0-121">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="8cdd0-121">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8cdd0-122">包含颜色、 透明度和渐变填充的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-122">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8cdd0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8cdd0-123">Child elements</span></span>

|<span data-ttu-id="8cdd0-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-124">**Element**</span></span>|<span data-ttu-id="8cdd0-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-125">**Type**</span></span>|<span data-ttu-id="8cdd0-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8cdd0-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="8cdd0-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8cdd0-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="8cdd0-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8cdd0-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="8cdd0-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="8cdd0-130">Attributes</span></span>

|<span data-ttu-id="8cdd0-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-131">**Attribute**</span></span>|<span data-ttu-id="8cdd0-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-132">**Type**</span></span>|<span data-ttu-id="8cdd0-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-133">**Required**</span></span>|<span data-ttu-id="8cdd0-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-134">**Description**</span></span>|<span data-ttu-id="8cdd0-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8cdd0-136">E</span><span class="sxs-lookup"><span data-stu-id="8cdd0-136">E</span></span>  <br/> |<span data-ttu-id="8cdd0-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8cdd0-137">xsd:string</span></span>  <br/> |<span data-ttu-id="8cdd0-138">可选</span><span class="sxs-lookup"><span data-stu-id="8cdd0-138">optional</span></span>  <br/> |<span data-ttu-id="8cdd0-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="8cdd0-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="8cdd0-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="8cdd0-142">F</span><span class="sxs-lookup"><span data-stu-id="8cdd0-142">F</span></span>  <br/> |<span data-ttu-id="8cdd0-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8cdd0-143">xsd:string</span></span>  <br/> |<span data-ttu-id="8cdd0-144">可选</span><span class="sxs-lookup"><span data-stu-id="8cdd0-144">optional</span></span>  <br/> | <span data-ttu-id="8cdd0-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-145">Represents the element's formula.</span></span> <span data-ttu-id="8cdd0-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="8cdd0-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="8cdd0-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="8cdd0-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="8cdd0-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="8cdd0-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="8cdd0-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="8cdd0-150">公式。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="8cdd0-151">N</span><span class="sxs-lookup"><span data-stu-id="8cdd0-151">N</span></span>  <br/> |<span data-ttu-id="8cdd0-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8cdd0-152">xsd:string</span></span>  <br/> |<span data-ttu-id="8cdd0-153">必需</span><span class="sxs-lookup"><span data-stu-id="8cdd0-153">required</span></span>  <br/> |<span data-ttu-id="8cdd0-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="8cdd0-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="8cdd0-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="8cdd0-157">U</span><span class="sxs-lookup"><span data-stu-id="8cdd0-157">U</span></span>  <br/> |<span data-ttu-id="8cdd0-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8cdd0-158">xsd:string</span></span>  <br/> |<span data-ttu-id="8cdd0-159">可选</span><span class="sxs-lookup"><span data-stu-id="8cdd0-159">optional</span></span>  <br/> |<span data-ttu-id="8cdd0-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="8cdd0-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="8cdd0-162">V</span><span class="sxs-lookup"><span data-stu-id="8cdd0-162">V</span></span>  <br/> |<span data-ttu-id="8cdd0-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8cdd0-163">xsd:string</span></span>  <br/> |<span data-ttu-id="8cdd0-164">可选</span><span class="sxs-lookup"><span data-stu-id="8cdd0-164">optional</span></span>  <br/> |<span data-ttu-id="8cdd0-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="8cdd0-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8cdd0-167">说明</span><span class="sxs-lookup"><span data-stu-id="8cdd0-167">Remarks</span></span>

<span data-ttu-id="8cdd0-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="8cdd0-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="8cdd0-170">**值**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-170">**Value**</span></span>|<span data-ttu-id="8cdd0-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-171">**Description**</span></span>|<span data-ttu-id="8cdd0-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="8cdd0-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8cdd0-173">GradientStopColor</span><span class="sxs-lookup"><span data-stu-id="8cdd0-173">GradientStopColor</span></span>  <br/> |<span data-ttu-id="8cdd0-174">渐变光圈的颜色值。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-174">The color value of the gradient stop.</span></span> <span data-ttu-id="8cdd0-175">此值可表达为文档的调色板中或通过使用**RGB**、 **THEMEVAL**或**HSL**函数颜色的索引号。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-175">This value can be expressed as the index number of a color in the document palette or by using the **RGB**, **THEMEVAL**, or **HSL** functions.</span></span>  <br/> |[<span data-ttu-id="8cdd0-176">Gradient Stop 行（“Fill Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="8cdd0-176">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="8cdd0-177">GradientStopColorTrans</span><span class="sxs-lookup"><span data-stu-id="8cdd0-177">GradientStopColorTrans</span></span>  <br/> |<span data-ttu-id="8cdd0-178">以百分比形式的渐变颜色光圈，透明度量。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-178">The amount of transparency of the gradient color stop, as a percentage.</span></span>  <br/> |[<span data-ttu-id="8cdd0-179">Gradient Stop 行（“Fill Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="8cdd0-179">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="8cdd0-180">GradientStopPosition</span><span class="sxs-lookup"><span data-stu-id="8cdd0-180">GradientStopPosition</span></span>  <br/> |<span data-ttu-id="8cdd0-181">沿行渐变的方向的渐变渐变的外部边缘的起点从百分比渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-181">The position of the gradient stop along the direction of the line gradient, as a percentage from the point of origin of the gradient to the outer edge of the gradient.</span></span>  <br/> |[<span data-ttu-id="8cdd0-182">Gradient Stop 行（“Fill Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="8cdd0-182">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
   

