---
title: Cell 元素 ("Geometry" 内容) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 82dcad38-d5fa-4892-91d9-1f3f25f1e600
description: 定义用于确定格式和行为属性的属性, 这些属性与构成 "Geometry" 内容的线条和弧形相关。
ms.openlocfilehash: 93cc7e204d97a813fea2db4b84c36dedf19cf5f2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539805"
---
# <a name="cell-element-geometry-section-visio-xml"></a><span data-ttu-id="408cb-103">Cell 元素 ("Geometry" 内容) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="408cb-103">Cell element (Geometry Section) (Visio XML)</span></span>

<span data-ttu-id="408cb-104">定义用于确定格式和行为属性的属性, 这些属性与构成 "Geometry" 内容的线条和弧形相关。</span><span class="sxs-lookup"><span data-stu-id="408cb-104">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="408cb-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="408cb-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="408cb-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="408cb-106">**Element type**</span></span> <br/> |[<span data-ttu-id="408cb-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="408cb-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="408cb-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="408cb-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="408cb-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="408cb-109">**Schema file**</span></span> <br/> |<span data-ttu-id="408cb-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="408cb-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="408cb-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="408cb-111">**Document parts**</span></span> <br/> |<span data-ttu-id="408cb-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="408cb-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="408cb-113">定义</span><span class="sxs-lookup"><span data-stu-id="408cb-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="408cb-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="408cb-114">Elements and attributes</span></span>

<span data-ttu-id="408cb-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="408cb-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="408cb-116">父元素</span><span class="sxs-lookup"><span data-stu-id="408cb-116">Parent elements</span></span>

