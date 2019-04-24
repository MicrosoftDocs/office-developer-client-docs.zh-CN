---
title: Row 元素 ("超链接" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f87cd7a4-b9de-5fb1-20ec-90759c966bd9
description: 包含用于在形状或绘图页与其他绘图页、另一个文件或网站之间创建多个跳转的元素。
ms.openlocfilehash: 16935e463e76e0f0ee72b3fa40964551cf125cdd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358564"
---
# <a name="row-element-hyperlink-section-visio-xml"></a><span data-ttu-id="8ba88-103">Row 元素 ("超链接" 部分) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="8ba88-103">Row element (Hyperlink Section) ('Visio XML')</span></span>

<span data-ttu-id="8ba88-104">包含用于在形状或绘图页与其他绘图页、另一个文件或网站之间创建多个跳转的元素。</span><span class="sxs-lookup"><span data-stu-id="8ba88-104">Contains elements for creating multiple jumps between a shape or drawing page and another drawing page, another file, or a website.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8ba88-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8ba88-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8ba88-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8ba88-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8ba88-107">HyperlinkRow_Type</span><span class="sxs-lookup"><span data-stu-id="8ba88-107">HyperlinkRow_Type</span></span>](hyperlinkrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8ba88-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8ba88-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8ba88-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8ba88-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8ba88-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="8ba88-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8ba88-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8ba88-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8ba88-112">master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="8ba88-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8ba88-113">定义</span><span class="sxs-lookup"><span data-stu-id="8ba88-113">Definition</span></span>

```XML
< xs:element name="Row" type="HyperlinkRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8ba88-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8ba88-114">Elements and attributes</span></span>

<span data-ttu-id="8ba88-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="8ba88-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8ba88-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8ba88-116">Parent elements</span></span>

|<span data-ttu-id="8ba88-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8ba88-117">**Element**</span></span>|<span data-ttu-id="8ba88-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8ba88-118">**Type**</span></span>|<span data-ttu-id="8ba88-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ba88-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8ba88-120">Section</span><span class="sxs-lookup"><span data-stu-id="8ba88-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8ba88-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="8ba88-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8ba88-122">包含用于在形状或绘图页与其他绘图页、另一个文件或网站之间创建多个跳转的元素。</span><span class="sxs-lookup"><span data-stu-id="8ba88-122">Contains elements for creating multiple jumps between a shape or drawing page and another drawing page, another file, or a website.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8ba88-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8ba88-123">Child elements</span></span>

|<span data-ttu-id="8ba88-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="8ba88-124">**Element**</span></span>|<span data-ttu-id="8ba88-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="8ba88-125">**Type**</span></span>|<span data-ttu-id="8ba88-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ba88-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8ba88-127">Cell</span><span class="sxs-lookup"><span data-stu-id="8ba88-127">Cell</span></span>](cell-element-hyperlink-rowvisio-xml.md) <br/> |[<span data-ttu-id="8ba88-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="8ba88-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8ba88-129">包含与形状关联的单个超链接的信息</span><span class="sxs-lookup"><span data-stu-id="8ba88-129">Contains the information for a single hyperlink associated with a shape</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="8ba88-130">属性</span><span class="sxs-lookup"><span data-stu-id="8ba88-130">Attributes</span></span>

|<span data-ttu-id="8ba88-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="8ba88-131">**Attribute**</span></span>|<span data-ttu-id="8ba88-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="8ba88-132">**Type**</span></span>|<span data-ttu-id="8ba88-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="8ba88-133">**Required**</span></span>|<span data-ttu-id="8ba88-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="8ba88-134">**Description**</span></span>|<span data-ttu-id="8ba88-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8ba88-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ba88-136">键</span><span class="sxs-lookup"><span data-stu-id="8ba88-136">Del</span></span>  <br/> |<span data-ttu-id="8ba88-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="8ba88-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="8ba88-138">可选</span><span class="sxs-lookup"><span data-stu-id="8ba88-138">optional</span></span>  <br/> |<span data-ttu-id="8ba88-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="8ba88-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="8ba88-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ba88-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="8ba88-141">IX</span><span class="sxs-lookup"><span data-stu-id="8ba88-141">IX</span></span>  <br/> |<span data-ttu-id="8ba88-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8ba88-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8ba88-143">可选</span><span class="sxs-lookup"><span data-stu-id="8ba88-143">optional</span></span>  <br/> |<span data-ttu-id="8ba88-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="8ba88-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="8ba88-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="8ba88-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="8ba88-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="8ba88-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="8ba88-147">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ba88-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8ba88-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="8ba88-148">LocalName</span></span>  <br/> |<span data-ttu-id="8ba88-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8ba88-149">xsd:string</span></span>  <br/> |<span data-ttu-id="8ba88-150">可选</span><span class="sxs-lookup"><span data-stu-id="8ba88-150">optional</span></span>  <br/> |<span data-ttu-id="8ba88-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8ba88-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="8ba88-152">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ba88-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8ba88-153">N</span><span class="sxs-lookup"><span data-stu-id="8ba88-153">N</span></span>  <br/> |<span data-ttu-id="8ba88-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8ba88-154">xsd:string</span></span>  <br/> |<span data-ttu-id="8ba88-155">可选</span><span class="sxs-lookup"><span data-stu-id="8ba88-155">optional</span></span>  <br/> |<span data-ttu-id="8ba88-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="8ba88-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="8ba88-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="8ba88-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="8ba88-158">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ba88-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8ba88-159">T</span><span class="sxs-lookup"><span data-stu-id="8ba88-159">T</span></span>  <br/> |<span data-ttu-id="8ba88-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8ba88-160">xsd:string</span></span>  <br/> |<span data-ttu-id="8ba88-161">可选</span><span class="sxs-lookup"><span data-stu-id="8ba88-161">optional</span></span>  <br/> |<span data-ttu-id="8ba88-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="8ba88-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="8ba88-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="8ba88-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="8ba88-164">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ba88-164">Values of the xsd:string type.</span></span>  <br/> |
   

