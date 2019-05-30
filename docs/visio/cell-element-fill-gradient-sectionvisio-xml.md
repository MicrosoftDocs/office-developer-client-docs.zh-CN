---
title: Cell 元素 ("填充渐变" 部分) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d085f83a-f77b-9bf9-07dc-4561b83e288c
description: 包含颜色、透明度以及填充渐变的渐变停止点的位置。
ms.openlocfilehash: 998c63d5273c39601e5b7293ae03eebbc3b467b2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539549"
---
# <a name="cell-element-fill-gradient-section-visio-xml"></a><span data-ttu-id="f6213-103">Cell 元素 ("填充渐变" 部分) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f6213-103">Cell element (Fill Gradient Section) (Visio XML)</span></span>

<span data-ttu-id="f6213-104">包含颜色、透明度以及填充渐变的渐变停止点的位置。</span><span class="sxs-lookup"><span data-stu-id="f6213-104">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f6213-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f6213-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f6213-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f6213-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f6213-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="f6213-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f6213-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f6213-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f6213-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f6213-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f6213-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="f6213-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f6213-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f6213-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f6213-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="f6213-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f6213-113">定义</span><span class="sxs-lookup"><span data-stu-id="f6213-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f6213-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f6213-114">Elements and attributes</span></span>

<span data-ttu-id="f6213-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f6213-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f6213-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f6213-116">Parent elements</span></span>

