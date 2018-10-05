---
title: 单元格元素 （用户定义的单元格部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ab7a11a0-a413-d4fe-ddf1-0d2e967dc21d
description: 用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。
ms.openlocfilehash: 0ce456b624f4a4b12a3f2fdc73f56651ea6985ed
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397497"
---
# <a name="cell-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="c01fb-103">单元格元素 （用户定义的单元格部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c01fb-103">Cell element (User-defined Cells Section) ('Visio XML')</span></span>

<span data-ttu-id="c01fb-104">用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。</span><span class="sxs-lookup"><span data-stu-id="c01fb-104">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c01fb-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c01fb-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c01fb-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c01fb-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c01fb-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="c01fb-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c01fb-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c01fb-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c01fb-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c01fb-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c01fb-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="c01fb-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c01fb-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c01fb-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c01fb-112">document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml</span><span class="sxs-lookup"><span data-stu-id="c01fb-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c01fb-113">定义</span><span class="sxs-lookup"><span data-stu-id="c01fb-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c01fb-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c01fb-114">Elements and attributes</span></span>

<span data-ttu-id="c01fb-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c01fb-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c01fb-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c01fb-116">Parent elements</span></span>

|<span data-ttu-id="c01fb-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c01fb-117">**Element**</span></span>|<span data-ttu-id="c01fb-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c01fb-118">**Type**</span></span>|<span data-ttu-id="c01fb-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c01fb-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c01fb-120">Row 元素（“User-defined Cells”部分）</span><span class="sxs-lookup"><span data-stu-id="c01fb-120">Row element (User-defined Cells Section)</span></span>](row-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="c01fb-121">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="c01fb-121">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c01fb-122">用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。</span><span class="sxs-lookup"><span data-stu-id="c01fb-122">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c01fb-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c01fb-123">Child elements</span></span>

|<span data-ttu-id="c01fb-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="c01fb-124">**Element**</span></span>|<span data-ttu-id="c01fb-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="c01fb-125">**Type**</span></span>|<span data-ttu-id="c01fb-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c01fb-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c01fb-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="c01fb-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c01fb-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="c01fb-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c01fb-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="c01fb-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c01fb-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="c01fb-130">Attributes</span></span>

|<span data-ttu-id="c01fb-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="c01fb-131">**Attribute**</span></span>|<span data-ttu-id="c01fb-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="c01fb-132">**Type**</span></span>|<span data-ttu-id="c01fb-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="c01fb-133">**Required**</span></span>|<span data-ttu-id="c01fb-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="c01fb-134">**Description**</span></span>|<span data-ttu-id="c01fb-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c01fb-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c01fb-136">E</span><span class="sxs-lookup"><span data-stu-id="c01fb-136">E</span></span>  <br/> |<span data-ttu-id="c01fb-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c01fb-137">xsd:string</span></span>  <br/> |<span data-ttu-id="c01fb-138">可选</span><span class="sxs-lookup"><span data-stu-id="c01fb-138">optional</span></span>  <br/> |<span data-ttu-id="c01fb-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="c01fb-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="c01fb-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="c01fb-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="c01fb-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="c01fb-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="c01fb-142">F</span><span class="sxs-lookup"><span data-stu-id="c01fb-142">F</span></span>  <br/> |<span data-ttu-id="c01fb-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c01fb-143">xsd:string</span></span>  <br/> |<span data-ttu-id="c01fb-144">可选</span><span class="sxs-lookup"><span data-stu-id="c01fb-144">optional</span></span>  <br/> | <span data-ttu-id="c01fb-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="c01fb-145">Represents the element's formula.</span></span> <span data-ttu-id="c01fb-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="c01fb-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="c01fb-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="c01fb-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="c01fb-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="c01fb-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="c01fb-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="c01fb-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="c01fb-150">公式。</span><span class="sxs-lookup"><span data-stu-id="c01fb-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="c01fb-151">N</span><span class="sxs-lookup"><span data-stu-id="c01fb-151">N</span></span>  <br/> |<span data-ttu-id="c01fb-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c01fb-152">xsd:string</span></span>  <br/> |<span data-ttu-id="c01fb-153">必需</span><span class="sxs-lookup"><span data-stu-id="c01fb-153">required</span></span>  <br/> |<span data-ttu-id="c01fb-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="c01fb-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="c01fb-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="c01fb-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="c01fb-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="c01fb-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="c01fb-157">U</span><span class="sxs-lookup"><span data-stu-id="c01fb-157">U</span></span>  <br/> |<span data-ttu-id="c01fb-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c01fb-158">xsd:string</span></span>  <br/> |<span data-ttu-id="c01fb-159">可选</span><span class="sxs-lookup"><span data-stu-id="c01fb-159">optional</span></span>  <br/> |<span data-ttu-id="c01fb-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="c01fb-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="c01fb-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="c01fb-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="c01fb-162">V</span><span class="sxs-lookup"><span data-stu-id="c01fb-162">V</span></span>  <br/> |<span data-ttu-id="c01fb-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c01fb-163">xsd:string</span></span>  <br/> |<span data-ttu-id="c01fb-164">可选</span><span class="sxs-lookup"><span data-stu-id="c01fb-164">optional</span></span>  <br/> |<span data-ttu-id="c01fb-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="c01fb-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="c01fb-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="c01fb-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c01fb-167">说明</span><span class="sxs-lookup"><span data-stu-id="c01fb-167">Remarks</span></span>

<span data-ttu-id="c01fb-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="c01fb-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="c01fb-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="c01fb-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="c01fb-170">**值**</span><span class="sxs-lookup"><span data-stu-id="c01fb-170">**Value**</span></span>|<span data-ttu-id="c01fb-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="c01fb-171">**Description**</span></span>|<span data-ttu-id="c01fb-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="c01fb-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c01fb-173">提示</span><span class="sxs-lookup"><span data-stu-id="c01fb-173">Prompt</span></span>  <br/> |<span data-ttu-id="c01fb-174">为用户定义的单元格指定说明性提示或注释。</span><span class="sxs-lookup"><span data-stu-id="c01fb-174">Specifies a descriptive prompt or comment for the user-defined cell.</span></span>  <br/> |[<span data-ttu-id="c01fb-175">Prompt Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="c01fb-175">Prompt Cell (User-Defined Cells Section)</span></span>](prompt-cell-user-defined-cells-section.md) <br/> |
|<span data-ttu-id="c01fb-176">值</span><span class="sxs-lookup"><span data-stu-id="c01fb-176">Value</span></span>  <br/> |<span data-ttu-id="c01fb-177">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="c01fb-177">Specifies a value for the corresponding user-defined cell.</span></span>  <br/> |[<span data-ttu-id="c01fb-178">Value Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="c01fb-178">Value Cell (User-Defined Cells Section)</span></span>](value-cell-user-defined-cells-section.md) <br/> |
   

