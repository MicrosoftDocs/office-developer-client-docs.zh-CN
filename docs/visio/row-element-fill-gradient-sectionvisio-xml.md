---
title: 'Row 元素 (Fill Gradient Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f216afb5-4393-6e1c-54c2-3c184a26d934
description: 包含填充渐变的渐变停点的颜色、透明度以及位置。
ms.openlocfilehash: d9f3661d91b43bca7ff809c4e41a0c1257660e66
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538618"
---
# <a name="row-element-fill-gradient-section-visio-xml"></a><span data-ttu-id="fe118-103">Row 元素 (Fill Gradient Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="fe118-103">Row element (Fill Gradient Section) (Visio XML)</span></span>

<span data-ttu-id="fe118-104">包含填充渐变的渐变停点的颜色、透明度以及位置。</span><span class="sxs-lookup"><span data-stu-id="fe118-104">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fe118-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fe118-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fe118-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fe118-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fe118-107">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="fe118-107">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fe118-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fe118-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fe118-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fe118-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fe118-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="fe118-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fe118-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fe118-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fe118-112">document.xml、master#.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="fe118-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fe118-113">定义</span><span class="sxs-lookup"><span data-stu-id="fe118-113">Definition</span></span>

```XML
< xs:element name="Row" type="FillGradientRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fe118-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fe118-114">Elements and attributes</span></span>

<span data-ttu-id="fe118-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fe118-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fe118-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fe118-116">Parent elements</span></span>

|<span data-ttu-id="fe118-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe118-117">**Element**</span></span>|<span data-ttu-id="fe118-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe118-118">**Type**</span></span>|<span data-ttu-id="fe118-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe118-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fe118-120">Section</span><span class="sxs-lookup"><span data-stu-id="fe118-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe118-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="fe118-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe118-122">包含填充渐变的渐变停点的颜色、透明度以及位置。</span><span class="sxs-lookup"><span data-stu-id="fe118-122">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fe118-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fe118-123">Child elements</span></span>

|<span data-ttu-id="fe118-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe118-124">**Element**</span></span>|<span data-ttu-id="fe118-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe118-125">**Type**</span></span>|<span data-ttu-id="fe118-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe118-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fe118-127">Cell</span><span class="sxs-lookup"><span data-stu-id="fe118-127">Cell</span></span>](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="fe118-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="fe118-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe118-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="fe118-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="fe118-130">属性</span><span class="sxs-lookup"><span data-stu-id="fe118-130">Attributes</span></span>

|<span data-ttu-id="fe118-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="fe118-131">**Attribute**</span></span>|<span data-ttu-id="fe118-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe118-132">**Type**</span></span>|<span data-ttu-id="fe118-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="fe118-133">**Required**</span></span>|<span data-ttu-id="fe118-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="fe118-134">**Description**</span></span>|<span data-ttu-id="fe118-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fe118-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe118-136">Del</span><span class="sxs-lookup"><span data-stu-id="fe118-136">Del</span></span>  <br/> |<span data-ttu-id="fe118-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="fe118-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="fe118-138">可选</span><span class="sxs-lookup"><span data-stu-id="fe118-138">optional</span></span>  <br/> |<span data-ttu-id="fe118-139">指定是否已删除从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="fe118-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="fe118-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe118-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="fe118-141">IX</span><span class="sxs-lookup"><span data-stu-id="fe118-141">IX</span></span>  <br/> |<span data-ttu-id="fe118-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="fe118-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="fe118-143">可选</span><span class="sxs-lookup"><span data-stu-id="fe118-143">optional</span></span>  <br/> |<span data-ttu-id="fe118-144">指定行的从 1 开始标识符。</span><span class="sxs-lookup"><span data-stu-id="fe118-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="fe118-145">它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。</span><span class="sxs-lookup"><span data-stu-id="fe118-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="fe118-146">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="fe118-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="fe118-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe118-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="fe118-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="fe118-148">LocalName</span></span>  <br/> |<span data-ttu-id="fe118-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fe118-149">xsd:string</span></span>  <br/> |<span data-ttu-id="fe118-150">可选</span><span class="sxs-lookup"><span data-stu-id="fe118-150">optional</span></span>  <br/> |<span data-ttu-id="fe118-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="fe118-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="fe118-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe118-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fe118-153">N</span><span class="sxs-lookup"><span data-stu-id="fe118-153">N</span></span>  <br/> |<span data-ttu-id="fe118-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fe118-154">xsd:string</span></span>  <br/> |<span data-ttu-id="fe118-155">可选</span><span class="sxs-lookup"><span data-stu-id="fe118-155">optional</span></span>  <br/> |<span data-ttu-id="fe118-156">指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="fe118-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="fe118-157">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="fe118-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="fe118-158">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe118-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fe118-159">T</span><span class="sxs-lookup"><span data-stu-id="fe118-159">T</span></span>  <br/> |<span data-ttu-id="fe118-160">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fe118-160">xsd:string</span></span>  <br/> |<span data-ttu-id="fe118-161">可选</span><span class="sxs-lookup"><span data-stu-id="fe118-161">optional</span></span>  <br/> |<span data-ttu-id="fe118-162">指定由行表示的几何路径类型，并用于几何可视化。</span><span class="sxs-lookup"><span data-stu-id="fe118-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="fe118-163">T 属性仅用于"Geometry"内容。</span><span class="sxs-lookup"><span data-stu-id="fe118-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="fe118-164">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fe118-164">Values of the xsd:string type.</span></span>  <br/> |
   