|<span data-ttu-id="408cb-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="408cb-117">**Element**</span></span>|<span data-ttu-id="408cb-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="408cb-118">**Type**</span></span>|<span data-ttu-id="408cb-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="408cb-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="408cb-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="408cb-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="408cb-121">Geometry_Type</span><span class="sxs-lookup"><span data-stu-id="408cb-121">Geometry_Type</span></span>](geometry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="408cb-122">定义用于确定格式和行为属性的属性, 这些属性与构成 "Geometry" 内容的线条和弧形相关。</span><span class="sxs-lookup"><span data-stu-id="408cb-122">Defines properties that determine formatting and behavioral properties with respect to the lines and arcs that make up the Geometry Section.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="408cb-123">子元素</span><span class="sxs-lookup"><span data-stu-id="408cb-123">Child elements</span></span>

|<span data-ttu-id="408cb-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="408cb-124">**Element**</span></span>|<span data-ttu-id="408cb-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="408cb-125">**Type**</span></span>|<span data-ttu-id="408cb-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="408cb-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="408cb-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="408cb-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="408cb-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="408cb-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="408cb-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="408cb-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="408cb-130">属性</span><span class="sxs-lookup"><span data-stu-id="408cb-130">Attributes</span></span>

|<span data-ttu-id="408cb-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="408cb-131">**Attribute**</span></span>|<span data-ttu-id="408cb-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="408cb-132">**Type**</span></span>|<span data-ttu-id="408cb-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="408cb-133">**Required**</span></span>|<span data-ttu-id="408cb-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="408cb-134">**Description**</span></span>|<span data-ttu-id="408cb-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="408cb-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="408cb-136">E</span><span class="sxs-lookup"><span data-stu-id="408cb-136">E</span></span>  <br/> |<span data-ttu-id="408cb-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="408cb-137">xsd:string</span></span>  <br/> |<span data-ttu-id="408cb-138">可选</span><span class="sxs-lookup"><span data-stu-id="408cb-138">optional</span></span>  <br/> |<span data-ttu-id="408cb-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="408cb-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="408cb-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="408cb-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="408cb-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="408cb-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="408cb-142">F</span><span class="sxs-lookup"><span data-stu-id="408cb-142">F</span></span>  <br/> |<span data-ttu-id="408cb-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="408cb-143">xsd:string</span></span>  <br/> |<span data-ttu-id="408cb-144">可选</span><span class="sxs-lookup"><span data-stu-id="408cb-144">optional</span></span>  <br/> | <span data-ttu-id="408cb-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="408cb-145">Represents the element's formula.</span></span> <span data-ttu-id="408cb-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="408cb-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="408cb-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="408cb-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="408cb-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="408cb-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="408cb-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="408cb-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="408cb-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="408cb-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="408cb-151">N</span><span class="sxs-lookup"><span data-stu-id="408cb-151">N</span></span>  <br/> |<span data-ttu-id="408cb-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="408cb-152">xsd:string</span></span>  <br/> |<span data-ttu-id="408cb-153">必需</span><span class="sxs-lookup"><span data-stu-id="408cb-153">required</span></span>  <br/> |<span data-ttu-id="408cb-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="408cb-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="408cb-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="408cb-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="408cb-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="408cb-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="408cb-157">U</span><span class="sxs-lookup"><span data-stu-id="408cb-157">U</span></span>  <br/> |<span data-ttu-id="408cb-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="408cb-158">xsd:string</span></span>  <br/> |<span data-ttu-id="408cb-159">可选</span><span class="sxs-lookup"><span data-stu-id="408cb-159">optional</span></span>  <br/> |<span data-ttu-id="408cb-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="408cb-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="408cb-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="408cb-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="408cb-162">部分</span><span class="sxs-lookup"><span data-stu-id="408cb-162">V</span></span>  <br/> |<span data-ttu-id="408cb-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="408cb-163">xsd:string</span></span>  <br/> |<span data-ttu-id="408cb-164">可选</span><span class="sxs-lookup"><span data-stu-id="408cb-164">optional</span></span>  <br/> |<span data-ttu-id="408cb-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="408cb-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="408cb-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="408cb-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="408cb-167">备注</span><span class="sxs-lookup"><span data-stu-id="408cb-167">Remarks</span></span>

<span data-ttu-id="408cb-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="408cb-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="408cb-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="408cb-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="408cb-170">**值**</span><span class="sxs-lookup"><span data-stu-id="408cb-170">**Value**</span></span>|<span data-ttu-id="408cb-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="408cb-171">**Description**</span></span>|<span data-ttu-id="408cb-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="408cb-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="408cb-173">NoFill</span><span class="sxs-lookup"><span data-stu-id="408cb-173">NoFill</span></span>  <br/> |<span data-ttu-id="408cb-174">指示是否可以填充路径。</span><span class="sxs-lookup"><span data-stu-id="408cb-174">Indicates whether a path can be filled.</span></span>  <br/> |[<span data-ttu-id="408cb-175">NoFill Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="408cb-175">NoFill Cell (Geometry Section)</span></span>](nofill-cell-geometry-section.md) <br/> |
|<span data-ttu-id="408cb-176">NoLine</span><span class="sxs-lookup"><span data-stu-id="408cb-176">NoLine</span></span>  <br/> |<span data-ttu-id="408cb-177">确定是否围绕路径的边界来绘制线条。</span><span class="sxs-lookup"><span data-stu-id="408cb-177">Determines whether a line is drawn around the boundary of the path.</span></span>  <br/> |[<span data-ttu-id="408cb-178">NoLine Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="408cb-178">NoLine Cell (Geometry Section)</span></span>](noline-cell-geometry-section.md) <br/> |
|<span data-ttu-id="408cb-179">NoQuickDrag</span><span class="sxs-lookup"><span data-stu-id="408cb-179">NoQuickDrag</span></span>  <br/> |<span data-ttu-id="408cb-180">确定当用户单击由 "Geometry" 内容定义的填充区域时, 是否可以选择或拖动形状。</span><span class="sxs-lookup"><span data-stu-id="408cb-180">Determines whether a shape can be selected or dragged when the user clicks the filled area defined by the Geometry section.</span></span>  <br/> |[<span data-ttu-id="408cb-181">NoQuickDrag 单元格 ("Geometry" 内容)</span><span class="sxs-lookup"><span data-stu-id="408cb-181">NoQuickDrag Cell (Geometry Section)</span></span>](noquickdrag-cell-geometry-section.md) <br/> |
|<span data-ttu-id="408cb-182">NoShow</span><span class="sxs-lookup"><span data-stu-id="408cb-182">NoShow</span></span>  <br/> |<span data-ttu-id="408cb-183">指明路径是否显示在绘图页上。</span><span class="sxs-lookup"><span data-stu-id="408cb-183">Indicates whether a path is displayed on the drawing page.</span></span>  <br/> |[<span data-ttu-id="408cb-184">NoShow Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="408cb-184">NoShow Cell (Geometry Section)</span></span>](noshow-cell-geometry-section.md) <br/> |
|<span data-ttu-id="408cb-185">NoSnap</span><span class="sxs-lookup"><span data-stu-id="408cb-185">NoSnap</span></span>  <br/> |<span data-ttu-id="408cb-186">确定其他形状是否与路径对齐。</span><span class="sxs-lookup"><span data-stu-id="408cb-186">Determines whether other shapes snap to a path.</span></span>  <br/> |[<span data-ttu-id="408cb-187">NoSnap Cell (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="408cb-187">NoSnap Cell (Geometry Section)</span></span>](nosnap-cell-geometry-section.md) <br/> |
   

