---
title: 'Row 元素 (Character Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 764a8e77-5308-e6ce-8763-dc6e6090da9d
description: 显示形状的文本域的格式属性，如字体、颜色、文本样式、大小写、相对于基线的位置和点大小。
ms.openlocfilehash: afff4dcb809bf73da6ada25045678711ade75b6b
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541783"
---
# <a name="row-element-character-section-visio-xml"></a><span data-ttu-id="d74cc-103">Row 元素 (Character Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="d74cc-103">Row element (Character Section) (Visio XML)</span></span>

<span data-ttu-id="d74cc-104">显示形状的文本域的格式属性，如字体、颜色、文本样式、大小写、相对于基线的位置和点大小。</span><span class="sxs-lookup"><span data-stu-id="d74cc-104">Shows the formatting attributes for a text run of the shape, such as font, color, text style, case, position relative to the baseline, and point size.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d74cc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d74cc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d74cc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d74cc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d74cc-107">CharacterRow_Type</span><span class="sxs-lookup"><span data-stu-id="d74cc-107">CharacterRow_Type</span></span>](characterrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d74cc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d74cc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d74cc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d74cc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d74cc-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d74cc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d74cc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d74cc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d74cc-112">document.xml、master#.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="d74cc-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d74cc-113">定义</span><span class="sxs-lookup"><span data-stu-id="d74cc-113">Definition</span></span>

```XML
< xs:element name="Row" type="CharacterRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d74cc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-114">Elements and attributes</span></span>

<span data-ttu-id="d74cc-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d74cc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d74cc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d74cc-116">Parent elements</span></span>

|<span data-ttu-id="d74cc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d74cc-117">**Element**</span></span>|<span data-ttu-id="d74cc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d74cc-118">**Type**</span></span>|<span data-ttu-id="d74cc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d74cc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d74cc-120">Section</span><span class="sxs-lookup"><span data-stu-id="d74cc-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d74cc-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="d74cc-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d74cc-122">显示形状的文本域的格式属性，如字体、颜色、文本样式、大小写、相对于基线的位置和点大小。</span><span class="sxs-lookup"><span data-stu-id="d74cc-122">Shows the formatting attributes for a text run of the shape, such as font, color, text style, case, position relative to the baseline, and point size.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d74cc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d74cc-123">Child elements</span></span>

|<span data-ttu-id="d74cc-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d74cc-124">**Element**</span></span>|<span data-ttu-id="d74cc-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d74cc-125">**Type**</span></span>|<span data-ttu-id="d74cc-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d74cc-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d74cc-127">Cell</span><span class="sxs-lookup"><span data-stu-id="d74cc-127">Cell</span></span>](cell-element-character-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d74cc-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d74cc-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d74cc-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="d74cc-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d74cc-130">属性</span><span class="sxs-lookup"><span data-stu-id="d74cc-130">Attributes</span></span>

|<span data-ttu-id="d74cc-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="d74cc-131">**Attribute**</span></span>|<span data-ttu-id="d74cc-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="d74cc-132">**Type**</span></span>|<span data-ttu-id="d74cc-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="d74cc-133">**Required**</span></span>|<span data-ttu-id="d74cc-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="d74cc-134">**Description**</span></span>|<span data-ttu-id="d74cc-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d74cc-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d74cc-136">Del</span><span class="sxs-lookup"><span data-stu-id="d74cc-136">Del</span></span>  <br/> |<span data-ttu-id="d74cc-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="d74cc-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d74cc-138">可选</span><span class="sxs-lookup"><span data-stu-id="d74cc-138">optional</span></span>  <br/> |<span data-ttu-id="d74cc-139">指定是否已删除从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="d74cc-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="d74cc-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d74cc-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d74cc-141">IX</span><span class="sxs-lookup"><span data-stu-id="d74cc-141">IX</span></span>  <br/> |<span data-ttu-id="d74cc-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d74cc-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d74cc-143">可选</span><span class="sxs-lookup"><span data-stu-id="d74cc-143">optional</span></span>  <br/> |<span data-ttu-id="d74cc-144">指定行的从 1 开始标识符。</span><span class="sxs-lookup"><span data-stu-id="d74cc-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="d74cc-145">它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。</span><span class="sxs-lookup"><span data-stu-id="d74cc-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="d74cc-146">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="d74cc-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="d74cc-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d74cc-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d74cc-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="d74cc-148">LocalName</span></span>  <br/> |<span data-ttu-id="d74cc-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d74cc-149">xsd:string</span></span>  <br/> |<span data-ttu-id="d74cc-150">可选</span><span class="sxs-lookup"><span data-stu-id="d74cc-150">optional</span></span>  <br/> |<span data-ttu-id="d74cc-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="d74cc-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="d74cc-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d74cc-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d74cc-153">N</span><span class="sxs-lookup"><span data-stu-id="d74cc-153">N</span></span>  <br/> |<span data-ttu-id="d74cc-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d74cc-154">xsd:string</span></span>  <br/> |<span data-ttu-id="d74cc-155">可选</span><span class="sxs-lookup"><span data-stu-id="d74cc-155">optional</span></span>  <br/> |<span data-ttu-id="d74cc-156">指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="d74cc-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="d74cc-157">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="d74cc-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="d74cc-158">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d74cc-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d74cc-159">T</span><span class="sxs-lookup"><span data-stu-id="d74cc-159">T</span></span>  <br/> |<span data-ttu-id="d74cc-160">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d74cc-160">xsd:string</span></span>  <br/> |<span data-ttu-id="d74cc-161">可选</span><span class="sxs-lookup"><span data-stu-id="d74cc-161">optional</span></span>  <br/> |<span data-ttu-id="d74cc-162">指定由行表示的几何路径类型，并用于几何可视化。</span><span class="sxs-lookup"><span data-stu-id="d74cc-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="d74cc-163">T 属性仅用于"Geometry"内容。</span><span class="sxs-lookup"><span data-stu-id="d74cc-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="d74cc-164">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d74cc-164">Values of the xsd:string type.</span></span>  <br/> |
   

