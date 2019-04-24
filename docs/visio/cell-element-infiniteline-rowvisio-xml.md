---
title: Cell 元素 ("InfiniteLine" 行) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e14b8246-0064-3a54-7bd6-ad28180f9ea6
description: 包含无限长线上两个点的 x 坐标或 y 坐标。
ms.openlocfilehash: 1dde7958116824efffce6247855a959fee61e869
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348984"
---
# <a name="cell-element-infiniteline-row-visio-xml"></a><span data-ttu-id="acbee-103">Cell 元素 ("InfiniteLine" 行) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="acbee-103">Cell element (InfiniteLine Row) ('Visio XML')</span></span>

<span data-ttu-id="acbee-104">包含无限长线上两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="acbee-104">Contains the x- or y-coordinates of two points on an infinite line.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="acbee-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="acbee-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="acbee-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="acbee-106">**Element type**</span></span> <br/> |[<span data-ttu-id="acbee-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="acbee-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="acbee-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="acbee-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="acbee-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="acbee-109">**Schema file**</span></span> <br/> |<span data-ttu-id="acbee-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="acbee-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="acbee-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="acbee-111">**Document parts**</span></span> <br/> |<span data-ttu-id="acbee-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="acbee-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="acbee-113">定义</span><span class="sxs-lookup"><span data-stu-id="acbee-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="acbee-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="acbee-114">Elements and attributes</span></span>

<span data-ttu-id="acbee-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="acbee-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="acbee-116">父元素</span><span class="sxs-lookup"><span data-stu-id="acbee-116">Parent elements</span></span>

|<span data-ttu-id="acbee-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="acbee-117">**Element**</span></span>|<span data-ttu-id="acbee-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="acbee-118">**Type**</span></span>|<span data-ttu-id="acbee-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="acbee-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="acbee-120">Row 元素 ("几何")</span><span class="sxs-lookup"><span data-stu-id="acbee-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="acbee-121">InfiniteLine_Type</span><span class="sxs-lookup"><span data-stu-id="acbee-121">InfiniteLine_Type</span></span>](infiniteline_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="acbee-122">包含无限长线上两个点的 x 坐标或 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="acbee-122">Contains the x- or y-coordinates of two points on an infinite line.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="acbee-123">子元素</span><span class="sxs-lookup"><span data-stu-id="acbee-123">Child elements</span></span>

|<span data-ttu-id="acbee-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="acbee-124">**Element**</span></span>|<span data-ttu-id="acbee-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="acbee-125">**Type**</span></span>|<span data-ttu-id="acbee-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="acbee-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="acbee-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="acbee-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="acbee-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="acbee-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="acbee-129">指定对绘图页的引用。</span><span class="sxs-lookup"><span data-stu-id="acbee-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="acbee-130">属性</span><span class="sxs-lookup"><span data-stu-id="acbee-130">Attributes</span></span>

