---
title: 单元格元素 （InfiniteLine 行） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e14b8246-0064-3a54-7bd6-ad28180f9ea6
description: 包含无限长线上两个点的 x 坐标或 y。
ms.openlocfilehash: 1dde7958116824efffce6247855a959fee61e869
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392786"
---
# <a name="cell-element-infiniteline-row-visio-xml"></a><span data-ttu-id="aa498-103">单元格元素 （InfiniteLine 行） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="aa498-103">Cell element (InfiniteLine Row) ('Visio XML')</span></span>

<span data-ttu-id="aa498-104">包含无限长线上两个点的 x 坐标或 y。</span><span class="sxs-lookup"><span data-stu-id="aa498-104">Contains the x- or y-coordinates of two points on an infinite line.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="aa498-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="aa498-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="aa498-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="aa498-106">**Element type**</span></span> <br/> |[<span data-ttu-id="aa498-107">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="aa498-107">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="aa498-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="aa498-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="aa498-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="aa498-109">**Schema file**</span></span> <br/> |<span data-ttu-id="aa498-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="aa498-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="aa498-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="aa498-111">**Document parts**</span></span> <br/> |<span data-ttu-id="aa498-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="aa498-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="aa498-113">定义</span><span class="sxs-lookup"><span data-stu-id="aa498-113">Definition</span></span>

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="aa498-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="aa498-114">Elements and attributes</span></span>

<span data-ttu-id="aa498-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="aa498-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="aa498-116">父元素</span><span class="sxs-lookup"><span data-stu-id="aa498-116">Parent elements</span></span>

|<span data-ttu-id="aa498-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="aa498-117">**Element**</span></span>|<span data-ttu-id="aa498-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="aa498-118">**Type**</span></span>|<span data-ttu-id="aa498-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa498-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="aa498-120">Row 元素 （geometry)</span><span class="sxs-lookup"><span data-stu-id="aa498-120">Row element (Geometry)</span></span>](row-element-geometry-sectionvisio-xml.md) <br/> |[<span data-ttu-id="aa498-121">InfiniteLine_Type</span><span class="sxs-lookup"><span data-stu-id="aa498-121">InfiniteLine_Type</span></span>](infiniteline_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="aa498-122">包含无限长线上两个点的 x 坐标或 y。</span><span class="sxs-lookup"><span data-stu-id="aa498-122">Contains the x- or y-coordinates of two points on an infinite line.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="aa498-123">子元素</span><span class="sxs-lookup"><span data-stu-id="aa498-123">Child elements</span></span>

|<span data-ttu-id="aa498-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="aa498-124">**Element**</span></span>|<span data-ttu-id="aa498-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="aa498-125">**Type**</span></span>|<span data-ttu-id="aa498-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa498-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="aa498-127">RefBy</span><span class="sxs-lookup"><span data-stu-id="aa498-127">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="aa498-128">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="aa498-128">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="aa498-129">指定在绘图页上的引用。</span><span class="sxs-lookup"><span data-stu-id="aa498-129">Specifies a reference to a drawing page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="aa498-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="aa498-130">Attributes</span></span>

