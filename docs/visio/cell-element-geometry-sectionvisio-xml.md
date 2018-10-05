---
title: 单元格 （geometry 内容） (Visio XML) 元素
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 82dcad38-d5fa-4892-91d9-1f3f25f1e600
description: 定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。
ms.openlocfilehash: ebfdb4dc7809f8883143fdda39f873a36f7bf896
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389307"
---
# <a name="cell-element-geometry-section-visio-xml"></a><span data-ttu-id="8e66d-103">单元格 （geometry 内容） (Visio XML) 元素</span><span class="sxs-lookup"><span data-stu-id="8e66d-103">Cell element (Geometry Section) ('Visio XML')</span></span>

<span data-ttu-id="8e66d-104">定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="8e66d-104">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8e66d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8e66d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8e66d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8e66d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8e66d-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="8e66d-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8e66d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8e66d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8e66d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8e66d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8e66d-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="8e66d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8e66d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8e66d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8e66d-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="8e66d-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8e66d-113">定义</span><span class="sxs-lookup"><span data-stu-id="8e66d-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8e66d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8e66d-114">Elements and attributes</span></span>

<span data-ttu-id="8e66d-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8e66d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8e66d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8e66d-116">Parent elements</span></span>

|<span data-ttu-id="8e66d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8e66d-117">**Element**</span></span>|<span data-ttu-id="8e66d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8e66d-118">**Type**</span></span>|<span data-ttu-id="8e66d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e66d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8e66d-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="8e66d-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="8e66d-121">Geometry_Type</span><span class="sxs-lookup"><span data-stu-id="8e66d-121">Geometry_Type</span></span>](geometry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8e66d-122">定义用于确定行和弧组成 geometry 内容的格式和行为的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="8e66d-122">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8e66d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8e66d-123">Child elements</span></span>

|<span data-ttu-id="8e66d-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="8e66d-124">**Element**</span></span>|<span data-ttu-id="8e66d-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="8e66d-125">**Type**</span></span>|<span data-ttu-id="8e66d-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e66d-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8e66d-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="8e66d-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8e66d-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="8e66d-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8e66d-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="8e66d-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="8e66d-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="8e66d-130">Attributes</span></span>

|<span data-ttu-id="8e66d-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="8e66d-131">**Attribute**</span></span>|<span data-ttu-id="8e66d-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="8e66d-132">**Type**</span></span>|<span data-ttu-id="8e66d-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="8e66d-133">**Required**</span></span>|<span data-ttu-id="8e66d-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e66d-134">**Description**</span></span>|<span data-ttu-id="8e66d-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8e66d-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e66d-136">E</span><span class="sxs-lookup"><span data-stu-id="8e66d-136">E</span></span>  <br/> |<span data-ttu-id="8e66d-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8e66d-137">xsd:string</span></span>  <br/> |<span data-ttu-id="8e66d-138">可选</span><span class="sxs-lookup"><span data-stu-id="8e66d-138">optional</span></span>  <br/> |<span data-ttu-id="8e66d-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="8e66d-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="8e66d-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="8e66d-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="8e66d-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="8e66d-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="8e66d-142">F</span><span class="sxs-lookup"><span data-stu-id="8e66d-142">F</span></span>  <br/> |<span data-ttu-id="8e66d-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8e66d-143">xsd:string</span></span>  <br/> |<span data-ttu-id="8e66d-144">可选</span><span class="sxs-lookup"><span data-stu-id="8e66d-144">optional</span></span>  <br/> | <span data-ttu-id="8e66d-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="8e66d-145">Represents the element's formula.</span></span> <span data-ttu-id="8e66d-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="8e66d-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="8e66d-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="8e66d-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="8e66d-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="8e66d-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="8e66d-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="8e66d-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="8e66d-150">公式。</span><span class="sxs-lookup"><span data-stu-id="8e66d-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="8e66d-151">N</span><span class="sxs-lookup"><span data-stu-id="8e66d-151">N</span></span>  <br/> |<span data-ttu-id="8e66d-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8e66d-152">xsd:string</span></span>  <br/> |<span data-ttu-id="8e66d-153">必需</span><span class="sxs-lookup"><span data-stu-id="8e66d-153">required</span></span>  <br/> |<span data-ttu-id="8e66d-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="8e66d-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="8e66d-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="8e66d-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="8e66d-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="8e66d-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="8e66d-157">U</span><span class="sxs-lookup"><span data-stu-id="8e66d-157">U</span></span>  <br/> |<span data-ttu-id="8e66d-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8e66d-158">xsd:string</span></span>  <br/> |<span data-ttu-id="8e66d-159">可选</span><span class="sxs-lookup"><span data-stu-id="8e66d-159">optional</span></span>  <br/> |<span data-ttu-id="8e66d-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="8e66d-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="8e66d-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="8e66d-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="8e66d-162">V</span><span class="sxs-lookup"><span data-stu-id="8e66d-162">V</span></span>  <br/> |<span data-ttu-id="8e66d-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8e66d-163">xsd:string</span></span>  <br/> |<span data-ttu-id="8e66d-164">可选</span><span class="sxs-lookup"><span data-stu-id="8e66d-164">optional</span></span>  <br/> |<span data-ttu-id="8e66d-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="8e66d-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="8e66d-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="8e66d-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8e66d-167">说明</span><span class="sxs-lookup"><span data-stu-id="8e66d-167">Remarks</span></span>

<span data-ttu-id="8e66d-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="8e66d-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="8e66d-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8e66d-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="8e66d-170">**值**</span><span class="sxs-lookup"><span data-stu-id="8e66d-170">**Value**</span></span>|<span data-ttu-id="8e66d-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e66d-171">**Description**</span></span>|<span data-ttu-id="8e66d-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="8e66d-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e66d-173">NoFill</span><span class="sxs-lookup"><span data-stu-id="8e66d-173">NoFill</span></span>  <br/> |<span data-ttu-id="8e66d-174">指示是否可以填充路径。</span><span class="sxs-lookup"><span data-stu-id="8e66d-174">Indicates whether a path can be filled.</span></span>  <br/> |[<span data-ttu-id="8e66d-175">NoFill Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="8e66d-175">NoFill Cell (Geometry Section)</span></span>](nofill-cell-geometry-section.md) <br/> |
|<span data-ttu-id="8e66d-176">NoLine</span><span class="sxs-lookup"><span data-stu-id="8e66d-176">NoLine</span></span>  <br/> |<span data-ttu-id="8e66d-177">确定是否围绕路径的边界来绘制线条。</span><span class="sxs-lookup"><span data-stu-id="8e66d-177">Determines whether a line is drawn around the boundary of the path.</span></span>  <br/> |[<span data-ttu-id="8e66d-178">NoLine Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="8e66d-178">NoLine Cell (Geometry Section)</span></span>](noline-cell-geometry-section.md) <br/> |
|<span data-ttu-id="8e66d-179">NoQuickDrag</span><span class="sxs-lookup"><span data-stu-id="8e66d-179">NoQuickDrag</span></span>  <br/> |<span data-ttu-id="8e66d-180">确定形状是否可以选择或拖动当用户单击由 geometry 内容定义的填充的区域。</span><span class="sxs-lookup"><span data-stu-id="8e66d-180">Determines whether a shape can be selected or dragged when the user clicks the filled area defined by the Geometry section.</span></span>  <br/> |[<span data-ttu-id="8e66d-181">NoQuickDrag 单元格（“Geometry”部分）</span><span class="sxs-lookup"><span data-stu-id="8e66d-181">NoQuickDrag Cell (Geometry Section)</span></span>](noquickdrag-cell-geometry-section.md) <br/> |
|<span data-ttu-id="8e66d-182">NoShow</span><span class="sxs-lookup"><span data-stu-id="8e66d-182">NoShow</span></span>  <br/> |<span data-ttu-id="8e66d-183">指明路径是否显示在绘图页上。</span><span class="sxs-lookup"><span data-stu-id="8e66d-183">Indicates whether a path is displayed on the drawing page.</span></span>  <br/> |[<span data-ttu-id="8e66d-184">NoShow Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="8e66d-184">NoShow Cell (Geometry Section)</span></span>](noshow-cell-geometry-section.md) <br/> |
|<span data-ttu-id="8e66d-185">NoSnap</span><span class="sxs-lookup"><span data-stu-id="8e66d-185">NoSnap</span></span>  <br/> |<span data-ttu-id="8e66d-186">确定其他形状是否与路径对齐。</span><span class="sxs-lookup"><span data-stu-id="8e66d-186">Determines whether other shapes snap to a path.</span></span>  <br/> |[<span data-ttu-id="8e66d-187">NoSnap Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="8e66d-187">NoSnap Cell (Geometry Section)</span></span>](nosnap-cell-geometry-section.md) <br/> |
   

