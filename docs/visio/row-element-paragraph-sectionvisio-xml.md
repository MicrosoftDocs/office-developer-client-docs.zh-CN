---
title: Row 元素 ("段落" 部分) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 00ecaa82-3b40-24cc-91c0-b2562e92161d
description: 显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。
ms.openlocfilehash: 48d32f3a0712e2ed3110ced545d5b946f147d755
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540817"
---
# <a name="row-element-paragraph-section-visio-xml"></a><span data-ttu-id="c2e18-103">Row 元素 ("段落" 部分) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c2e18-103">Row element (Paragraph Section) (Visio XML)</span></span>

<span data-ttu-id="c2e18-104">显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。</span><span class="sxs-lookup"><span data-stu-id="c2e18-104">Shows the paragraph formatting attributes for the shape's text, such as indents, line spacing, bullets, and horizontal alignment of paragraphs.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c2e18-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c2e18-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c2e18-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c2e18-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c2e18-107">ParagraphRow_Type</span><span class="sxs-lookup"><span data-stu-id="c2e18-107">ParagraphRow_Type</span></span>](paragraphrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c2e18-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c2e18-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c2e18-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c2e18-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c2e18-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="c2e18-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c2e18-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c2e18-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c2e18-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="c2e18-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c2e18-113">定义</span><span class="sxs-lookup"><span data-stu-id="c2e18-113">Definition</span></span>

```XML
< xs:element name="Row" type="ParagraphRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c2e18-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c2e18-114">Elements and attributes</span></span>

<span data-ttu-id="c2e18-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c2e18-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c2e18-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c2e18-116">Parent elements</span></span>

|<span data-ttu-id="c2e18-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c2e18-117">**Element**</span></span>|<span data-ttu-id="c2e18-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2e18-118">**Type**</span></span>|<span data-ttu-id="c2e18-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2e18-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c2e18-120">Section</span><span class="sxs-lookup"><span data-stu-id="c2e18-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c2e18-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="c2e18-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c2e18-122">显示形状文本的段落格式属性，如段落的缩进、行间距、项目符号和水平对齐方式。</span><span class="sxs-lookup"><span data-stu-id="c2e18-122">Shows the paragraph formatting attributes for the shape's text, such as indents, line spacing, bullets, and horizontal alignment of paragraphs.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c2e18-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c2e18-123">Child elements</span></span>

|<span data-ttu-id="c2e18-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="c2e18-124">**Element**</span></span>|<span data-ttu-id="c2e18-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2e18-125">**Type**</span></span>|<span data-ttu-id="c2e18-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c2e18-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c2e18-127">Cell</span><span class="sxs-lookup"><span data-stu-id="c2e18-127">Cell</span></span>](cell-element-paragraph-sectionvisio-xml.md) <br/> |[<span data-ttu-id="c2e18-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="c2e18-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c2e18-129">指定一个属性。</span><span class="sxs-lookup"><span data-stu-id="c2e18-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c2e18-130">属性</span><span class="sxs-lookup"><span data-stu-id="c2e18-130">Attributes</span></span>

|<span data-ttu-id="c2e18-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="c2e18-131">**Attribute**</span></span>|<span data-ttu-id="c2e18-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="c2e18-132">**Type**</span></span>|<span data-ttu-id="c2e18-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="c2e18-133">**Required**</span></span>|<span data-ttu-id="c2e18-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="c2e18-134">**Description**</span></span>|<span data-ttu-id="c2e18-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c2e18-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c2e18-136">键</span><span class="sxs-lookup"><span data-stu-id="c2e18-136">Del</span></span>  <br/> |<span data-ttu-id="c2e18-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="c2e18-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c2e18-138">可选</span><span class="sxs-lookup"><span data-stu-id="c2e18-138">optional</span></span>  <br/> |<span data-ttu-id="c2e18-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="c2e18-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="c2e18-140">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2e18-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c2e18-141">IX</span><span class="sxs-lookup"><span data-stu-id="c2e18-141">IX</span></span>  <br/> |<span data-ttu-id="c2e18-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c2e18-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c2e18-143">可选</span><span class="sxs-lookup"><span data-stu-id="c2e18-143">optional</span></span>  <br/> |<span data-ttu-id="c2e18-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="c2e18-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="c2e18-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="c2e18-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="c2e18-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="c2e18-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="c2e18-147">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2e18-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c2e18-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="c2e18-148">LocalName</span></span>  <br/> |<span data-ttu-id="c2e18-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2e18-149">xsd:string</span></span>  <br/> |<span data-ttu-id="c2e18-150">可选</span><span class="sxs-lookup"><span data-stu-id="c2e18-150">optional</span></span>  <br/> |<span data-ttu-id="c2e18-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="c2e18-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="c2e18-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2e18-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c2e18-153">N</span><span class="sxs-lookup"><span data-stu-id="c2e18-153">N</span></span>  <br/> |<span data-ttu-id="c2e18-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2e18-154">xsd:string</span></span>  <br/> |<span data-ttu-id="c2e18-155">可选</span><span class="sxs-lookup"><span data-stu-id="c2e18-155">optional</span></span>  <br/> |<span data-ttu-id="c2e18-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="c2e18-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="c2e18-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="c2e18-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="c2e18-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2e18-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c2e18-159">T</span><span class="sxs-lookup"><span data-stu-id="c2e18-159">T</span></span>  <br/> |<span data-ttu-id="c2e18-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c2e18-160">xsd:string</span></span>  <br/> |<span data-ttu-id="c2e18-161">可选</span><span class="sxs-lookup"><span data-stu-id="c2e18-161">optional</span></span>  <br/> |<span data-ttu-id="c2e18-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="c2e18-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="c2e18-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="c2e18-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="c2e18-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c2e18-164">Values of the xsd:string type.</span></span>  <br/> |
   