|<span data-ttu-id="f6213-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f6213-117">**Element**</span></span>|<span data-ttu-id="f6213-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6213-118">**Type**</span></span>|<span data-ttu-id="f6213-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6213-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f6213-120">Row 元素 ("FillGradient" 内容)</span><span class="sxs-lookup"><span data-stu-id="f6213-120">Row element (FillGradient Section)</span></span>](row-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f6213-121">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="f6213-121">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f6213-122">包含颜色、透明度以及填充渐变的渐变停止点的位置。</span><span class="sxs-lookup"><span data-stu-id="f6213-122">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f6213-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f6213-123">Child elements</span></span>

|<span data-ttu-id="f6213-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f6213-124">**Element**</span></span>|<span data-ttu-id="f6213-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6213-125">**Type**</span></span>|<span data-ttu-id="f6213-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6213-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f6213-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="f6213-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f6213-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="f6213-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f6213-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="f6213-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f6213-130">属性</span><span class="sxs-lookup"><span data-stu-id="f6213-130">Attributes</span></span>

|<span data-ttu-id="f6213-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="f6213-131">**Attribute**</span></span>|<span data-ttu-id="f6213-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6213-132">**Type**</span></span>|<span data-ttu-id="f6213-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="f6213-133">**Required**</span></span>|<span data-ttu-id="f6213-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="f6213-134">**Description**</span></span>|<span data-ttu-id="f6213-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f6213-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6213-136">E</span><span class="sxs-lookup"><span data-stu-id="f6213-136">E</span></span>  <br/> |<span data-ttu-id="f6213-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f6213-137">xsd:string</span></span>  <br/> |<span data-ttu-id="f6213-138">可选</span><span class="sxs-lookup"><span data-stu-id="f6213-138">optional</span></span>  <br/> |<span data-ttu-id="f6213-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="f6213-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="f6213-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="f6213-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="f6213-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="f6213-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="f6213-142">F</span><span class="sxs-lookup"><span data-stu-id="f6213-142">F</span></span>  <br/> |<span data-ttu-id="f6213-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f6213-143">xsd:string</span></span>  <br/> |<span data-ttu-id="f6213-144">可选</span><span class="sxs-lookup"><span data-stu-id="f6213-144">optional</span></span>  <br/> | <span data-ttu-id="f6213-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="f6213-145">Represents the element's formula.</span></span> <span data-ttu-id="f6213-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="f6213-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="f6213-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="f6213-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="f6213-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="f6213-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="f6213-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="f6213-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="f6213-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="f6213-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="f6213-151">N</span><span class="sxs-lookup"><span data-stu-id="f6213-151">N</span></span>  <br/> |<span data-ttu-id="f6213-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f6213-152">xsd:string</span></span>  <br/> |<span data-ttu-id="f6213-153">必需</span><span class="sxs-lookup"><span data-stu-id="f6213-153">required</span></span>  <br/> |<span data-ttu-id="f6213-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f6213-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="f6213-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="f6213-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="f6213-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="f6213-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="f6213-157">U</span><span class="sxs-lookup"><span data-stu-id="f6213-157">U</span></span>  <br/> |<span data-ttu-id="f6213-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f6213-158">xsd:string</span></span>  <br/> |<span data-ttu-id="f6213-159">可选</span><span class="sxs-lookup"><span data-stu-id="f6213-159">optional</span></span>  <br/> |<span data-ttu-id="f6213-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="f6213-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="f6213-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="f6213-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="f6213-162">部分</span><span class="sxs-lookup"><span data-stu-id="f6213-162">V</span></span>  <br/> |<span data-ttu-id="f6213-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f6213-163">xsd:string</span></span>  <br/> |<span data-ttu-id="f6213-164">可选</span><span class="sxs-lookup"><span data-stu-id="f6213-164">optional</span></span>  <br/> |<span data-ttu-id="f6213-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f6213-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="f6213-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="f6213-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f6213-167">备注</span><span class="sxs-lookup"><span data-stu-id="f6213-167">Remarks</span></span>

<span data-ttu-id="f6213-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="f6213-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="f6213-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="f6213-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="f6213-170">**值**</span><span class="sxs-lookup"><span data-stu-id="f6213-170">**Value**</span></span>|<span data-ttu-id="f6213-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6213-171">**Description**</span></span>|<span data-ttu-id="f6213-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f6213-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6213-173">GradientStopColor</span><span class="sxs-lookup"><span data-stu-id="f6213-173">GradientStopColor</span></span>  <br/> |<span data-ttu-id="f6213-174">渐变光圈的颜色值。</span><span class="sxs-lookup"><span data-stu-id="f6213-174">The color value of the gradient stop.</span></span> <span data-ttu-id="f6213-175">此值可表示为文档调色板中的颜色的索引号, 或者使用**RGB**、 **THEMEVAL**或**HSL**函数。</span><span class="sxs-lookup"><span data-stu-id="f6213-175">This value can be expressed as the index number of a color in the document palette or by using the **RGB**, **THEMEVAL**, or **HSL** functions.</span></span>  <br/> |[<span data-ttu-id="f6213-176">渐变停止行 ("填充渐变" 部分)</span><span class="sxs-lookup"><span data-stu-id="f6213-176">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="f6213-177">GradientStopColorTrans</span><span class="sxs-lookup"><span data-stu-id="f6213-177">GradientStopColorTrans</span></span>  <br/> |<span data-ttu-id="f6213-178">以百分比表示的渐变色标的透明度。</span><span class="sxs-lookup"><span data-stu-id="f6213-178">The amount of transparency of the gradient color stop, as a percentage.</span></span>  <br/> |[<span data-ttu-id="f6213-179">渐变停止行 ("填充渐变" 部分)</span><span class="sxs-lookup"><span data-stu-id="f6213-179">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
|<span data-ttu-id="f6213-180">GradientStopPosition</span><span class="sxs-lookup"><span data-stu-id="f6213-180">GradientStopPosition</span></span>  <br/> |<span data-ttu-id="f6213-181">渐变光圈沿直线渐变的方向, 作为从渐变原点到渐变边缘的百分比表示的相对位置。</span><span class="sxs-lookup"><span data-stu-id="f6213-181">The position of the gradient stop along the direction of the line gradient, as a percentage from the point of origin of the gradient to the outer edge of the gradient.</span></span>  <br/> |[<span data-ttu-id="f6213-182">渐变停止行 ("填充渐变" 部分)</span><span class="sxs-lookup"><span data-stu-id="f6213-182">Gradient Stop Row (Fill Gradient Section)</span></span>](gradient-stop-row-fill-gradient-section.md) <br/> |
   