|<span data-ttu-id="acbee-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="acbee-131">**Attribute**</span></span>|<span data-ttu-id="acbee-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="acbee-132">**Type**</span></span>|<span data-ttu-id="acbee-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="acbee-133">**Required**</span></span>|<span data-ttu-id="acbee-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="acbee-134">**Description**</span></span>|<span data-ttu-id="acbee-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="acbee-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="acbee-136">E</span><span class="sxs-lookup"><span data-stu-id="acbee-136">E</span></span>  <br/> |<span data-ttu-id="acbee-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="acbee-137">xsd:string</span></span>  <br/> |<span data-ttu-id="acbee-138">可选</span><span class="sxs-lookup"><span data-stu-id="acbee-138">optional</span></span>  <br/> |<span data-ttu-id="acbee-139">指示公式的计算结果为错误。</span><span class="sxs-lookup"><span data-stu-id="acbee-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="acbee-140">**E**的值是当前值 (一条错误消息字符串);**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="acbee-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="acbee-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="acbee-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="acbee-142">F</span><span class="sxs-lookup"><span data-stu-id="acbee-142">F</span></span>  <br/> |<span data-ttu-id="acbee-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="acbee-143">xsd:string</span></span>  <br/> |<span data-ttu-id="acbee-144">可选</span><span class="sxs-lookup"><span data-stu-id="acbee-144">optional</span></span>  <br/> | <span data-ttu-id="acbee-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="acbee-145">Represents the element's formula.</span></span> <span data-ttu-id="acbee-146">此属性可以包含以下字符串之一:</span><span class="sxs-lookup"><span data-stu-id="acbee-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="acbee-147">"(某些公式)" 如果该公式在本地存在</span><span class="sxs-lookup"><span data-stu-id="acbee-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="acbee-148">`No Formula`如果公式为本地删除或被阻止</span><span class="sxs-lookup"><span data-stu-id="acbee-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="acbee-149">`Inh`如果公式是继承的。</span><span class="sxs-lookup"><span data-stu-id="acbee-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="acbee-150">一个公式。</span><span class="sxs-lookup"><span data-stu-id="acbee-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="acbee-151">N</span><span class="sxs-lookup"><span data-stu-id="acbee-151">N</span></span>  <br/> |<span data-ttu-id="acbee-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="acbee-152">xsd:string</span></span>  <br/> |<span data-ttu-id="acbee-153">必需</span><span class="sxs-lookup"><span data-stu-id="acbee-153">required</span></span>  <br/> |<span data-ttu-id="acbee-154">代表 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="acbee-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="acbee-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="acbee-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="acbee-156">请参阅下面的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="acbee-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="acbee-157">U</span><span class="sxs-lookup"><span data-stu-id="acbee-157">U</span></span>  <br/> |<span data-ttu-id="acbee-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="acbee-158">xsd:string</span></span>  <br/> |<span data-ttu-id="acbee-159">可选</span><span class="sxs-lookup"><span data-stu-id="acbee-159">optional</span></span>  <br/> |<span data-ttu-id="acbee-160">表示一个度量单位, 默认值为 DL。</span><span class="sxs-lookup"><span data-stu-id="acbee-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="acbee-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="acbee-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="acbee-162">部分</span><span class="sxs-lookup"><span data-stu-id="acbee-162">V</span></span>  <br/> |<span data-ttu-id="acbee-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="acbee-163">xsd:string</span></span>  <br/> |<span data-ttu-id="acbee-164">可选</span><span class="sxs-lookup"><span data-stu-id="acbee-164">optional</span></span>  <br/> |<span data-ttu-id="acbee-165">表示单元格的值。</span><span class="sxs-lookup"><span data-stu-id="acbee-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="acbee-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="acbee-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="acbee-167">注解</span><span class="sxs-lookup"><span data-stu-id="acbee-167">Remarks</span></span>

<span data-ttu-id="acbee-168">此**单元格**元素的**N**属性必须是与 ShapeSheet 单元格相对应的一组有限的值之一。</span><span class="sxs-lookup"><span data-stu-id="acbee-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="acbee-169">请参阅下表, 以确定此**单元格**元素允许的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="acbee-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="acbee-170">**Value**</span><span class="sxs-lookup"><span data-stu-id="acbee-170">**Value**</span></span>|<span data-ttu-id="acbee-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="acbee-171">**Description**</span></span>|<span data-ttu-id="acbee-172">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="acbee-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="acbee-173">X</span><span class="sxs-lookup"><span data-stu-id="acbee-173">X</span></span>  <br/> |<span data-ttu-id="acbee-174">无限长线上某个点的 x 坐标；与 Y 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="acbee-174">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the Y cell.</span></span>  <br/> |[<span data-ttu-id="acbee-175">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="acbee-175">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="acbee-176">Y</span><span class="sxs-lookup"><span data-stu-id="acbee-176">Y</span></span>  <br/> |<span data-ttu-id="acbee-177">无限长线上某个点的 y 坐标；与 X 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="acbee-177">A y-coordinate of a point on the infinite line; paired with x-coordinate represented by the X cell.</span></span>  <br/> |[<span data-ttu-id="acbee-178">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="acbee-178">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="acbee-179">A</span><span class="sxs-lookup"><span data-stu-id="acbee-179">A</span></span>  <br/> |<span data-ttu-id="acbee-180">无限长线上某个点的 x 坐标；与 B 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="acbee-180">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="acbee-181">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="acbee-181">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="acbee-182">B</span><span class="sxs-lookup"><span data-stu-id="acbee-182">B</span></span>  <br/> |<span data-ttu-id="acbee-183">无限长线上某个点的 y 坐标；与 A 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="acbee-183">A y-coordinate of a point on an infinite line; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="acbee-184">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="acbee-184">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
   

