---
title: 'Cell 元素 (Scratch Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af17b1c5-51ee-f46f-79d0-4f33369b66f1
description: 指定用于输入和测试其他单元格可引用的公式的工作区。
ms.openlocfilehash: 32e7eb2cfe13221ced2a8096acde412625d3ad33
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542322"
---
# <a name="cell-element-scratch-section-visio-xml"></a><span data-ttu-id="7826d-103">Cell 元素 (Scratch Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="7826d-103">Cell element (Scratch Section) (Visio XML)</span></span>

<span data-ttu-id="7826d-104">指定用于输入和测试其他单元格可引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="7826d-104">Specifies a work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7826d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7826d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7826d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7826d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7826d-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="7826d-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7826d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7826d-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7826d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7826d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7826d-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7826d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7826d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7826d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7826d-112">document.xml、masters.xml、master#.xml、pages.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="7826d-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7826d-113">定义</span><span class="sxs-lookup"><span data-stu-id="7826d-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7826d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7826d-114">Elements and attributes</span></span>

<span data-ttu-id="7826d-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7826d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7826d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7826d-116">Parent elements</span></span>

|<span data-ttu-id="7826d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="7826d-117">**Element**</span></span>|<span data-ttu-id="7826d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="7826d-118">**Type**</span></span>|<span data-ttu-id="7826d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="7826d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7826d-120">Row 元素 (Scratch Section) </span><span class="sxs-lookup"><span data-stu-id="7826d-120">Row element (Scratch Section)</span></span>](row-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="7826d-121">ScratchRow_Type</span><span class="sxs-lookup"><span data-stu-id="7826d-121">ScratchRow_Type</span></span>](scratch_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7826d-122">指定用于输入和测试其他单元格可引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="7826d-122">Specifies a work area for entering and testing formulas that can be referred to by other cells.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="7826d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7826d-123">Child elements</span></span>

|<span data-ttu-id="7826d-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="7826d-124">**Element**</span></span>|<span data-ttu-id="7826d-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="7826d-125">**Type**</span></span>|<span data-ttu-id="7826d-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="7826d-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7826d-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="7826d-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7826d-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="7826d-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7826d-129">指定对页面的引用。</span><span class="sxs-lookup"><span data-stu-id="7826d-129">Specifies a reference to a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="7826d-130">属性</span><span class="sxs-lookup"><span data-stu-id="7826d-130">Attributes</span></span>

