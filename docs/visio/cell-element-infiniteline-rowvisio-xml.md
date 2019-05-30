---
title: Cell 元素 ("InfiniteLine" 行) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e14b8246-0064-3a54-7bd6-ad28180f9ea6
description: 包含无限长线上两个点的 x 坐标或 y 坐标。
ms.openlocfilehash: 1198e516a15e829b9a2da23491ca5f75e88a8e7d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539770"
---
# <a name="cell-element-infiniteline-row-visio-xml"></a><span data-ttu-id="b5f71-103">Cell 元素 ("InfiniteLine" 行) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b5f71-103">Cell element (InfiniteLine Row) (Visio XML)</span></span>

<span data-ttu-id="b5f71-104">包含无限长线上两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="b5f71-104">Contains the x- or y-coordinates of two points on an infinite line.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b5f71-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b5f71-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b5f71-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b5f71-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b5f71-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="b5f71-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b5f71-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b5f71-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b5f71-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b5f71-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b5f71-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="b5f71-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b5f71-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b5f71-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b5f71-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="b5f71-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b5f71-113">定义</span><span class="sxs-lookup"><span data-stu-id="b5f71-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b5f71-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b5f71-114">Elements and attributes</span></span>

<span data-ttu-id="b5f71-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b5f71-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b5f71-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b5f71-116">Parent elements</span></span>

|<span data-ttu-id="b5f71-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b5f71-117">**Element**</span></span>|<span data-ttu-id="b5f71-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b5f71-118">**Type**</span></span>|<span data-ttu-id="b5f71-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b5f71-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b5f71-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="b5f71-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="b5f71-121">InfiniteLine_Type</span><span class="sxs-lookup"><span data-stu-id="b5f71-121">InfiniteLine_Type</span></span>](infiniteline_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b5f71-122">包含无限长线上两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="b5f71-122">Contains the x- or y-coordinates of two points on an infinite line.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b5f71-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b5f71-123">Child elements</span></span>

|<span data-ttu-id="b5f71-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="b5f71-124">**Element**</span></span>|<span data-ttu-id="b5f71-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="b5f71-125">**Type**</span></span>|<span data-ttu-id="b5f71-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b5f71-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b5f71-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="b5f71-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b5f71-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="b5f71-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b5f71-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="b5f71-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b5f71-130">属性</span><span class="sxs-lookup"><span data-stu-id="b5f71-130">Attributes</span></span>

|<span data-ttu-id="b5f71-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="b5f71-131">**Attribute**</span></span>|<span data-ttu-id="b5f71-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="b5f71-132">**Type**</span></span>|<span data-ttu-id="b5f71-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="b5f71-133">**Required**</span></span>|<span data-ttu-id="b5f71-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="b5f71-134">**Description**</span></span>|<span data-ttu-id="b5f71-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b5f71-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b5f71-136">E</span><span class="sxs-lookup"><span data-stu-id="b5f71-136">E</span></span>  <br/> |<span data-ttu-id="b5f71-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b5f71-137">xsd:string</span></span>  <br/> |<span data-ttu-id="b5f71-138">可选</span><span class="sxs-lookup"><span data-stu-id="b5f71-138">optional</span></span>  <br/> |<span data-ttu-id="b5f71-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="b5f71-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="b5f71-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="b5f71-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="b5f71-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="b5f71-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="b5f71-142">F</span><span class="sxs-lookup"><span data-stu-id="b5f71-142">F</span></span>  <br/> |<span data-ttu-id="b5f71-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b5f71-143">xsd:string</span></span>  <br/> |<span data-ttu-id="b5f71-144">可选</span><span class="sxs-lookup"><span data-stu-id="b5f71-144">optional</span></span>  <br/> | <span data-ttu-id="b5f71-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="b5f71-145">Represents the element's formula.</span></span> <span data-ttu-id="b5f71-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="b5f71-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="b5f71-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="b5f71-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="b5f71-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="b5f71-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="b5f71-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="b5f71-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="b5f71-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="b5f71-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="b5f71-151">N</span><span class="sxs-lookup"><span data-stu-id="b5f71-151">N</span></span>  <br/> |<span data-ttu-id="b5f71-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b5f71-152">xsd:string</span></span>  <br/> |<span data-ttu-id="b5f71-153">必需</span><span class="sxs-lookup"><span data-stu-id="b5f71-153">required</span></span>  <br/> |<span data-ttu-id="b5f71-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="b5f71-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="b5f71-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="b5f71-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="b5f71-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="b5f71-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="b5f71-157">U</span><span class="sxs-lookup"><span data-stu-id="b5f71-157">U</span></span>  <br/> |<span data-ttu-id="b5f71-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b5f71-158">xsd:string</span></span>  <br/> |<span data-ttu-id="b5f71-159">可选</span><span class="sxs-lookup"><span data-stu-id="b5f71-159">optional</span></span>  <br/> |<span data-ttu-id="b5f71-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="b5f71-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="b5f71-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="b5f71-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="b5f71-162">部分</span><span class="sxs-lookup"><span data-stu-id="b5f71-162">V</span></span>  <br/> |<span data-ttu-id="b5f71-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b5f71-163">xsd:string</span></span>  <br/> |<span data-ttu-id="b5f71-164">可选</span><span class="sxs-lookup"><span data-stu-id="b5f71-164">optional</span></span>  <br/> |<span data-ttu-id="b5f71-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="b5f71-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="b5f71-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="b5f71-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b5f71-167">备注</span><span class="sxs-lookup"><span data-stu-id="b5f71-167">Remarks</span></span>

<span data-ttu-id="b5f71-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="b5f71-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="b5f71-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="b5f71-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="b5f71-170">**值**</span><span class="sxs-lookup"><span data-stu-id="b5f71-170">**Value**</span></span>|<span data-ttu-id="b5f71-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="b5f71-171">**Description**</span></span>|<span data-ttu-id="b5f71-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b5f71-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5f71-173">X</span><span class="sxs-lookup"><span data-stu-id="b5f71-173">X</span></span>  <br/> |<span data-ttu-id="b5f71-174">无限长线上某个点的 x 坐标；与 Y 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="b5f71-174">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the Y cell.</span></span>  <br/> |[<span data-ttu-id="b5f71-175">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b5f71-175">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="b5f71-176">Y</span><span class="sxs-lookup"><span data-stu-id="b5f71-176">Y</span></span>  <br/> |<span data-ttu-id="b5f71-177">无限长线上某个点的 y 坐标；与 X 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="b5f71-177">A y-coordinate of a point on the infinite line; paired with x-coordinate represented by the X cell.</span></span>  <br/> |[<span data-ttu-id="b5f71-178">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b5f71-178">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="b5f71-179">A</span><span class="sxs-lookup"><span data-stu-id="b5f71-179">A</span></span>  <br/> |<span data-ttu-id="b5f71-180">无限长线上某个点的 x 坐标；与 B 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="b5f71-180">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="b5f71-181">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b5f71-181">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="b5f71-182">B</span><span class="sxs-lookup"><span data-stu-id="b5f71-182">B</span></span>  <br/> |<span data-ttu-id="b5f71-183">无限长线上某个点的 y 坐标；与 A 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="b5f71-183">A y-coordinate of a point on an infinite line; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="b5f71-184">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="b5f71-184">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
   

