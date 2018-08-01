---
title: 单元格 （Tabs 内容） (Visio XML) 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4292d489-fb7c-9d5d-9bec-2a1a0772d8ba
description: 指定形状和样式制表位位置或对齐的控件的属性。
ms.openlocfilehash: da2fb31688227180bb38a4366c3293a2e16600c8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779851"
---
# <a name="cell-element-tabs-section-visio-xml"></a><span data-ttu-id="98243-103">单元格 （Tabs 内容） (Visio XML) 元素</span><span class="sxs-lookup"><span data-stu-id="98243-103">Cell element (Tabs Section) ('Visio XML')</span></span>

<span data-ttu-id="98243-104">指定形状和样式制表位位置或对齐的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="98243-104">Specifies a property that controls shape and style tab stop position or alignment.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="98243-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="98243-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="98243-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="98243-106">**Element type**</span></span> <br/> |[<span data-ttu-id="98243-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="98243-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="98243-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="98243-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="98243-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="98243-109">**Schema file**</span></span> <br/> |<span data-ttu-id="98243-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="98243-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="98243-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="98243-111">**Document parts**</span></span> <br/> |<span data-ttu-id="98243-112">document.xml，母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="98243-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="98243-113">定义</span><span class="sxs-lookup"><span data-stu-id="98243-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="98243-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="98243-114">Elements and attributes</span></span>

<span data-ttu-id="98243-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="98243-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="98243-116">父元素</span><span class="sxs-lookup"><span data-stu-id="98243-116">Parent elements</span></span>

|<span data-ttu-id="98243-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="98243-117">**Element**</span></span>|<span data-ttu-id="98243-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="98243-118">**Type**</span></span>|<span data-ttu-id="98243-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="98243-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="98243-120">Row 元素（“Tabs”部分）</span><span class="sxs-lookup"><span data-stu-id="98243-120">Row element (Tabs Section)</span></span>](row-element-tabs-sectionvisio-xml.md) <br/> |[<span data-ttu-id="98243-121">TabsRow_Type</span><span class="sxs-lookup"><span data-stu-id="98243-121">TabsRow_Type</span></span>](tabsrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="98243-122">指定形状和样式制表位位置或对齐的控件的属性。</span><span class="sxs-lookup"><span data-stu-id="98243-122">Specifies a property that controls shape and style tab stop position or alignment.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="98243-123">子元素</span><span class="sxs-lookup"><span data-stu-id="98243-123">Child elements</span></span>

|<span data-ttu-id="98243-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="98243-124">**Element**</span></span>|<span data-ttu-id="98243-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="98243-125">**Type**</span></span>|<span data-ttu-id="98243-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="98243-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="98243-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="98243-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="98243-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="98243-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="98243-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="98243-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="98243-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="98243-130">Attributes</span></span>

|<span data-ttu-id="98243-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="98243-131">**Attribute**</span></span>|<span data-ttu-id="98243-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="98243-132">**Type**</span></span>|<span data-ttu-id="98243-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="98243-133">**Required**</span></span>|<span data-ttu-id="98243-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="98243-134">**Description**</span></span>|<span data-ttu-id="98243-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="98243-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="98243-136">E</span><span class="sxs-lookup"><span data-stu-id="98243-136">E</span></span>  <br/> |<span data-ttu-id="98243-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="98243-137">xsd:string</span></span>  <br/> |<span data-ttu-id="98243-138">可选</span><span class="sxs-lookup"><span data-stu-id="98243-138">optional</span></span>  <br/> |<span data-ttu-id="98243-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="98243-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="98243-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="98243-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="98243-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="98243-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="98243-142">F</span><span class="sxs-lookup"><span data-stu-id="98243-142">F</span></span>  <br/> |<span data-ttu-id="98243-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="98243-143">xsd:string</span></span>  <br/> |<span data-ttu-id="98243-144">可选</span><span class="sxs-lookup"><span data-stu-id="98243-144">optional</span></span>  <br/> | <span data-ttu-id="98243-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="98243-145">Represents the element's formula.</span></span> <span data-ttu-id="98243-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="98243-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="98243-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="98243-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="98243-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="98243-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="98243-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="98243-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="98243-150">公式。</span><span class="sxs-lookup"><span data-stu-id="98243-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="98243-151">N</span><span class="sxs-lookup"><span data-stu-id="98243-151">N</span></span>  <br/> |<span data-ttu-id="98243-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="98243-152">xsd:string</span></span>  <br/> |<span data-ttu-id="98243-153">必需</span><span class="sxs-lookup"><span data-stu-id="98243-153">required</span></span>  <br/> |<span data-ttu-id="98243-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="98243-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="98243-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="98243-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="98243-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="98243-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="98243-157">U</span><span class="sxs-lookup"><span data-stu-id="98243-157">U</span></span>  <br/> |<span data-ttu-id="98243-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="98243-158">xsd:string</span></span>  <br/> |<span data-ttu-id="98243-159">可选</span><span class="sxs-lookup"><span data-stu-id="98243-159">optional</span></span>  <br/> |<span data-ttu-id="98243-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="98243-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="98243-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="98243-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="98243-162">V</span><span class="sxs-lookup"><span data-stu-id="98243-162">V</span></span>  <br/> |<span data-ttu-id="98243-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="98243-163">xsd:string</span></span>  <br/> |<span data-ttu-id="98243-164">可选</span><span class="sxs-lookup"><span data-stu-id="98243-164">optional</span></span>  <br/> |<span data-ttu-id="98243-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="98243-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="98243-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="98243-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="98243-167">说明</span><span class="sxs-lookup"><span data-stu-id="98243-167">Remarks</span></span>

<span data-ttu-id="98243-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="98243-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="98243-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="98243-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="98243-170">**值**</span><span class="sxs-lookup"><span data-stu-id="98243-170">**Value**</span></span>|<span data-ttu-id="98243-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="98243-171">**Description**</span></span>|<span data-ttu-id="98243-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="98243-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98243-173">对齐方式</span><span class="sxs-lookup"><span data-stu-id="98243-173">Alignment</span></span>  <br/> |<span data-ttu-id="98243-174">指定制表位的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="98243-174">Specifies the tab alignment.</span></span>  <br/> |[<span data-ttu-id="98243-175">Alignment Cell (Tabs Section)</span><span class="sxs-lookup"><span data-stu-id="98243-175">Alignment Cell (Tabs Section)</span></span>](alignment-cell-tabs-section.md) <br/> |
|<span data-ttu-id="98243-176">位置</span><span class="sxs-lookup"><span data-stu-id="98243-176">Position</span></span>  <br/> |<span data-ttu-id="98243-p104">指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。</span><span class="sxs-lookup"><span data-stu-id="98243-p104">Specifies the position of a tab stop. The tab position is independent of the scale of the drawing. If the drawing is scaled, the tab position remains the same.</span></span>  <br/> |[<span data-ttu-id="98243-180">Position Cell (Tabs Section)</span><span class="sxs-lookup"><span data-stu-id="98243-180">Position Cell (Tabs Section)</span></span>](position-cell-tabs-section.md) <br/> |
   

