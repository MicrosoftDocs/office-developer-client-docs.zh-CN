---
title: Row 元素 （连接内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f44fc18-4757-7aba-8778-a474ab93a78d
description: 包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。
ms.openlocfilehash: 9f8f5f0735f7eeff2f1b2ec4562b79e6550d1716
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389916"
---
# <a name="row-element-connection-section-visio-xml"></a><span data-ttu-id="4de05-103">Row 元素 （连接内容） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4de05-103">Row element (Connection Section) ('Visio XML')</span></span>

<span data-ttu-id="4de05-104">包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。</span><span class="sxs-lookup"><span data-stu-id="4de05-104">Contains the x- or y-coordinates, horizontal and vertical direction, and type for a single connection point on a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4de05-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4de05-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4de05-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4de05-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4de05-107">ConnectionRow_Type</span><span class="sxs-lookup"><span data-stu-id="4de05-107">ConnectionRow_Type</span></span>](connectionrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4de05-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4de05-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4de05-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4de05-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4de05-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4de05-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4de05-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4de05-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4de05-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="4de05-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4de05-113">定义</span><span class="sxs-lookup"><span data-stu-id="4de05-113">Definition</span></span>

```XML
< xs:element name="Row" type="ConnectionRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4de05-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4de05-114">Elements and attributes</span></span>

<span data-ttu-id="4de05-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4de05-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4de05-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4de05-116">Parent elements</span></span>

|<span data-ttu-id="4de05-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de05-117">**Element**</span></span>|<span data-ttu-id="4de05-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de05-118">**Type**</span></span>|<span data-ttu-id="4de05-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de05-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de05-120">Section</span><span class="sxs-lookup"><span data-stu-id="4de05-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de05-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="4de05-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de05-122">包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。</span><span class="sxs-lookup"><span data-stu-id="4de05-122">Contains the x- or y-coordinates, horizontal and vertical direction, and type for a single connection point on a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4de05-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4de05-123">Child elements</span></span>

|<span data-ttu-id="4de05-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de05-124">**Element**</span></span>|<span data-ttu-id="4de05-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de05-125">**Type**</span></span>|<span data-ttu-id="4de05-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de05-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de05-127">Cell</span><span class="sxs-lookup"><span data-stu-id="4de05-127">Cell</span></span>](cell-element-connection-rowvisio-xml.md) <br/> |[<span data-ttu-id="4de05-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="4de05-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de05-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="4de05-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4de05-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="4de05-130">Attributes</span></span>

|<span data-ttu-id="4de05-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="4de05-131">**Attribute**</span></span>|<span data-ttu-id="4de05-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de05-132">**Type**</span></span>|<span data-ttu-id="4de05-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="4de05-133">**Required**</span></span>|<span data-ttu-id="4de05-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de05-134">**Description**</span></span>|<span data-ttu-id="4de05-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4de05-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4de05-136">Del</span><span class="sxs-lookup"><span data-stu-id="4de05-136">Del</span></span>  <br/> |<span data-ttu-id="4de05-137">化</span><span class="sxs-lookup"><span data-stu-id="4de05-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4de05-138">可选</span><span class="sxs-lookup"><span data-stu-id="4de05-138">optional</span></span>  <br/> |<span data-ttu-id="4de05-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="4de05-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="4de05-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de05-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4de05-141">IX</span><span class="sxs-lookup"><span data-stu-id="4de05-141">IX</span></span>  <br/> |<span data-ttu-id="4de05-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4de05-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4de05-143">可选</span><span class="sxs-lookup"><span data-stu-id="4de05-143">optional</span></span>  <br/> |<span data-ttu-id="4de05-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="4de05-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="4de05-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="4de05-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="4de05-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="4de05-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="4de05-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de05-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4de05-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="4de05-148">LocalName</span></span>  <br/> |<span data-ttu-id="4de05-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de05-149">xsd:string</span></span>  <br/> |<span data-ttu-id="4de05-150">可选</span><span class="sxs-lookup"><span data-stu-id="4de05-150">optional</span></span>  <br/> |<span data-ttu-id="4de05-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="4de05-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="4de05-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de05-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4de05-153">N</span><span class="sxs-lookup"><span data-stu-id="4de05-153">N</span></span>  <br/> |<span data-ttu-id="4de05-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de05-154">xsd:string</span></span>  <br/> |<span data-ttu-id="4de05-155">可选</span><span class="sxs-lookup"><span data-stu-id="4de05-155">optional</span></span>  <br/> |<span data-ttu-id="4de05-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="4de05-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="4de05-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="4de05-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="4de05-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de05-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4de05-159">T</span><span class="sxs-lookup"><span data-stu-id="4de05-159">T</span></span>  <br/> |<span data-ttu-id="4de05-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de05-160">xsd:string</span></span>  <br/> |<span data-ttu-id="4de05-161">可选</span><span class="sxs-lookup"><span data-stu-id="4de05-161">optional</span></span>  <br/> |<span data-ttu-id="4de05-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="4de05-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="4de05-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="4de05-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="4de05-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de05-164">Values of the xsd:string type.</span></span>  <br/> |
   
