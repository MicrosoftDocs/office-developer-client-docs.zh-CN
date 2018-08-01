---
title: 单元格元素 （用户定义的单元格部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ab7a11a0-a413-d4fe-ddf1-0d2e967dc21d
description: 用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。
ms.openlocfilehash: 40555c58e6afdb3eefe5b1a14d4155ad4e57ed6e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779844"
---
# <a name="cell-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="782e5-103">单元格元素 （用户定义的单元格部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="782e5-103">Cell element (User-defined Cells Section) ('Visio XML')</span></span>

<span data-ttu-id="782e5-104">用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。</span><span class="sxs-lookup"><span data-stu-id="782e5-104">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="782e5-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="782e5-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="782e5-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="782e5-106">**Element type**</span></span> <br/> |[<span data-ttu-id="782e5-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="782e5-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="782e5-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="782e5-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="782e5-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="782e5-109">**Schema file**</span></span> <br/> |<span data-ttu-id="782e5-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="782e5-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="782e5-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="782e5-111">**Document parts**</span></span> <br/> |<span data-ttu-id="782e5-112">document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml</span><span class="sxs-lookup"><span data-stu-id="782e5-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="782e5-113">定义</span><span class="sxs-lookup"><span data-stu-id="782e5-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="782e5-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="782e5-114">Elements and attributes</span></span>

<span data-ttu-id="782e5-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="782e5-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="782e5-116">父元素</span><span class="sxs-lookup"><span data-stu-id="782e5-116">Parent elements</span></span>

|<span data-ttu-id="782e5-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="782e5-117">**Element**</span></span>|<span data-ttu-id="782e5-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="782e5-118">**Type**</span></span>|<span data-ttu-id="782e5-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="782e5-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="782e5-120">Row 元素（“User-defined Cells”部分）</span><span class="sxs-lookup"><span data-stu-id="782e5-120">Row element (User-defined Cells Section)</span></span>](row-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="782e5-121">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="782e5-121">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="782e5-122">用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。</span><span class="sxs-lookup"><span data-stu-id="782e5-122">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="782e5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="782e5-123">Child elements</span></span>

|<span data-ttu-id="782e5-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="782e5-124">**Element**</span></span>|<span data-ttu-id="782e5-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="782e5-125">**Type**</span></span>|<span data-ttu-id="782e5-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="782e5-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="782e5-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="782e5-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="782e5-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="782e5-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="782e5-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="782e5-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="782e5-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="782e5-130">Attributes</span></span>

|<span data-ttu-id="782e5-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="782e5-131">**Attribute**</span></span>|<span data-ttu-id="782e5-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="782e5-132">**Type**</span></span>|<span data-ttu-id="782e5-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="782e5-133">**Required**</span></span>|<span data-ttu-id="782e5-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="782e5-134">**Description**</span></span>|<span data-ttu-id="782e5-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="782e5-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="782e5-136">E</span><span class="sxs-lookup"><span data-stu-id="782e5-136">E</span></span>  <br/> |<span data-ttu-id="782e5-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="782e5-137">xsd:string</span></span>  <br/> |<span data-ttu-id="782e5-138">可选</span><span class="sxs-lookup"><span data-stu-id="782e5-138">optional</span></span>  <br/> |<span data-ttu-id="782e5-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="782e5-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="782e5-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="782e5-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="782e5-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="782e5-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="782e5-142">F</span><span class="sxs-lookup"><span data-stu-id="782e5-142">F</span></span>  <br/> |<span data-ttu-id="782e5-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="782e5-143">xsd:string</span></span>  <br/> |<span data-ttu-id="782e5-144">可选</span><span class="sxs-lookup"><span data-stu-id="782e5-144">optional</span></span>  <br/> | <span data-ttu-id="782e5-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="782e5-145">Represents the element's formula.</span></span> <span data-ttu-id="782e5-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="782e5-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="782e5-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="782e5-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="782e5-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="782e5-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="782e5-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="782e5-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="782e5-150">公式。</span><span class="sxs-lookup"><span data-stu-id="782e5-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="782e5-151">N</span><span class="sxs-lookup"><span data-stu-id="782e5-151">N</span></span>  <br/> |<span data-ttu-id="782e5-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="782e5-152">xsd:string</span></span>  <br/> |<span data-ttu-id="782e5-153">必需</span><span class="sxs-lookup"><span data-stu-id="782e5-153">required</span></span>  <br/> |<span data-ttu-id="782e5-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="782e5-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="782e5-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="782e5-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="782e5-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="782e5-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="782e5-157">U</span><span class="sxs-lookup"><span data-stu-id="782e5-157">U</span></span>  <br/> |<span data-ttu-id="782e5-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="782e5-158">xsd:string</span></span>  <br/> |<span data-ttu-id="782e5-159">可选</span><span class="sxs-lookup"><span data-stu-id="782e5-159">optional</span></span>  <br/> |<span data-ttu-id="782e5-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="782e5-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="782e5-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="782e5-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="782e5-162">V</span><span class="sxs-lookup"><span data-stu-id="782e5-162">V</span></span>  <br/> |<span data-ttu-id="782e5-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="782e5-163">xsd:string</span></span>  <br/> |<span data-ttu-id="782e5-164">可选</span><span class="sxs-lookup"><span data-stu-id="782e5-164">optional</span></span>  <br/> |<span data-ttu-id="782e5-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="782e5-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="782e5-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="782e5-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="782e5-167">说明</span><span class="sxs-lookup"><span data-stu-id="782e5-167">Remarks</span></span>

<span data-ttu-id="782e5-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="782e5-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="782e5-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="782e5-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="782e5-170">**值**</span><span class="sxs-lookup"><span data-stu-id="782e5-170">**Value**</span></span>|<span data-ttu-id="782e5-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="782e5-171">**Description**</span></span>|<span data-ttu-id="782e5-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="782e5-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="782e5-173">提示</span><span class="sxs-lookup"><span data-stu-id="782e5-173">Prompt</span></span>  <br/> |<span data-ttu-id="782e5-174">为用户定义的单元格指定说明性提示或注释。</span><span class="sxs-lookup"><span data-stu-id="782e5-174">Specifies a descriptive prompt or comment for the user-defined cell.</span></span>  <br/> |[<span data-ttu-id="782e5-175">Prompt Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="782e5-175">Prompt Cell (User-Defined Cells Section)</span></span>](prompt-cell-user-defined-cells-section.md) <br/> |
|<span data-ttu-id="782e5-176">值</span><span class="sxs-lookup"><span data-stu-id="782e5-176">Value</span></span>  <br/> |<span data-ttu-id="782e5-177">为相应的用户定义的单元格指定值。</span><span class="sxs-lookup"><span data-stu-id="782e5-177">Specifies a value for the corresponding user-defined cell.</span></span>  <br/> |[<span data-ttu-id="782e5-178">Value Cell (User-Defined Cells Section)</span><span class="sxs-lookup"><span data-stu-id="782e5-178">Value Cell (User-Defined Cells Section)</span></span>](value-cell-user-defined-cells-section.md) <br/> |
   

