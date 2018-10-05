---
title: Row 元素 （层部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b884be2-3eed-0864-6a6c-877b43d9065f
description: 包含定义单个图层和页面其属性的元素。
ms.openlocfilehash: 2aff1666f5a2cb87ed10b76e0facdb19a4278c89
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396839"
---
# <a name="row-element-layer-section-visio-xml"></a><span data-ttu-id="5bf74-103">Row 元素 （层部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5bf74-103">Row element (Layer Section) ('Visio XML')</span></span>

<span data-ttu-id="5bf74-104">包含定义单个图层和页面其属性的元素。</span><span class="sxs-lookup"><span data-stu-id="5bf74-104">Contains elements that define a single layer and its properties for a page.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5bf74-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5bf74-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5bf74-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5bf74-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5bf74-107">LayerRow_Type</span><span class="sxs-lookup"><span data-stu-id="5bf74-107">LayerRow_Type</span></span>](layerrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5bf74-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5bf74-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5bf74-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5bf74-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5bf74-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5bf74-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5bf74-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5bf74-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5bf74-112">masters.xml、 pages.xml</span><span class="sxs-lookup"><span data-stu-id="5bf74-112">masters.xml, pages.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5bf74-113">定义</span><span class="sxs-lookup"><span data-stu-id="5bf74-113">Definition</span></span>

```XML
< xs:element name="Row" type="LayerRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5bf74-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5bf74-114">Elements and attributes</span></span>

<span data-ttu-id="5bf74-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5bf74-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5bf74-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5bf74-116">Parent elements</span></span>

|<span data-ttu-id="5bf74-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5bf74-117">**Element**</span></span>|<span data-ttu-id="5bf74-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5bf74-118">**Type**</span></span>|<span data-ttu-id="5bf74-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bf74-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5bf74-120">Section</span><span class="sxs-lookup"><span data-stu-id="5bf74-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5bf74-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="5bf74-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5bf74-122">包含定义单个图层和页面其属性的元素。</span><span class="sxs-lookup"><span data-stu-id="5bf74-122">Contains elements that define a single layer and its properties for a page.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5bf74-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5bf74-123">Child elements</span></span>

|<span data-ttu-id="5bf74-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="5bf74-124">**Element**</span></span>|<span data-ttu-id="5bf74-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="5bf74-125">**Type**</span></span>|<span data-ttu-id="5bf74-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bf74-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5bf74-127">Cell</span><span class="sxs-lookup"><span data-stu-id="5bf74-127">Cell</span></span>](cell-element-layer-sectionvisio-xml.md) <br/> |[<span data-ttu-id="5bf74-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="5bf74-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5bf74-129">指定一个图层属性或页面其属性。</span><span class="sxs-lookup"><span data-stu-id="5bf74-129">Specifies one property for a layer or its properties for a page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="5bf74-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="5bf74-130">Attributes</span></span>

|<span data-ttu-id="5bf74-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="5bf74-131">**Attribute**</span></span>|<span data-ttu-id="5bf74-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="5bf74-132">**Type**</span></span>|<span data-ttu-id="5bf74-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="5bf74-133">**Required**</span></span>|<span data-ttu-id="5bf74-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bf74-134">**Description**</span></span>|<span data-ttu-id="5bf74-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5bf74-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5bf74-136">Del</span><span class="sxs-lookup"><span data-stu-id="5bf74-136">Del</span></span>  <br/> |<span data-ttu-id="5bf74-137">化</span><span class="sxs-lookup"><span data-stu-id="5bf74-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="5bf74-138">可选</span><span class="sxs-lookup"><span data-stu-id="5bf74-138">optional</span></span>  <br/> |<span data-ttu-id="5bf74-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="5bf74-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="5bf74-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="5bf74-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="5bf74-141">IX</span><span class="sxs-lookup"><span data-stu-id="5bf74-141">IX</span></span>  <br/> |<span data-ttu-id="5bf74-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5bf74-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5bf74-143">可选</span><span class="sxs-lookup"><span data-stu-id="5bf74-143">optional</span></span>  <br/> |<span data-ttu-id="5bf74-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="5bf74-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="5bf74-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="5bf74-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="5bf74-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="5bf74-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="5bf74-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5bf74-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5bf74-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="5bf74-148">LocalName</span></span>  <br/> |<span data-ttu-id="5bf74-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5bf74-149">xsd:string</span></span>  <br/> |<span data-ttu-id="5bf74-150">可选</span><span class="sxs-lookup"><span data-stu-id="5bf74-150">optional</span></span>  <br/> |<span data-ttu-id="5bf74-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="5bf74-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="5bf74-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5bf74-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5bf74-153">N</span><span class="sxs-lookup"><span data-stu-id="5bf74-153">N</span></span>  <br/> |<span data-ttu-id="5bf74-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5bf74-154">xsd:string</span></span>  <br/> |<span data-ttu-id="5bf74-155">可选</span><span class="sxs-lookup"><span data-stu-id="5bf74-155">optional</span></span>  <br/> |<span data-ttu-id="5bf74-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="5bf74-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="5bf74-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="5bf74-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="5bf74-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5bf74-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="5bf74-159">T</span><span class="sxs-lookup"><span data-stu-id="5bf74-159">T</span></span>  <br/> |<span data-ttu-id="5bf74-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5bf74-160">xsd:string</span></span>  <br/> |<span data-ttu-id="5bf74-161">可选</span><span class="sxs-lookup"><span data-stu-id="5bf74-161">optional</span></span>  <br/> |<span data-ttu-id="5bf74-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="5bf74-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="5bf74-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="5bf74-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="5bf74-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5bf74-164">Values of the xsd:string type.</span></span>  <br/> |
   

