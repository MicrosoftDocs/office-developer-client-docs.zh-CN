---
title: 单元格 （geometry 内容） (Visio XML) 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 82dcad38-d5fa-4892-91d9-1f3f25f1e600
description: 定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。
ms.openlocfilehash: f7ac096206b9197d71691f485a7c5aafc08eb2c8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779862"
---
# <a name="cell-element-geometry-section-visio-xml"></a><span data-ttu-id="27647-103">单元格 （geometry 内容） (Visio XML) 元素</span><span class="sxs-lookup"><span data-stu-id="27647-103">Cell element (Geometry Section) ('Visio XML')</span></span>

<span data-ttu-id="27647-104">定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="27647-104">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="27647-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="27647-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="27647-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="27647-106">**Element type**</span></span> <br/> |[<span data-ttu-id="27647-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="27647-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="27647-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="27647-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="27647-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="27647-109">**Schema file**</span></span> <br/> |<span data-ttu-id="27647-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="27647-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="27647-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="27647-111">**Document parts**</span></span> <br/> |<span data-ttu-id="27647-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="27647-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="27647-113">定义</span><span class="sxs-lookup"><span data-stu-id="27647-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="27647-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="27647-114">Elements and attributes</span></span>

<span data-ttu-id="27647-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="27647-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="27647-116">父元素</span><span class="sxs-lookup"><span data-stu-id="27647-116">Parent elements</span></span>