|<span data-ttu-id="7826d-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="7826d-131">**Attribute**</span></span>|<span data-ttu-id="7826d-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="7826d-132">**Type**</span></span>|<span data-ttu-id="7826d-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="7826d-133">**Required**</span></span>|<span data-ttu-id="7826d-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="7826d-134">**Description**</span></span>|<span data-ttu-id="7826d-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="7826d-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7826d-136">E</span><span class="sxs-lookup"><span data-stu-id="7826d-136">E</span></span>  <br/> |<span data-ttu-id="7826d-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7826d-137">xsd:string</span></span>  <br/> |<span data-ttu-id="7826d-138">可选</span><span class="sxs-lookup"><span data-stu-id="7826d-138">optional</span></span>  <br/> |<span data-ttu-id="7826d-139">指示公式计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="7826d-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="7826d-140">**E** 的值是错误消息字符串 (的当前) ;**V** 属性的值是最后一个有效值。</span><span class="sxs-lookup"><span data-stu-id="7826d-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="7826d-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="7826d-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="7826d-142">F</span><span class="sxs-lookup"><span data-stu-id="7826d-142">F</span></span>  <br/> |<span data-ttu-id="7826d-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7826d-143">xsd:string</span></span>  <br/> |<span data-ttu-id="7826d-144">可选</span><span class="sxs-lookup"><span data-stu-id="7826d-144">optional</span></span>  <br/> | <span data-ttu-id="7826d-145">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="7826d-145">Represents the element's formula.</span></span> <span data-ttu-id="7826d-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="7826d-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="7826d-147">如果 (存在) ，则"设置一些公式"。</span><span class="sxs-lookup"><span data-stu-id="7826d-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="7826d-148">`No Formula` 如果公式在本地删除或阻止</span><span class="sxs-lookup"><span data-stu-id="7826d-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="7826d-149">`Inh` 如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="7826d-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="7826d-150">公式。</span><span class="sxs-lookup"><span data-stu-id="7826d-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="7826d-151">N</span><span class="sxs-lookup"><span data-stu-id="7826d-151">N</span></span>  <br/> |<span data-ttu-id="7826d-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7826d-152">xsd:string</span></span>  <br/> |<span data-ttu-id="7826d-153">必需</span><span class="sxs-lookup"><span data-stu-id="7826d-153">required</span></span>  <br/> |<span data-ttu-id="7826d-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7826d-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="7826d-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="7826d-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="7826d-156">请参阅下面的"备注"部分。</span><span class="sxs-lookup"><span data-stu-id="7826d-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="7826d-157">U</span><span class="sxs-lookup"><span data-stu-id="7826d-157">U</span></span>  <br/> |<span data-ttu-id="7826d-158">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7826d-158">xsd:string</span></span>  <br/> |<span data-ttu-id="7826d-159">可选</span><span class="sxs-lookup"><span data-stu-id="7826d-159">optional</span></span>  <br/> |<span data-ttu-id="7826d-160">表示度量单位 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="7826d-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="7826d-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="7826d-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="7826d-162">V</span><span class="sxs-lookup"><span data-stu-id="7826d-162">V</span></span>  <br/> |<span data-ttu-id="7826d-163">xsd：string</span><span class="sxs-lookup"><span data-stu-id="7826d-163">xsd:string</span></span>  <br/> |<span data-ttu-id="7826d-164">可选</span><span class="sxs-lookup"><span data-stu-id="7826d-164">optional</span></span>  <br/> |<span data-ttu-id="7826d-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7826d-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="7826d-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="7826d-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
### <a name="remarks"></a><span data-ttu-id="7826d-167">备注</span><span class="sxs-lookup"><span data-stu-id="7826d-167">Remarks</span></span>

<span data-ttu-id="7826d-168">此 **Cell** 元素的 **N** 属性必须是与 ShapeSheet 单元格对应的一组有限值之一。</span><span class="sxs-lookup"><span data-stu-id="7826d-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="7826d-169">请参阅下表以确定此 **Cell** 元素允许的 **N** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="7826d-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="7826d-170">**值**</span><span class="sxs-lookup"><span data-stu-id="7826d-170">**Value**</span></span>|<span data-ttu-id="7826d-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="7826d-171">**Description**</span></span>|<span data-ttu-id="7826d-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7826d-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7826d-173">A</span><span class="sxs-lookup"><span data-stu-id="7826d-173">A</span></span>  <br/> |<span data-ttu-id="7826d-174">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-174">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-175">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-175">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="7826d-176">B</span><span class="sxs-lookup"><span data-stu-id="7826d-176">B</span></span>  <br/> |<span data-ttu-id="7826d-177">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-177">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-178">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-178">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="7826d-179">C</span><span class="sxs-lookup"><span data-stu-id="7826d-179">C</span></span>  <br/> |<span data-ttu-id="7826d-180">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-180">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-181">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-181">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="7826d-182">D</span><span class="sxs-lookup"><span data-stu-id="7826d-182">D</span></span>  <br/> |<span data-ttu-id="7826d-183">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-183">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-184">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-184">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="7826d-185">X</span><span class="sxs-lookup"><span data-stu-id="7826d-185">X</span></span>  <br/> |<span data-ttu-id="7826d-186">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-186">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-187">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-187">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="7826d-188">Y</span><span class="sxs-lookup"><span data-stu-id="7826d-188">Y</span></span>  <br/> |<span data-ttu-id="7826d-189">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="7826d-189">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="7826d-190">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="7826d-190">Scratch Section</span></span>](scratch-section.md) <br/> |
   

