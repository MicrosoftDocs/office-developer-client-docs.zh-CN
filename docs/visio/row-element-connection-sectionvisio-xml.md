---
title: Row 元素 （连接内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f44fc18-4757-7aba-8778-a474ab93a78d
description: 包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。
ms.openlocfilehash: d06a51e52f2b5273171d068f6fc2a6bf5227eed5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781143"
---
# <a name="row-element-connection-section-visio-xml"></a><span data-ttu-id="95686-103">Row 元素 （连接内容） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="95686-103">Row element (Connection Section) ('Visio XML')</span></span>

<span data-ttu-id="95686-104">包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。</span><span class="sxs-lookup"><span data-stu-id="95686-104">Contains the x- or y-coordinates, horizontal and vertical direction, and type for a single connection point on a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="95686-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="95686-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="95686-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="95686-106">**Element type**</span></span> <br/> |[<span data-ttu-id="95686-107">ConnectionRow_Type</span><span class="sxs-lookup"><span data-stu-id="95686-107">ConnectionRow_Type</span></span>](connectionrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="95686-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="95686-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="95686-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="95686-109">**Schema file**</span></span> <br/> |<span data-ttu-id="95686-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="95686-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="95686-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="95686-111">**Document parts**</span></span> <br/> |<span data-ttu-id="95686-112">母版页 #.xml、 页面 #.xml</span><span class="sxs-lookup"><span data-stu-id="95686-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="95686-113">定义</span><span class="sxs-lookup"><span data-stu-id="95686-113">Definition</span></span>

```XML
< xs:element name="Row" type="ConnectionRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="95686-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="95686-114">Elements and attributes</span></span>

<span data-ttu-id="95686-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="95686-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="95686-116">父元素</span><span class="sxs-lookup"><span data-stu-id="95686-116">Parent elements</span></span>

|<span data-ttu-id="95686-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="95686-117">**Element**</span></span>|<span data-ttu-id="95686-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="95686-118">**Type**</span></span>|<span data-ttu-id="95686-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="95686-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="95686-120">Section</span><span class="sxs-lookup"><span data-stu-id="95686-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="95686-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="95686-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="95686-122">包含的 x 轴或 y 坐标、 水平和垂直方向和形状上的单个连接点类型。</span><span class="sxs-lookup"><span data-stu-id="95686-122">Contains the x- or y-coordinates, horizontal and vertical direction, and type for a single connection point on a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="95686-123">子元素</span><span class="sxs-lookup"><span data-stu-id="95686-123">Child elements</span></span>

|<span data-ttu-id="95686-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="95686-124">**Element**</span></span>|<span data-ttu-id="95686-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="95686-125">**Type**</span></span>|<span data-ttu-id="95686-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="95686-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="95686-127">Cell</span><span class="sxs-lookup"><span data-stu-id="95686-127">Cell</span></span>](cell-element-connection-rowvisio-xml.md) <br/> |[<span data-ttu-id="95686-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="95686-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="95686-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="95686-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="95686-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="95686-130">Attributes</span></span>

|<span data-ttu-id="95686-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="95686-131">**Attribute**</span></span>|<span data-ttu-id="95686-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="95686-132">**Type**</span></span>|<span data-ttu-id="95686-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="95686-133">**Required**</span></span>|<span data-ttu-id="95686-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="95686-134">**Description**</span></span>|<span data-ttu-id="95686-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="95686-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95686-136">Del</span><span class="sxs-lookup"><span data-stu-id="95686-136">Del</span></span>  <br/> |<span data-ttu-id="95686-137">化</span><span class="sxs-lookup"><span data-stu-id="95686-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="95686-138">可选</span><span class="sxs-lookup"><span data-stu-id="95686-138">optional</span></span>  <br/> |<span data-ttu-id="95686-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="95686-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="95686-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="95686-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="95686-141">IX</span><span class="sxs-lookup"><span data-stu-id="95686-141">IX</span></span>  <br/> |<span data-ttu-id="95686-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="95686-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="95686-143">可选</span><span class="sxs-lookup"><span data-stu-id="95686-143">optional</span></span>  <br/> |<span data-ttu-id="95686-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="95686-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="95686-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="95686-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="95686-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="95686-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="95686-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="95686-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="95686-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="95686-148">LocalName</span></span>  <br/> |<span data-ttu-id="95686-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="95686-149">xsd:string</span></span>  <br/> |<span data-ttu-id="95686-150">可选</span><span class="sxs-lookup"><span data-stu-id="95686-150">optional</span></span>  <br/> |<span data-ttu-id="95686-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="95686-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="95686-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="95686-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="95686-153">N</span><span class="sxs-lookup"><span data-stu-id="95686-153">N</span></span>  <br/> |<span data-ttu-id="95686-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="95686-154">xsd:string</span></span>  <br/> |<span data-ttu-id="95686-155">可选</span><span class="sxs-lookup"><span data-stu-id="95686-155">optional</span></span>  <br/> |<span data-ttu-id="95686-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="95686-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="95686-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="95686-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="95686-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="95686-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="95686-159">T</span><span class="sxs-lookup"><span data-stu-id="95686-159">T</span></span>  <br/> |<span data-ttu-id="95686-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="95686-160">xsd:string</span></span>  <br/> |<span data-ttu-id="95686-161">可选</span><span class="sxs-lookup"><span data-stu-id="95686-161">optional</span></span>  <br/> |<span data-ttu-id="95686-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="95686-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="95686-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="95686-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="95686-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="95686-164">Values of the xsd:string type.</span></span>  <br/> |
   

