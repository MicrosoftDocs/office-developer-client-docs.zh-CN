---
title: 单元格 （Line 渐变内容） (Visio XML) 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8001249c-ea67-c5c0-3168-485400c43d8c
description: 包含颜色、 透明度或行渐变的渐变光圈的位置。
ms.openlocfilehash: 13b42af36c9e11a71f21f39527788342354de01d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779828"
---
# <a name="cell-element-line-gradient-section-visio-xml"></a><span data-ttu-id="2684c-103">单元格 （Line 渐变内容） (Visio XML) 元素</span><span class="sxs-lookup"><span data-stu-id="2684c-103">Cell element (Line Gradient Section) ('Visio XML')</span></span>

<span data-ttu-id="2684c-104">包含颜色、 透明度或行渐变的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="2684c-104">Contains the color, transparency, or position of a gradient stop for a line gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2684c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2684c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2684c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2684c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="2684c-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="2684c-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="2684c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2684c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="2684c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2684c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="2684c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="2684c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="2684c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="2684c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="2684c-112">document.xml，母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="2684c-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2684c-113">定义</span><span class="sxs-lookup"><span data-stu-id="2684c-113">Definition</span></span>

```XML
< xs:element name="Cell"  type="Cell_Type" minOccurs="0" maxOccurs="unbounded">
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2684c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2684c-114">Elements and attributes</span></span>

<span data-ttu-id="2684c-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2684c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2684c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="2684c-116">Parent elements</span></span>

|<span data-ttu-id="2684c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="2684c-117">**Element**</span></span>|<span data-ttu-id="2684c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="2684c-118">**Type**</span></span>|<span data-ttu-id="2684c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="2684c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2684c-120">Row 元素（“Line Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="2684c-120">Row element (Line Gradient Section)</span></span>](row-element-line-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="2684c-121">LineGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="2684c-121">LineGradientRow_Type</span></span>](linegradientrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2684c-122">包含颜色、 透明度和行渐变的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="2684c-122">Contains the color, transparency, and position of a gradient stop for a line gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2684c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="2684c-123">Child elements</span></span>

|<span data-ttu-id="2684c-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="2684c-124">**Element**</span></span>|<span data-ttu-id="2684c-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="2684c-125">**Type**</span></span>|<span data-ttu-id="2684c-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="2684c-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2684c-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="2684c-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2684c-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="2684c-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2684c-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="2684c-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2684c-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="2684c-130">Attributes</span></span>

|<span data-ttu-id="2684c-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="2684c-131">**Attribute**</span></span>|<span data-ttu-id="2684c-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="2684c-132">**Type**</span></span>|<span data-ttu-id="2684c-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="2684c-133">**Required**</span></span>|<span data-ttu-id="2684c-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="2684c-134">**Description**</span></span>|<span data-ttu-id="2684c-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2684c-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2684c-136">E</span><span class="sxs-lookup"><span data-stu-id="2684c-136">E</span></span>  <br/> |<span data-ttu-id="2684c-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2684c-137">xsd:string</span></span>  <br/> |<span data-ttu-id="2684c-138">可选</span><span class="sxs-lookup"><span data-stu-id="2684c-138">optional</span></span>  <br/> |<span data-ttu-id="2684c-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="2684c-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="2684c-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="2684c-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="2684c-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="2684c-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="2684c-142">F</span><span class="sxs-lookup"><span data-stu-id="2684c-142">F</span></span>  <br/> |<span data-ttu-id="2684c-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2684c-143">xsd:string</span></span>  <br/> |<span data-ttu-id="2684c-144">可选</span><span class="sxs-lookup"><span data-stu-id="2684c-144">optional</span></span>  <br/> | <span data-ttu-id="2684c-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="2684c-145">Represents the element's formula.</span></span> <span data-ttu-id="2684c-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="2684c-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="2684c-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="2684c-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="2684c-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="2684c-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="2684c-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="2684c-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="2684c-150">公式。</span><span class="sxs-lookup"><span data-stu-id="2684c-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="2684c-151">N</span><span class="sxs-lookup"><span data-stu-id="2684c-151">N</span></span>  <br/> |<span data-ttu-id="2684c-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2684c-152">xsd:string</span></span>  <br/> |<span data-ttu-id="2684c-153">必需</span><span class="sxs-lookup"><span data-stu-id="2684c-153">required</span></span>  <br/> |<span data-ttu-id="2684c-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="2684c-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="2684c-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="2684c-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="2684c-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="2684c-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="2684c-157">U</span><span class="sxs-lookup"><span data-stu-id="2684c-157">U</span></span>  <br/> |<span data-ttu-id="2684c-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2684c-158">xsd:string</span></span>  <br/> |<span data-ttu-id="2684c-159">可选</span><span class="sxs-lookup"><span data-stu-id="2684c-159">optional</span></span>  <br/> |<span data-ttu-id="2684c-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="2684c-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="2684c-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="2684c-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="2684c-162">V</span><span class="sxs-lookup"><span data-stu-id="2684c-162">V</span></span>  <br/> |<span data-ttu-id="2684c-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2684c-163">xsd:string</span></span>  <br/> |<span data-ttu-id="2684c-164">可选</span><span class="sxs-lookup"><span data-stu-id="2684c-164">optional</span></span>  <br/> |<span data-ttu-id="2684c-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2684c-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="2684c-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="2684c-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2684c-167">说明</span><span class="sxs-lookup"><span data-stu-id="2684c-167">Remarks</span></span>

<span data-ttu-id="2684c-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="2684c-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="2684c-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="2684c-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="2684c-170">**值**</span><span class="sxs-lookup"><span data-stu-id="2684c-170">**Value**</span></span>|<span data-ttu-id="2684c-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="2684c-171">**Description**</span></span>|<span data-ttu-id="2684c-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="2684c-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2684c-173">GradientStopColor</span><span class="sxs-lookup"><span data-stu-id="2684c-173">GradientStopColor</span></span>  <br/> |<span data-ttu-id="2684c-174">渐变光圈的颜色值。</span><span class="sxs-lookup"><span data-stu-id="2684c-174">The color value of the gradient stop.</span></span>  <br/> |[<span data-ttu-id="2684c-175">Gradient Stop 行（“Line Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="2684c-175">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
|<span data-ttu-id="2684c-176">GradientStopColorTrans</span><span class="sxs-lookup"><span data-stu-id="2684c-176">GradientStopColorTrans</span></span>  <br/> |<span data-ttu-id="2684c-177">透明的渐变程度停止百分比的颜色。</span><span class="sxs-lookup"><span data-stu-id="2684c-177">The amount of transparency of the gradient stop color, as a percentage.</span></span>  <br/> |[<span data-ttu-id="2684c-178">Gradient Stop 行（“Line Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="2684c-178">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
|<span data-ttu-id="2684c-179">GradientStopPosition</span><span class="sxs-lookup"><span data-stu-id="2684c-179">GradientStopPosition</span></span>  <br/> |<span data-ttu-id="2684c-180">沿行渐变的方向的渐变渐变的外部边缘的起点从百分比渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="2684c-180">The position of the gradient stop along the direction of the line gradient, as a percentage from the point of origin of the gradient to the outer edge of the gradient.</span></span>  <br/> |[<span data-ttu-id="2684c-181">Gradient Stop 行（“Line Gradient”部分）</span><span class="sxs-lookup"><span data-stu-id="2684c-181">Gradient Stop Row (Line Gradient Section)</span></span>](gradient-stop-row-line-gradient-section.md) <br/> |
   

