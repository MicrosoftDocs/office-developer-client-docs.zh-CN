---
title: Cell 元素 ("用户定义的单元格" 部分) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ab7a11a0-a413-d4fe-ddf1-0d2e967dc21d
description: 用户指定的信息部分的一个属性, 可由其他单元格和附加工具引用。
ms.openlocfilehash: 5b7e3eb1f4550430e4df51098b86862fcc7400da
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539312"
---
# <a name="cell-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="e97bc-103">Cell 元素 ("用户定义的单元格" 部分) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e97bc-103">Cell element (User-defined Cells Section) (Visio XML)</span></span>

<span data-ttu-id="e97bc-104">用户指定的信息部分的一个属性, 可由其他单元格和附加工具引用。</span><span class="sxs-lookup"><span data-stu-id="e97bc-104">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e97bc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e97bc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e97bc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e97bc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e97bc-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="e97bc-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e97bc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e97bc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e97bc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e97bc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e97bc-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e97bc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e97bc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e97bc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e97bc-112">document .xml、.master、master # .xml、pages、.xml 和第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="e97bc-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e97bc-113">定义</span><span class="sxs-lookup"><span data-stu-id="e97bc-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e97bc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e97bc-114">Elements and attributes</span></span>

<span data-ttu-id="e97bc-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e97bc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e97bc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e97bc-116">Parent elements</span></span>

|<span data-ttu-id="e97bc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e97bc-117">**Element**</span></span>|<span data-ttu-id="e97bc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e97bc-118">**Type**</span></span>|<span data-ttu-id="e97bc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e97bc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e97bc-120">Row 元素 ("用户定义的单元格" 部分)</span><span class="sxs-lookup"><span data-stu-id="e97bc-120">Row element (User-defined Cells Section)</span></span>](row-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="e97bc-121">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="e97bc-121">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e97bc-122">用户指定的信息部分的一个属性, 可由其他单元格和附加工具引用。</span><span class="sxs-lookup"><span data-stu-id="e97bc-122">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e97bc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e97bc-123">Child elements</span></span>

|<span data-ttu-id="e97bc-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="e97bc-124">**Element**</span></span>|<span data-ttu-id="e97bc-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e97bc-125">**Type**</span></span>|<span data-ttu-id="e97bc-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="e97bc-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e97bc-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="e97bc-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e97bc-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="e97bc-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e97bc-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="e97bc-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="e97bc-130">属性</span><span class="sxs-lookup"><span data-stu-id="e97bc-130">Attributes</span></span>

|<span data-ttu-id="e97bc-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="e97bc-131">**Attribute**</span></span>|<span data-ttu-id="e97bc-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="e97bc-132">**Type**</span></span>|<span data-ttu-id="e97bc-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="e97bc-133">**Required**</span></span>|<span data-ttu-id="e97bc-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="e97bc-134">**Description**</span></span>|<span data-ttu-id="e97bc-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e97bc-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e97bc-136">E</span><span class="sxs-lookup"><span data-stu-id="e97bc-136">E</span></span>  <br/> |<span data-ttu-id="e97bc-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e97bc-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e97bc-138">可选</span><span class="sxs-lookup"><span data-stu-id="e97bc-138">optional</span></span>  <br/> |<span data-ttu-id="e97bc-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="e97bc-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="e97bc-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="e97bc-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="e97bc-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="e97bc-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="e97bc-142">F</span><span class="sxs-lookup"><span data-stu-id="e97bc-142">F</span></span>  <br/> |<span data-ttu-id="e97bc-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e97bc-143">xsd:string</span></span>  <br/> |<span data-ttu-id="e97bc-144">可选</span><span class="sxs-lookup"><span data-stu-id="e97bc-144">optional</span></span>  <br/> | <span data-ttu-id="e97bc-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="e97bc-145">Represents the element's formula.</span></span> <span data-ttu-id="e97bc-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="e97bc-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="e97bc-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="e97bc-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="e97bc-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="e97bc-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="e97bc-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="e97bc-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="e97bc-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="e97bc-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="e97bc-151">N</span><span class="sxs-lookup"><span data-stu-id="e97bc-151">N</span></span>  <br/> |<span data-ttu-id="e97bc-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e97bc-152">xsd:string</span></span>  <br/> |<span data-ttu-id="e97bc-153">必需</span><span class="sxs-lookup"><span data-stu-id="e97bc-153">required</span></span>  <br/> |<span data-ttu-id="e97bc-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="e97bc-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="e97bc-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="e97bc-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="e97bc-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="e97bc-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="e97bc-157">U</span><span class="sxs-lookup"><span data-stu-id="e97bc-157">U</span></span>  <br/> |<span data-ttu-id="e97bc-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e97bc-158">xsd:string</span></span>  <br/> |<span data-ttu-id="e97bc-159">可选</span><span class="sxs-lookup"><span data-stu-id="e97bc-159">optional</span></span>  <br/> |<span data-ttu-id="e97bc-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="e97bc-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="e97bc-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="e97bc-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="e97bc-162">部分</span><span class="sxs-lookup"><span data-stu-id="e97bc-162">V</span></span>  <br/> |<span data-ttu-id="e97bc-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e97bc-163">xsd:string</span></span>  <br/> |<span data-ttu-id="e97bc-164">可选</span><span class="sxs-lookup"><span data-stu-id="e97bc-164">optional</span></span>  <br/> |<span data-ttu-id="e97bc-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="e97bc-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="e97bc-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="e97bc-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e97bc-167">备注</span><span class="sxs-lookup"><span data-stu-id="e97bc-167">Remarks</span></span>

<span data-ttu-id="e97bc-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="e97bc-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="e97bc-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="e97bc-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="e97bc-170">**值**</span><span class="sxs-lookup"><span data-stu-id="e97bc-170">**Value**</span></span>|<span data-ttu-id="e97bc-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="e97bc-171">**Description**</span></span>|<span data-ttu-id="e97bc-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e97bc-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e97bc-173">Prompt</span><span class="sxs-lookup"><span data-stu-id="e97bc-173">Prompt</span></span>  <br/> |<span data-ttu-id="e97bc-174">为用户定义的单元格指定说明性提示或注释。</span><span class="sxs-lookup"><span data-stu-id="e97bc-174">Specifies a descriptive prompt or comment for the user-defined cell.</span></span>  <br/> |[<span data-ttu-id="e97bc-175">Prompt Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="e97bc-175">Prompt Cell (User-Defined Cells Section)</span></span>](prompt-cell-user-defined-cells-section.md) <br/> |
|<span data-ttu-id="e97bc-176">值</span><span class="sxs-lookup"><span data-stu-id="e97bc-176">Value</span></span>  <br/> |<span data-ttu-id="e97bc-177">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="e97bc-177">Specifies a value for the corresponding user-defined cell.</span></span>  <br/> |[<span data-ttu-id="e97bc-178">Value Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="e97bc-178">Value Cell (User-Defined Cells Section)</span></span>](value-cell-user-defined-cells-section.md) <br/> |
   

