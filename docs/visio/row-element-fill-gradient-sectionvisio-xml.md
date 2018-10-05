---
title: Row 元素 （填充渐变部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f216afb5-4393-6e1c-54c2-3c184a26d934
description: 包含颜色、 透明度和渐变填充的渐变光圈的位置。
ms.openlocfilehash: 55ec3b58f57d1fb008825c1a5a4156e5aec59552
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393773"
---
# <a name="row-element-fill-gradient-section-visio-xml"></a><span data-ttu-id="91920-103">Row 元素 （填充渐变部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="91920-103">Row element (Fill Gradient Section) ('Visio XML')</span></span>

<span data-ttu-id="91920-104">包含颜色、 透明度和渐变填充的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="91920-104">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="91920-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="91920-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="91920-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="91920-106">**Element type**</span></span> <br/> |[<span data-ttu-id="91920-107">FillGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="91920-107">FillGradientRow_Type</span></span>](fillgradientrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="91920-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="91920-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="91920-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="91920-109">**Schema file**</span></span> <br/> |<span data-ttu-id="91920-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="91920-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="91920-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="91920-111">**Document parts**</span></span> <br/> |<span data-ttu-id="91920-112">document.xml，母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="91920-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="91920-113">定义</span><span class="sxs-lookup"><span data-stu-id="91920-113">Definition</span></span>

```XML
< xs:element name="Row" type="FillGradientRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="91920-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="91920-114">Elements and attributes</span></span>

<span data-ttu-id="91920-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="91920-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="91920-116">父元素</span><span class="sxs-lookup"><span data-stu-id="91920-116">Parent elements</span></span>

|<span data-ttu-id="91920-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="91920-117">**Element**</span></span>|<span data-ttu-id="91920-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="91920-118">**Type**</span></span>|<span data-ttu-id="91920-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="91920-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="91920-120">Section</span><span class="sxs-lookup"><span data-stu-id="91920-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="91920-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="91920-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="91920-122">包含颜色、 透明度和渐变填充的渐变光圈的位置。</span><span class="sxs-lookup"><span data-stu-id="91920-122">Contains the color, transparency, and position of a gradient stop for a fill gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="91920-123">子元素</span><span class="sxs-lookup"><span data-stu-id="91920-123">Child elements</span></span>

|<span data-ttu-id="91920-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="91920-124">**Element**</span></span>|<span data-ttu-id="91920-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="91920-125">**Type**</span></span>|<span data-ttu-id="91920-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="91920-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="91920-127">Cell</span><span class="sxs-lookup"><span data-stu-id="91920-127">Cell</span></span>](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="91920-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="91920-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="91920-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="91920-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="91920-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="91920-130">Attributes</span></span>

|<span data-ttu-id="91920-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="91920-131">**Attribute**</span></span>|<span data-ttu-id="91920-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="91920-132">**Type**</span></span>|<span data-ttu-id="91920-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="91920-133">**Required**</span></span>|<span data-ttu-id="91920-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="91920-134">**Description**</span></span>|<span data-ttu-id="91920-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="91920-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91920-136">Del</span><span class="sxs-lookup"><span data-stu-id="91920-136">Del</span></span>  <br/> |<span data-ttu-id="91920-137">化</span><span class="sxs-lookup"><span data-stu-id="91920-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="91920-138">可选</span><span class="sxs-lookup"><span data-stu-id="91920-138">optional</span></span>  <br/> |<span data-ttu-id="91920-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="91920-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="91920-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="91920-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="91920-141">IX</span><span class="sxs-lookup"><span data-stu-id="91920-141">IX</span></span>  <br/> |<span data-ttu-id="91920-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="91920-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="91920-143">可选</span><span class="sxs-lookup"><span data-stu-id="91920-143">optional</span></span>  <br/> |<span data-ttu-id="91920-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="91920-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="91920-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="91920-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="91920-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="91920-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="91920-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91920-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="91920-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="91920-148">LocalName</span></span>  <br/> |<span data-ttu-id="91920-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91920-149">xsd:string</span></span>  <br/> |<span data-ttu-id="91920-150">可选</span><span class="sxs-lookup"><span data-stu-id="91920-150">optional</span></span>  <br/> |<span data-ttu-id="91920-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="91920-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="91920-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91920-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91920-153">N</span><span class="sxs-lookup"><span data-stu-id="91920-153">N</span></span>  <br/> |<span data-ttu-id="91920-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91920-154">xsd:string</span></span>  <br/> |<span data-ttu-id="91920-155">可选</span><span class="sxs-lookup"><span data-stu-id="91920-155">optional</span></span>  <br/> |<span data-ttu-id="91920-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="91920-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="91920-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="91920-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="91920-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91920-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91920-159">T</span><span class="sxs-lookup"><span data-stu-id="91920-159">T</span></span>  <br/> |<span data-ttu-id="91920-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91920-160">xsd:string</span></span>  <br/> |<span data-ttu-id="91920-161">可选</span><span class="sxs-lookup"><span data-stu-id="91920-161">optional</span></span>  <br/> |<span data-ttu-id="91920-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="91920-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="91920-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="91920-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="91920-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91920-164">Values of the xsd:string type.</span></span>  <br/> |
   