|<span data-ttu-id="aa498-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="aa498-131">**Attribute**</span></span>|<span data-ttu-id="aa498-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="aa498-132">**Type**</span></span>|<span data-ttu-id="aa498-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="aa498-133">**Required**</span></span>|<span data-ttu-id="aa498-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa498-134">**Description**</span></span>|<span data-ttu-id="aa498-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="aa498-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa498-136">E</span><span class="sxs-lookup"><span data-stu-id="aa498-136">E</span></span>  <br/> |<span data-ttu-id="aa498-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="aa498-137">xsd:string</span></span>  <br/> |<span data-ttu-id="aa498-138">可选</span><span class="sxs-lookup"><span data-stu-id="aa498-138">optional</span></span>  <br/> |<span data-ttu-id="aa498-139">指示该公式计算为错误。</span><span class="sxs-lookup"><span data-stu-id="aa498-139">Indicates that the formula evaluates to an error.</span></span> <span data-ttu-id="aa498-140">**E**的值是当前值 （错误消息字符串）;**V**属性的值是最后一个有效的值。</span><span class="sxs-lookup"><span data-stu-id="aa498-140">The value of **E** is the current value (an error message string); the value of the **V** attribute is the last valid value.</span></span>  <br/> |<span data-ttu-id="aa498-141">错误消息字符串。</span><span class="sxs-lookup"><span data-stu-id="aa498-141">An error message string.</span></span>  <br/> |
|<span data-ttu-id="aa498-142">F</span><span class="sxs-lookup"><span data-stu-id="aa498-142">F</span></span>  <br/> |<span data-ttu-id="aa498-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="aa498-143">xsd:string</span></span>  <br/> |<span data-ttu-id="aa498-144">可选</span><span class="sxs-lookup"><span data-stu-id="aa498-144">optional</span></span>  <br/> | <span data-ttu-id="aa498-145">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="aa498-145">Represents the element's formula.</span></span> <span data-ttu-id="aa498-146">此属性可以包含以下字符串之一：</span><span class="sxs-lookup"><span data-stu-id="aa498-146">This attribute can contain one of the following strings:</span></span>  <br/>  <span data-ttu-id="aa498-147">（某些公式） 如果公式本地存在</span><span class="sxs-lookup"><span data-stu-id="aa498-147">'(some formula)' if the formula exists locally</span></span>  <br/>  <span data-ttu-id="aa498-148">`No Formula`如果本地删除或阻止公式</span><span class="sxs-lookup"><span data-stu-id="aa498-148">`No Formula` if the formula is locally deleted or blocked</span></span>  <br/>  <span data-ttu-id="aa498-149">`Inh`如果继承的公式。</span><span class="sxs-lookup"><span data-stu-id="aa498-149">`Inh` if the formula is inherited.</span></span>  <br/> |<span data-ttu-id="aa498-150">公式。</span><span class="sxs-lookup"><span data-stu-id="aa498-150">A formula.</span></span>  <br/> |
|<span data-ttu-id="aa498-151">N</span><span class="sxs-lookup"><span data-stu-id="aa498-151">N</span></span>  <br/> |<span data-ttu-id="aa498-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="aa498-152">xsd:string</span></span>  <br/> |<span data-ttu-id="aa498-153">必需</span><span class="sxs-lookup"><span data-stu-id="aa498-153">required</span></span>  <br/> |<span data-ttu-id="aa498-154">表示的 ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="aa498-154">Represents the name of the ShapeSheet cell.</span></span>  <br/> |<span data-ttu-id="aa498-155">ShapeSheet 单元格的名称。</span><span class="sxs-lookup"><span data-stu-id="aa498-155">The name of the ShapeSheet cell.</span></span>  <br/> <span data-ttu-id="aa498-156">请参阅下面的备注部分。</span><span class="sxs-lookup"><span data-stu-id="aa498-156">See the Remarks section below.</span></span>  <br/> |
|<span data-ttu-id="aa498-157">U</span><span class="sxs-lookup"><span data-stu-id="aa498-157">U</span></span>  <br/> |<span data-ttu-id="aa498-158">xsd: string</span><span class="sxs-lookup"><span data-stu-id="aa498-158">xsd:string</span></span>  <br/> |<span data-ttu-id="aa498-159">可选</span><span class="sxs-lookup"><span data-stu-id="aa498-159">optional</span></span>  <br/> |<span data-ttu-id="aa498-160">代表单位默认值是度量的 DL。</span><span class="sxs-lookup"><span data-stu-id="aa498-160">Represents a unit of measure The default is DL.</span></span>  <br/> |<span data-ttu-id="aa498-161">单元格的单位。</span><span class="sxs-lookup"><span data-stu-id="aa498-161">The units of the cell.</span></span>  <br/> |
|<span data-ttu-id="aa498-162">V</span><span class="sxs-lookup"><span data-stu-id="aa498-162">V</span></span>  <br/> |<span data-ttu-id="aa498-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="aa498-163">xsd:string</span></span>  <br/> |<span data-ttu-id="aa498-164">可选</span><span class="sxs-lookup"><span data-stu-id="aa498-164">optional</span></span>  <br/> |<span data-ttu-id="aa498-165">代表单元格的值。</span><span class="sxs-lookup"><span data-stu-id="aa498-165">Represents the value of the cell.</span></span>  <br/> |<span data-ttu-id="aa498-166">ShapeSheet 单元格的值。</span><span class="sxs-lookup"><span data-stu-id="aa498-166">The value of the ShapeSheet cell.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aa498-167">说明</span><span class="sxs-lookup"><span data-stu-id="aa498-167">Remarks</span></span>

