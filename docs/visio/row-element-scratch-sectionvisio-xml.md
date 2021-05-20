---
title: 'Row 元素 (Scratch Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bdbaf263-ae57-2807-f100-8d590ab92927
description: 用于输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: fb346785b9cb6539d970ae1bd1c44fc706bd657d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540999"
---
# <a name="row-element-scratch-section-visio-xml"></a><span data-ttu-id="0b520-103">Row 元素 (Scratch Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="0b520-103">Row element (Scratch Section) (Visio XML)</span></span>

<span data-ttu-id="0b520-104">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="0b520-104">A work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="0b520-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="0b520-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0b520-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="0b520-106">**Element type**</span></span> <br/> |[<span data-ttu-id="0b520-107">ScratchRow_Type</span><span class="sxs-lookup"><span data-stu-id="0b520-107">ScratchRow_Type</span></span>](scratchrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="0b520-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0b520-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="0b520-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0b520-109">**Schema file**</span></span> <br/> |<span data-ttu-id="0b520-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="0b520-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="0b520-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="0b520-111">**Document parts**</span></span> <br/> |<span data-ttu-id="0b520-112">document.xml、masters.xml、master#.xml、pages.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="0b520-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0b520-113">定义</span><span class="sxs-lookup"><span data-stu-id="0b520-113">Definition</span></span>

```XML
< xs:element name="Row" type="ScratchRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0b520-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0b520-114">Elements and attributes</span></span>

<span data-ttu-id="0b520-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0b520-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="0b520-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0b520-116">Parent elements</span></span>

|<span data-ttu-id="0b520-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0b520-117">**Element**</span></span>|<span data-ttu-id="0b520-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0b520-118">**Type**</span></span>|<span data-ttu-id="0b520-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0b520-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0b520-120">Section</span><span class="sxs-lookup"><span data-stu-id="0b520-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0b520-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="0b520-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0b520-122">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="0b520-122">A work area for entering and testing formulas that can be referred to by other cells.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="0b520-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0b520-123">Child elements</span></span>

|<span data-ttu-id="0b520-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="0b520-124">**Element**</span></span>|<span data-ttu-id="0b520-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="0b520-125">**Type**</span></span>|<span data-ttu-id="0b520-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="0b520-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0b520-127">Cell</span><span class="sxs-lookup"><span data-stu-id="0b520-127">Cell</span></span>](cell-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="0b520-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="0b520-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0b520-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="0b520-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="0b520-130">属性</span><span class="sxs-lookup"><span data-stu-id="0b520-130">Attributes</span></span>

|<span data-ttu-id="0b520-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="0b520-131">**Attribute**</span></span>|<span data-ttu-id="0b520-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="0b520-132">**Type**</span></span>|<span data-ttu-id="0b520-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="0b520-133">**Required**</span></span>|<span data-ttu-id="0b520-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="0b520-134">**Description**</span></span>|<span data-ttu-id="0b520-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0b520-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0b520-136">Del</span><span class="sxs-lookup"><span data-stu-id="0b520-136">Del</span></span>  <br/> |<span data-ttu-id="0b520-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="0b520-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="0b520-138">可选</span><span class="sxs-lookup"><span data-stu-id="0b520-138">optional</span></span>  <br/> |<span data-ttu-id="0b520-139">指定是否已删除从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="0b520-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="0b520-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0b520-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="0b520-141">IX</span><span class="sxs-lookup"><span data-stu-id="0b520-141">IX</span></span>  <br/> |<span data-ttu-id="0b520-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0b520-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0b520-143">可选</span><span class="sxs-lookup"><span data-stu-id="0b520-143">optional</span></span>  <br/> |<span data-ttu-id="0b520-144">指定行的从 1 开始标识符。</span><span class="sxs-lookup"><span data-stu-id="0b520-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="0b520-145">它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。</span><span class="sxs-lookup"><span data-stu-id="0b520-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="0b520-146">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="0b520-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="0b520-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0b520-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0b520-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="0b520-148">LocalName</span></span>  <br/> |<span data-ttu-id="0b520-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="0b520-149">xsd:string</span></span>  <br/> |<span data-ttu-id="0b520-150">可选</span><span class="sxs-lookup"><span data-stu-id="0b520-150">optional</span></span>  <br/> |<span data-ttu-id="0b520-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="0b520-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="0b520-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0b520-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0b520-153">N</span><span class="sxs-lookup"><span data-stu-id="0b520-153">N</span></span>  <br/> |<span data-ttu-id="0b520-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="0b520-154">xsd:string</span></span>  <br/> |<span data-ttu-id="0b520-155">可选</span><span class="sxs-lookup"><span data-stu-id="0b520-155">optional</span></span>  <br/> |<span data-ttu-id="0b520-156">指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="0b520-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="0b520-157">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="0b520-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="0b520-158">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0b520-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0b520-159">T</span><span class="sxs-lookup"><span data-stu-id="0b520-159">T</span></span>  <br/> |<span data-ttu-id="0b520-160">xsd：string</span><span class="sxs-lookup"><span data-stu-id="0b520-160">xsd:string</span></span>  <br/> |<span data-ttu-id="0b520-161">可选</span><span class="sxs-lookup"><span data-stu-id="0b520-161">optional</span></span>  <br/> |<span data-ttu-id="0b520-162">指定由行表示的几何路径类型，并用于几何可视化。</span><span class="sxs-lookup"><span data-stu-id="0b520-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="0b520-163">T 属性仅用于"Geometry"内容。</span><span class="sxs-lookup"><span data-stu-id="0b520-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="0b520-164">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0b520-164">Values of the xsd:string type.</span></span>  <br/> |
   

