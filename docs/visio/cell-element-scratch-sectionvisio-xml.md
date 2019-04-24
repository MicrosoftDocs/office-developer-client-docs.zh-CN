---
title: Cell 元素 ("草稿" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: af17b1c5-51ee-f46f-79d0-4f33369b66f1
description: 指定用于输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: 147cc152ec20e3e2b032b91f6387ec06a3cb1d6f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339527"
---
# <a name="cell-element-scratch-section-visio-xml"></a><span data-ttu-id="673fa-103">Cell 元素 ("草稿" 部分) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="673fa-103">Cell element (Scratch Section) ('Visio XML')</span></span>

<span data-ttu-id="673fa-104">指定用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="673fa-104">Specifies a work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="673fa-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="673fa-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="673fa-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="673fa-106">**Element type**</span></span> <br/> |[<span data-ttu-id="673fa-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="673fa-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="673fa-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="673fa-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="673fa-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="673fa-109">**Schema file**</span></span> <br/> |<span data-ttu-id="673fa-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="673fa-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="673fa-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="673fa-111">**Document parts**</span></span> <br/> |<span data-ttu-id="673fa-112">document .xml、.master、master # .xml、pages、.xml 和第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="673fa-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="673fa-113">定义</span><span class="sxs-lookup"><span data-stu-id="673fa-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="673fa-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="673fa-114">Elements and attributes</span></span>

<span data-ttu-id="673fa-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="673fa-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="673fa-116">父元素</span><span class="sxs-lookup"><span data-stu-id="673fa-116">Parent elements</span></span>

|<span data-ttu-id="673fa-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="673fa-117">**Element**</span></span>|<span data-ttu-id="673fa-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="673fa-118">**Type**</span></span>|<span data-ttu-id="673fa-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="673fa-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="673fa-120">Row 元素 ("草稿" 部分)</span><span class="sxs-lookup"><span data-stu-id="673fa-120">Row element (Scratch Section)</span></span>](row-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="673fa-121">ScratchRow_Type</span><span class="sxs-lookup"><span data-stu-id="673fa-121">ScratchRow_Type</span></span>](scratch_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="673fa-122">指定用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="673fa-122">Specifies a work area for entering and testing formulas that can be referred to by other cells.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="673fa-123">子元素</span><span class="sxs-lookup"><span data-stu-id="673fa-123">Child elements</span></span>

|<span data-ttu-id="673fa-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="673fa-124">**Element**</span></span>|<span data-ttu-id="673fa-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="673fa-125">**Type**</span></span>|<span data-ttu-id="673fa-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="673fa-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="673fa-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="673fa-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="673fa-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="673fa-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="673fa-129">指定对页面的引用。</span><span class="sxs-lookup"><span data-stu-id="673fa-129">Specifies a reference to a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="673fa-130">属性</span><span class="sxs-lookup"><span data-stu-id="673fa-130">Attributes</span></span>

|<span data-ttu-id="673fa-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="673fa-131">**Attribute**</span></span>|<span data-ttu-id="673fa-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="673fa-132">**Type**</span></span>|<span data-ttu-id="673fa-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="673fa-133">**Required**</span></span>|<span data-ttu-id="673fa-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="673fa-134">**Description**</span></span>|<span data-ttu-id="673fa-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="673fa-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="673fa-136">E</span><span class="sxs-lookup"><span data-stu-id="673fa-136">E</span></span>  <br/> |<span data-ttu-id="673fa-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="673fa-137">xsd:string</span></span>  <br/> |<span data-ttu-id="673fa-138">可选</span><span class="sxs-lookup"><span data-stu-id="673fa-138">optional</span></span>  <br/> |<span data-ttu-id="673fa-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="673fa-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="673fa-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="673fa-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="673fa-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="673fa-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="673fa-142">F</span><span class="sxs-lookup"><span data-stu-id="673fa-142">F</span></span>  <br/> |<span data-ttu-id="673fa-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="673fa-143">xsd:string</span></span>  <br/> |<span data-ttu-id="673fa-144">可选</span><span class="sxs-lookup"><span data-stu-id="673fa-144">optional</span></span>  <br/> | <span data-ttu-id="673fa-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="673fa-145">Represents the element's formula.</span></span> <span data-ttu-id="673fa-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="673fa-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="673fa-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="673fa-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="673fa-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="673fa-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="673fa-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="673fa-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="673fa-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="673fa-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="673fa-151">N</span><span class="sxs-lookup"><span data-stu-id="673fa-151">N</span></span>  <br/> |<span data-ttu-id="673fa-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="673fa-152">xsd:string</span></span>  <br/> |<span data-ttu-id="673fa-153">必需</span><span class="sxs-lookup"><span data-stu-id="673fa-153">required</span></span>  <br/> |<span data-ttu-id="673fa-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="673fa-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="673fa-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="673fa-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="673fa-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="673fa-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="673fa-157">U</span><span class="sxs-lookup"><span data-stu-id="673fa-157">U</span></span>  <br/> |<span data-ttu-id="673fa-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="673fa-158">xsd:string</span></span>  <br/> |<span data-ttu-id="673fa-159">可选</span><span class="sxs-lookup"><span data-stu-id="673fa-159">optional</span></span>  <br/> |<span data-ttu-id="673fa-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="673fa-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="673fa-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="673fa-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="673fa-162">部分</span><span class="sxs-lookup"><span data-stu-id="673fa-162">V</span></span>  <br/> |<span data-ttu-id="673fa-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="673fa-163">xsd:string</span></span>  <br/> |<span data-ttu-id="673fa-164">可选</span><span class="sxs-lookup"><span data-stu-id="673fa-164">optional</span></span>  <br/> |<span data-ttu-id="673fa-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="673fa-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="673fa-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="673fa-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
### <a name="remarks"></a><span data-ttu-id="673fa-167">注解</span><span class="sxs-lookup"><span data-stu-id="673fa-167">Remarks</span></span>

<span data-ttu-id="673fa-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="673fa-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="673fa-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="673fa-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="673fa-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="673fa-170">**Value**</span></span>|<span data-ttu-id="673fa-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="673fa-171">**Description**</span></span>|<span data-ttu-id="673fa-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="673fa-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="673fa-173">A</span><span class="sxs-lookup"><span data-stu-id="673fa-173">A</span></span>  <br/> |<span data-ttu-id="673fa-174">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-174">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-175">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-175">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="673fa-176">B</span><span class="sxs-lookup"><span data-stu-id="673fa-176">B</span></span>  <br/> |<span data-ttu-id="673fa-177">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-177">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-178">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-178">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="673fa-179">C</span><span class="sxs-lookup"><span data-stu-id="673fa-179">C</span></span>  <br/> |<span data-ttu-id="673fa-180">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-180">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-181">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-181">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="673fa-182">D</span><span class="sxs-lookup"><span data-stu-id="673fa-182">D</span></span>  <br/> |<span data-ttu-id="673fa-183">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-183">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-184">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-184">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="673fa-185">X</span><span class="sxs-lookup"><span data-stu-id="673fa-185">X</span></span>  <br/> |<span data-ttu-id="673fa-186">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-186">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-187">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-187">Scratch Section</span></span>](scratch-section.md) <br/> |
|<span data-ttu-id="673fa-188">Y</span><span class="sxs-lookup"><span data-stu-id="673fa-188">Y</span></span>  <br/> |<span data-ttu-id="673fa-189">可用于输入或测试公式的草稿单元格。</span><span class="sxs-lookup"><span data-stu-id="673fa-189">A scratch cell that you can use for entering or testing formulas.</span></span>  <br/> |[<span data-ttu-id="673fa-190">Scratch Section</span><span class="sxs-lookup"><span data-stu-id="673fa-190">Scratch Section</span></span>](scratch-section.md) <br/> |
   