|<span data-ttu-id="27647-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="27647-117">**Element**</span></span>|<span data-ttu-id="27647-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="27647-118">**Type**</span></span>|<span data-ttu-id="27647-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="27647-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="27647-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="27647-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="27647-121">Geometry_Type</span><span class="sxs-lookup"><span data-stu-id="27647-121">Geometry_Type</span></span>](geometry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="27647-122">定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="27647-122">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="27647-123">子元素</span><span class="sxs-lookup"><span data-stu-id="27647-123">Child elements</span></span>

|<span data-ttu-id="27647-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="27647-124">**Element**</span></span>|<span data-ttu-id="27647-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="27647-125">**Type**</span></span>|<span data-ttu-id="27647-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="27647-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="27647-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="27647-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="27647-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="27647-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="27647-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="27647-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="27647-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="27647-130">Attributes</span></span>

|<span data-ttu-id="27647-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="27647-131">**Attribute**</span></span>|<span data-ttu-id="27647-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="27647-132">**Type**</span></span>|<span data-ttu-id="27647-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="27647-133">**Required**</span></span>|<span data-ttu-id="27647-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="27647-134">**Description**</span></span>|<span data-ttu-id="27647-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="27647-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27647-136">E</span><span class="sxs-lookup"><span data-stu-id="27647-136">E</span></span>  <br/> |<span data-ttu-id="27647-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="27647-137">xsd:string</span></span>  <br/> |<span data-ttu-id="27647-138">可选</span><span class="sxs-lookup"><span data-stu-id="27647-138">optional</span></span>  <br/> |<span data-ttu-id="27647-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="27647-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="27647-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="27647-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="27647-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="27647-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="27647-142">F</span><span class="sxs-lookup"><span data-stu-id="27647-142">F</span></span>  <br/> |<span data-ttu-id="27647-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="27647-143">xsd:string</span></span>  <br/> |<span data-ttu-id="27647-144">可选</span><span class="sxs-lookup"><span data-stu-id="27647-144">optional</span></span>  <br/> | <span data-ttu-id="27647-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="27647-145">Represents the element's formula.</span></span> <span data-ttu-id="27647-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="27647-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="27647-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="27647-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="27647-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="27647-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="27647-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="27647-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="27647-150">公式。</span><span class="sxs-lookup"><span data-stu-id="27647-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="27647-151">N</span><span class="sxs-lookup"><span data-stu-id="27647-151">N</span></span>  <br/> |<span data-ttu-id="27647-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="27647-152">xsd:string</span></span>  <br/> |<span data-ttu-id="27647-153">必需</span><span class="sxs-lookup"><span data-stu-id="27647-153">required</span></span>  <br/> |<span data-ttu-id="27647-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="27647-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="27647-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="27647-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="27647-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="27647-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="27647-157">U</span><span class="sxs-lookup"><span data-stu-id="27647-157">U</span></span>  <br/> |<span data-ttu-id="27647-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="27647-158">xsd:string</span></span>  <br/> |<span data-ttu-id="27647-159">可选</span><span class="sxs-lookup"><span data-stu-id="27647-159">optional</span></span>  <br/> |<span data-ttu-id="27647-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="27647-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="27647-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="27647-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="27647-162">V</span><span class="sxs-lookup"><span data-stu-id="27647-162">V</span></span>  <br/> |<span data-ttu-id="27647-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="27647-163">xsd:string</span></span>  <br/> |<span data-ttu-id="27647-164">可选</span><span class="sxs-lookup"><span data-stu-id="27647-164">optional</span></span>  <br/> |<span data-ttu-id="27647-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="27647-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="27647-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="27647-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="27647-167">说明</span><span class="sxs-lookup"><span data-stu-id="27647-167">Remarks</span></span>

<span data-ttu-id="27647-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="27647-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="27647-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="27647-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="27647-170">**值**</span><span class="sxs-lookup"><span data-stu-id="27647-170">**Value**</span></span>|<span data-ttu-id="27647-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="27647-171">**Description**</span></span>|<span data-ttu-id="27647-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="27647-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27647-173">NoFill</span><span class="sxs-lookup"><span data-stu-id="27647-173">NoFill</span></span>  <br/> |<span data-ttu-id="27647-174">指示是否可以填充路径。</span><span class="sxs-lookup"><span data-stu-id="27647-174">Indicates whether a path can be filled.</span></span>  <br/> |[<span data-ttu-id="27647-175">NoFill Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="27647-175">NoFill Cell (Geometry Section)</span></span>](nofill-cell-geometry-section.md) <br/> |
|<span data-ttu-id="27647-176">NoLine</span><span class="sxs-lookup"><span data-stu-id="27647-176">NoLine</span></span>  <br/> |<span data-ttu-id="27647-177">确定是否围绕路径的边界来绘制线条。</span><span class="sxs-lookup"><span data-stu-id="27647-177">Determines whether a line is drawn around the boundary of the path.</span></span>  <br/> |[<span data-ttu-id="27647-178">NoLine Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="27647-178">NoLine Cell (Geometry Section)</span></span>](noline-cell-geometry-section.md) <br/> |
|<span data-ttu-id="27647-179">NoQuickDrag</span><span class="sxs-lookup"><span data-stu-id="27647-179">NoQuickDrag</span></span>  <br/> |<span data-ttu-id="27647-180">确定形状是否可以选择或拖动当用户单击由 geometry 内容定义的填充的区域。</span><span class="sxs-lookup"><span data-stu-id="27647-180">Determines whether a shape can be selected or dragged when the user clicks the filled area defined by the Geometry section.</span></span>  <br/> |[<span data-ttu-id="27647-181">NoQuickDrag 单元格（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="27647-181">NoQuickDrag Cell (Geometry Section)</span></span>](noquickdrag-cell-geometry-section.md) <br/> |
|<span data-ttu-id="27647-182">NoShow</span><span class="sxs-lookup"><span data-stu-id="27647-182">NoShow</span></span>  <br/> |<span data-ttu-id="27647-183">指明路径是否显示在绘图页上。</span><span class="sxs-lookup"><span data-stu-id="27647-183">Indicates whether a path is displayed on the drawing page.</span></span>  <br/> |[<span data-ttu-id="27647-184">NoShow Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="27647-184">NoShow Cell (Geometry Section)</span></span>](noshow-cell-geometry-section.md) <br/> |
|<span data-ttu-id="27647-185">NoSnap</span><span class="sxs-lookup"><span data-stu-id="27647-185">NoSnap</span></span>  <br/> |<span data-ttu-id="27647-186">确定其他形状是否与路径对齐。</span><span class="sxs-lookup"><span data-stu-id="27647-186">Determines whether other shapes snap to a path.</span></span>  <br/> |[<span data-ttu-id="27647-187">NoSnap Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="27647-187">NoSnap Cell (Geometry Section)</span></span>](nosnap-cell-geometry-section.md) <br/> |
   