<span data-ttu-id="aa498-168">此**单元格**元素的**N**属性必须为一组有限的对应于 ShapeSheet 单元格的值之一。</span><span class="sxs-lookup"><span data-stu-id="aa498-168">The **N** attribute of this **Cell** element must be one of a limited set of values that correspond to ShapeSheet cells.</span></span> <span data-ttu-id="aa498-169">请参阅下表为确定允许此**单元格**元素的**N**属性的值。</span><span class="sxs-lookup"><span data-stu-id="aa498-169">Refer to the table below to determine the values of the **N** attribute that are permitted for this **Cell** element.</span></span> 
  
|<span data-ttu-id="aa498-170">**值**</span><span class="sxs-lookup"><span data-stu-id="aa498-170">**Value**</span></span>|<span data-ttu-id="aa498-171">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa498-171">**Description**</span></span>|<span data-ttu-id="aa498-172">**更多信息**</span><span class="sxs-lookup"><span data-stu-id="aa498-172">**More information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aa498-173">X</span><span class="sxs-lookup"><span data-stu-id="aa498-173">X</span></span>  <br/> |<span data-ttu-id="aa498-174">无限长线上某个点的 x 坐标；与 Y 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="aa498-174">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the Y cell.</span></span>  <br/> |[<span data-ttu-id="aa498-175">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="aa498-175">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="aa498-176">Y</span><span class="sxs-lookup"><span data-stu-id="aa498-176">Y</span></span>  <br/> |<span data-ttu-id="aa498-177">无限长线上某个点的 y 坐标；与 X 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="aa498-177">A y-coordinate of a point on the infinite line; paired with x-coordinate represented by the X cell.</span></span>  <br/> |[<span data-ttu-id="aa498-178">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="aa498-178">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="aa498-179">A</span><span class="sxs-lookup"><span data-stu-id="aa498-179">A</span></span>  <br/> |<span data-ttu-id="aa498-180">无限长线上某个点的 x 坐标；与 B 单元格所表示的 y 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="aa498-180">An x-coordinate of a point on the infinite line; paired with y-coordinate represented by the B cell.</span></span>  <br/> |[<span data-ttu-id="aa498-181">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="aa498-181">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
|<span data-ttu-id="aa498-182">B</span><span class="sxs-lookup"><span data-stu-id="aa498-182">B</span></span>  <br/> |<span data-ttu-id="aa498-183">无限长线上某个点的 y 坐标；与 A 单元格所表示的 x 坐标配对。</span><span class="sxs-lookup"><span data-stu-id="aa498-183">A y-coordinate of a point on an infinite line; paired with x-coordinate represented by the A cell.</span></span>  <br/> |[<span data-ttu-id="aa498-184">InfiniteLine Row (Geometry Section)</span><span class="sxs-lookup"><span data-stu-id="aa498-184">InfiniteLine Row (Geometry Section)</span></span>](infiniteline-row-geometry-section.md) <br/> |
   

