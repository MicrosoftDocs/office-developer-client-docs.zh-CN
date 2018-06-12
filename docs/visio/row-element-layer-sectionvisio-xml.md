---
title: Row 元素 （层部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b884be2-3eed-0864-6a6c-877b43d9065f
description: 包含定义单个图层和页面其属性的元素。
ms.openlocfilehash: ed8368c0c7215068cbbfcdd89c1f5b56969b5a06
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781177"
---
# <a name="row-element-layer-section-visio-xml"></a><span data-ttu-id="ba48e-103">Row 元素 （层部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ba48e-103">Row element (Layer Section) ('Visio XML')</span></span>

<span data-ttu-id="ba48e-104">包含定义单个图层和页面其属性的元素。</span><span class="sxs-lookup"><span data-stu-id="ba48e-104">Contains elements that define a single layer and its properties for a page.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="ba48e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ba48e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ba48e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ba48e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ba48e-107">LayerRow_Type</span><span class="sxs-lookup"><span data-stu-id="ba48e-107">LayerRow_Type</span></span>](layerrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ba48e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ba48e-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ba48e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ba48e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ba48e-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="ba48e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ba48e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ba48e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ba48e-112">masters.xml、 pages.xml</span><span class="sxs-lookup"><span data-stu-id="ba48e-112">masters.xml, pages.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ba48e-113">定义</span><span class="sxs-lookup"><span data-stu-id="ba48e-113">Definition</span></span>

```XML
< xs:element name="Row" type="LayerRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ba48e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ba48e-114">Elements and attributes</span></span>

<span data-ttu-id="ba48e-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ba48e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ba48e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ba48e-116">Parent elements</span></span>

|<span data-ttu-id="ba48e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="ba48e-117">**Element**</span></span>|<span data-ttu-id="ba48e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ba48e-118">**Type**</span></span>|<span data-ttu-id="ba48e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba48e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ba48e-120">节</span><span class="sxs-lookup"><span data-stu-id="ba48e-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ba48e-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="ba48e-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ba48e-122">包含定义单个图层和页面其属性的元素。</span><span class="sxs-lookup"><span data-stu-id="ba48e-122">Contains elements that define a single layer and its properties for a page.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="ba48e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ba48e-123">Child elements</span></span>

|<span data-ttu-id="ba48e-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="ba48e-124">**Element**</span></span>|<span data-ttu-id="ba48e-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="ba48e-125">**Type**</span></span>|<span data-ttu-id="ba48e-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba48e-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ba48e-127">Cell</span><span class="sxs-lookup"><span data-stu-id="ba48e-127">Cell</span></span>](cell-element-layer-sectionvisio-xml.md) <br/> |[<span data-ttu-id="ba48e-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="ba48e-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ba48e-129">指定一个图层属性或页面其属性。</span><span class="sxs-lookup"><span data-stu-id="ba48e-129">Specifies one property for a layer or its properties for a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="ba48e-130">属性</span><span class="sxs-lookup"><span data-stu-id="ba48e-130">Attributes</span></span>

|<span data-ttu-id="ba48e-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="ba48e-131">**Attribute**</span></span>|<span data-ttu-id="ba48e-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="ba48e-132">**Type**</span></span>|<span data-ttu-id="ba48e-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="ba48e-133">**Required**</span></span>|<span data-ttu-id="ba48e-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba48e-134">**Description**</span></span>|<span data-ttu-id="ba48e-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ba48e-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ba48e-136">Del</span><span class="sxs-lookup"><span data-stu-id="ba48e-136">Del</span></span>  <br/> |<span data-ttu-id="ba48e-137">化</span><span class="sxs-lookup"><span data-stu-id="ba48e-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="ba48e-138">可选</span><span class="sxs-lookup"><span data-stu-id="ba48e-138">optional</span></span>  <br/> |<span data-ttu-id="ba48e-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="ba48e-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="ba48e-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba48e-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="ba48e-141">IX</span><span class="sxs-lookup"><span data-stu-id="ba48e-141">IX</span></span>  <br/> |<span data-ttu-id="ba48e-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ba48e-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ba48e-143">可选</span><span class="sxs-lookup"><span data-stu-id="ba48e-143">optional</span></span>  <br/> |<span data-ttu-id="ba48e-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="ba48e-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="ba48e-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="ba48e-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="ba48e-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="ba48e-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="ba48e-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba48e-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ba48e-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="ba48e-148">LocalName</span></span>  <br/> |<span data-ttu-id="ba48e-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ba48e-149">xsd:string</span></span>  <br/> |<span data-ttu-id="ba48e-150">可选</span><span class="sxs-lookup"><span data-stu-id="ba48e-150">optional</span></span>  <br/> |<span data-ttu-id="ba48e-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="ba48e-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="ba48e-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba48e-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ba48e-153">N</span><span class="sxs-lookup"><span data-stu-id="ba48e-153">N</span></span>  <br/> |<span data-ttu-id="ba48e-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ba48e-154">xsd:string</span></span>  <br/> |<span data-ttu-id="ba48e-155">可选</span><span class="sxs-lookup"><span data-stu-id="ba48e-155">optional</span></span>  <br/> |<span data-ttu-id="ba48e-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="ba48e-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="ba48e-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="ba48e-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="ba48e-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba48e-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ba48e-159">T</span><span class="sxs-lookup"><span data-stu-id="ba48e-159">T</span></span>  <br/> |<span data-ttu-id="ba48e-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ba48e-160">xsd:string</span></span>  <br/> |<span data-ttu-id="ba48e-161">可选</span><span class="sxs-lookup"><span data-stu-id="ba48e-161">optional</span></span>  <br/> |<span data-ttu-id="ba48e-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="ba48e-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="ba48e-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="ba48e-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="ba48e-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ba48e-164">Values of the xsd:string type.</span></span>  <br/> |
   

