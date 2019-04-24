---
title: Cell 元素 ("Tabs" 内容) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4292d489-fb7c-9d5d-9bec-2a1a0772d8ba
description: 指定用于控制形状和样式的制表位位置或对齐方式的属性。
ms.openlocfilehash: c6641c452144544dc769616130c96d6cf89aca23
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339639"
---
# <a name="cell-element-tabs-section-visio-xml"></a><span data-ttu-id="ac14b-103">Cell 元素 ("Tabs" 内容) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="ac14b-103">Cell element (Tabs Section) ('Visio XML')</span></span>

<span data-ttu-id="ac14b-104">指定用于控制形状和样式的制表位位置或对齐方式的属性。</span><span class="sxs-lookup"><span data-stu-id="ac14b-104">Specifies a property that controls shape and style tab stop position or alignment.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="ac14b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ac14b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ac14b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ac14b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ac14b-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="ac14b-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ac14b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ac14b-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ac14b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ac14b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ac14b-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="ac14b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ac14b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ac14b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ac14b-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="ac14b-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ac14b-113">定义</span><span class="sxs-lookup"><span data-stu-id="ac14b-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ac14b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ac14b-114">Elements and attributes</span></span>

<span data-ttu-id="ac14b-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="ac14b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ac14b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ac14b-116">Parent elements</span></span>

|<span data-ttu-id="ac14b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="ac14b-117">**Element**</span></span>|<span data-ttu-id="ac14b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ac14b-118">**Type**</span></span>|<span data-ttu-id="ac14b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac14b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ac14b-120">Row 元素 ("Tabs" 部分)</span><span class="sxs-lookup"><span data-stu-id="ac14b-120">Row element (Tabs Section)</span></span>](row-element-tabs-sectionvisio-xml.md) <br/> |[<span data-ttu-id="ac14b-121">TabsRow_Type</span><span class="sxs-lookup"><span data-stu-id="ac14b-121">TabsRow_Type</span></span>](tabsrow_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ac14b-122">指定用于控制形状和样式的制表位位置或对齐方式的属性。</span><span class="sxs-lookup"><span data-stu-id="ac14b-122">Specifies a property that controls shape and style tab stop position or alignment.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="ac14b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ac14b-123">Child elements</span></span>

|<span data-ttu-id="ac14b-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="ac14b-124">**Element**</span></span>|<span data-ttu-id="ac14b-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="ac14b-125">**Type**</span></span>|<span data-ttu-id="ac14b-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac14b-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ac14b-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="ac14b-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ac14b-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="ac14b-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ac14b-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="ac14b-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="ac14b-130">属性</span><span class="sxs-lookup"><span data-stu-id="ac14b-130">Attributes</span></span>

|<span data-ttu-id="ac14b-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="ac14b-131">**Attribute**</span></span>|<span data-ttu-id="ac14b-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="ac14b-132">**Type**</span></span>|<span data-ttu-id="ac14b-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="ac14b-133">**Required**</span></span>|<span data-ttu-id="ac14b-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="ac14b-134">**Description**</span></span>|<span data-ttu-id="ac14b-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ac14b-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac14b-136">E</span><span class="sxs-lookup"><span data-stu-id="ac14b-136">E</span></span>  <br/> |<span data-ttu-id="ac14b-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ac14b-137">xsd:string</span></span>  <br/> |<span data-ttu-id="ac14b-138">可选</span><span class="sxs-lookup"><span data-stu-id="ac14b-138">optional</span></span>  <br/> |<span data-ttu-id="ac14b-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="ac14b-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="ac14b-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="ac14b-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="ac14b-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="ac14b-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="ac14b-142">F</span><span class="sxs-lookup"><span data-stu-id="ac14b-142">F</span></span>  <br/> |<span data-ttu-id="ac14b-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ac14b-143">xsd:string</span></span>  <br/> |<span data-ttu-id="ac14b-144">可选</span><span class="sxs-lookup"><span data-stu-id="ac14b-144">optional</span></span>  <br/> | <span data-ttu-id="ac14b-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="ac14b-145">Represents the element's formula.</span></span> <span data-ttu-id="ac14b-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="ac14b-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="ac14b-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="ac14b-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="ac14b-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="ac14b-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="ac14b-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="ac14b-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="ac14b-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="ac14b-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="ac14b-151">N</span><span class="sxs-lookup"><span data-stu-id="ac14b-151">N</span></span>  <br/> |<span data-ttu-id="ac14b-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ac14b-152">xsd:string</span></span>  <br/> |<span data-ttu-id="ac14b-153">必需</span><span class="sxs-lookup"><span data-stu-id="ac14b-153">required</span></span>  <br/> |<span data-ttu-id="ac14b-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="ac14b-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="ac14b-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="ac14b-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="ac14b-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="ac14b-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="ac14b-157">U</span><span class="sxs-lookup"><span data-stu-id="ac14b-157">U</span></span>  <br/> |<span data-ttu-id="ac14b-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ac14b-158">xsd:string</span></span>  <br/> |<span data-ttu-id="ac14b-159">可选</span><span class="sxs-lookup"><span data-stu-id="ac14b-159">optional</span></span>  <br/> |<span data-ttu-id="ac14b-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="ac14b-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="ac14b-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="ac14b-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="ac14b-162">部分</span><span class="sxs-lookup"><span data-stu-id="ac14b-162">V</span></span>  <br/> |<span data-ttu-id="ac14b-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ac14b-163">xsd:string</span></span>  <br/> |<span data-ttu-id="ac14b-164">可选</span><span class="sxs-lookup"><span data-stu-id="ac14b-164">optional</span></span>  <br/> |<span data-ttu-id="ac14b-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ac14b-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="ac14b-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="ac14b-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac14b-167">注解</span><span class="sxs-lookup"><span data-stu-id="ac14b-167">Remarks</span></span>

<span data-ttu-id="ac14b-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="ac14b-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="ac14b-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="ac14b-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="ac14b-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="ac14b-170">**Value**</span></span>|<span data-ttu-id="ac14b-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="ac14b-171">**Description**</span></span>|<span data-ttu-id="ac14b-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="ac14b-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac14b-173">Alignment</span><span class="sxs-lookup"><span data-stu-id="ac14b-173">Alignment</span></span>  <br/> |<span data-ttu-id="ac14b-174">指定制表位的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="ac14b-174">Specifies the tab alignment.</span></span>  <br/> |[<span data-ttu-id="ac14b-175">Alignment Cell (Tabs Section)</span><span class="sxs-lookup"><span data-stu-id="ac14b-175">Alignment Cell (Tabs Section)</span></span>](alignment-cell-tabs-section.md) <br/> |
|<span data-ttu-id="ac14b-176">Position</span><span class="sxs-lookup"><span data-stu-id="ac14b-176">Position</span></span>  <br/> |<span data-ttu-id="ac14b-p104">指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。</span><span class="sxs-lookup"><span data-stu-id="ac14b-p104">Specifies the position of a tab stop. The tab position is independent of the scale of the drawing. If the drawing is scaled, the tab position remains the same.</span></span>  <br/> |[<span data-ttu-id="ac14b-180">Position Cell (Tabs Section)</span><span class="sxs-lookup"><span data-stu-id="ac14b-180">Position Cell (Tabs Section)</span></span>](position-cell-tabs-section.md) <br/> |
   

