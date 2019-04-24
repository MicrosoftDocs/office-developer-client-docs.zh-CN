---
title: Row 元素 ("段落" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 00ecaa82-3b40-24cc-91c0-b2562e92161d
description: 显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。
ms.openlocfilehash: 304c63bf810232b5a9a0f08b9b36718dd75dcc69
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283575"
---
# <a name="row-element-paragraph-section-visio-xml"></a><span data-ttu-id="0c8d2-103">Row 元素 ("段落" 部分) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="0c8d2-103">Row element (Paragraph Section) ('Visio XML')</span></span>

<span data-ttu-id="0c8d2-104">显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-104">Shows the paragraph formatting attributes for the shape's text, such as indents, line spacing, bullets, and horizontal alignment of paragraphs.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="0c8d2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="0c8d2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0c8d2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="0c8d2-107">ParagraphRow_Type</span><span class="sxs-lookup"><span data-stu-id="0c8d2-107">ParagraphRow_Type</span></span>](paragraphrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="0c8d2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="0c8d2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="0c8d2-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="0c8d2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="0c8d2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="0c8d2-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="0c8d2-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0c8d2-113">定义</span><span class="sxs-lookup"><span data-stu-id="0c8d2-113">Definition</span></span>

```XML
< xs:element name="Row" type="ParagraphRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0c8d2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0c8d2-114">Elements and attributes</span></span>

<span data-ttu-id="0c8d2-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="0c8d2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0c8d2-116">Parent elements</span></span>

|<span data-ttu-id="0c8d2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-117">**Element**</span></span>|<span data-ttu-id="0c8d2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-118">**Type**</span></span>|<span data-ttu-id="0c8d2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0c8d2-120">Section</span><span class="sxs-lookup"><span data-stu-id="0c8d2-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c8d2-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="0c8d2-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0c8d2-122">显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-122">Shows the paragraph formatting attributes for the shape's text, such as indents, line spacing, bullets, and horizontal alignment of paragraphs.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="0c8d2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0c8d2-123">Child elements</span></span>

|<span data-ttu-id="0c8d2-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-124">**Element**</span></span>|<span data-ttu-id="0c8d2-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-125">**Type**</span></span>|<span data-ttu-id="0c8d2-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0c8d2-127">Cell</span><span class="sxs-lookup"><span data-stu-id="0c8d2-127">Cell</span></span>](cell-element-paragraph-sectionvisio-xml.md) <br/> |[<span data-ttu-id="0c8d2-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="0c8d2-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0c8d2-129">指定一个属性。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="0c8d2-130">属性</span><span class="sxs-lookup"><span data-stu-id="0c8d2-130">Attributes</span></span>

|<span data-ttu-id="0c8d2-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-131">**Attribute**</span></span>|<span data-ttu-id="0c8d2-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-132">**Type**</span></span>|<span data-ttu-id="0c8d2-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-133">**Required**</span></span>|<span data-ttu-id="0c8d2-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-134">**Description**</span></span>|<span data-ttu-id="0c8d2-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0c8d2-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c8d2-136">键</span><span class="sxs-lookup"><span data-stu-id="0c8d2-136">Del</span></span>  <br/> |<span data-ttu-id="0c8d2-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="0c8d2-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="0c8d2-138">可选</span><span class="sxs-lookup"><span data-stu-id="0c8d2-138">optional</span></span>  <br/> |<span data-ttu-id="0c8d2-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="0c8d2-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="0c8d2-141">IX</span><span class="sxs-lookup"><span data-stu-id="0c8d2-141">IX</span></span>  <br/> |<span data-ttu-id="0c8d2-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c8d2-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c8d2-143">可选</span><span class="sxs-lookup"><span data-stu-id="0c8d2-143">optional</span></span>  <br/> |<span data-ttu-id="0c8d2-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="0c8d2-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="0c8d2-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="0c8d2-147">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c8d2-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="0c8d2-148">LocalName</span></span>  <br/> |<span data-ttu-id="0c8d2-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0c8d2-149">xsd:string</span></span>  <br/> |<span data-ttu-id="0c8d2-150">可选</span><span class="sxs-lookup"><span data-stu-id="0c8d2-150">optional</span></span>  <br/> |<span data-ttu-id="0c8d2-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="0c8d2-152">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0c8d2-153">N</span><span class="sxs-lookup"><span data-stu-id="0c8d2-153">N</span></span>  <br/> |<span data-ttu-id="0c8d2-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0c8d2-154">xsd:string</span></span>  <br/> |<span data-ttu-id="0c8d2-155">可选</span><span class="sxs-lookup"><span data-stu-id="0c8d2-155">optional</span></span>  <br/> |<span data-ttu-id="0c8d2-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="0c8d2-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="0c8d2-158">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0c8d2-159">T</span><span class="sxs-lookup"><span data-stu-id="0c8d2-159">T</span></span>  <br/> |<span data-ttu-id="0c8d2-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0c8d2-160">xsd:string</span></span>  <br/> |<span data-ttu-id="0c8d2-161">可选</span><span class="sxs-lookup"><span data-stu-id="0c8d2-161">optional</span></span>  <br/> |<span data-ttu-id="0c8d2-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="0c8d2-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="0c8d2-164">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c8d2-164">Values of the xsd:string type.</span></span>  <br/> |
   

