---
title: 'Row 元素 (User-defined Cells Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9fc27888-2809-aa29-4dbb-7e4f8a0c4758
description: 用户指定的一段信息，其他单元格和加载项工具可以引用这些信息。
ms.openlocfilehash: 1573fd6ab27cc1dbec9559552ec33d9a4ad19fd2
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538170"
---
# <a name="row-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="07c41-103">Row 元素 (User-defined Cells Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="07c41-103">Row element (User-defined Cells Section) (Visio XML)</span></span>

<span data-ttu-id="07c41-104">用户指定的一段信息，其他单元格和加载项工具可以引用这些信息。</span><span class="sxs-lookup"><span data-stu-id="07c41-104">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="07c41-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="07c41-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="07c41-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="07c41-106">**Element type**</span></span> <br/> |[<span data-ttu-id="07c41-107">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="07c41-107">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="07c41-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="07c41-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="07c41-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="07c41-109">**Schema file**</span></span> <br/> |<span data-ttu-id="07c41-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="07c41-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="07c41-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="07c41-111">**Document parts**</span></span> <br/> |<span data-ttu-id="07c41-112">document.xml、masters.xml、master#.xml、pages.xml、page#.xml</span><span class="sxs-lookup"><span data-stu-id="07c41-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="07c41-113">定义</span><span class="sxs-lookup"><span data-stu-id="07c41-113">Definition</span></span>

```XML
< xs:element name="Row" type="UserRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="07c41-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="07c41-114">Elements and attributes</span></span>

<span data-ttu-id="07c41-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="07c41-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="07c41-116">父元素</span><span class="sxs-lookup"><span data-stu-id="07c41-116">Parent elements</span></span>

|<span data-ttu-id="07c41-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="07c41-117">**Element**</span></span>|<span data-ttu-id="07c41-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="07c41-118">**Type**</span></span>|<span data-ttu-id="07c41-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="07c41-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07c41-120">Section</span><span class="sxs-lookup"><span data-stu-id="07c41-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="07c41-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="07c41-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07c41-122">用户指定的一段信息，其他单元格和加载项工具可以引用这些信息。</span><span class="sxs-lookup"><span data-stu-id="07c41-122">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="07c41-123">子元素</span><span class="sxs-lookup"><span data-stu-id="07c41-123">Child elements</span></span>

|<span data-ttu-id="07c41-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="07c41-124">**Element**</span></span>|<span data-ttu-id="07c41-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="07c41-125">**Type**</span></span>|<span data-ttu-id="07c41-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="07c41-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07c41-127">Cell</span><span class="sxs-lookup"><span data-stu-id="07c41-127">Cell</span></span>](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="07c41-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="07c41-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07c41-129">用户指定的信息块的一个属性，其他单元格和加载项工具可以引用这些信息。</span><span class="sxs-lookup"><span data-stu-id="07c41-129">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="07c41-130">属性</span><span class="sxs-lookup"><span data-stu-id="07c41-130">Attributes</span></span>

|<span data-ttu-id="07c41-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="07c41-131">**Attribute**</span></span>|<span data-ttu-id="07c41-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="07c41-132">**Type**</span></span>|<span data-ttu-id="07c41-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="07c41-133">**Required**</span></span>|<span data-ttu-id="07c41-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="07c41-134">**Description**</span></span>|<span data-ttu-id="07c41-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="07c41-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07c41-136">Del</span><span class="sxs-lookup"><span data-stu-id="07c41-136">Del</span></span>  <br/> |<span data-ttu-id="07c41-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="07c41-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="07c41-138">可选</span><span class="sxs-lookup"><span data-stu-id="07c41-138">optional</span></span>  <br/> |<span data-ttu-id="07c41-139">指定是否已删除从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="07c41-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="07c41-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07c41-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="07c41-141">IX</span><span class="sxs-lookup"><span data-stu-id="07c41-141">IX</span></span>  <br/> |<span data-ttu-id="07c41-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="07c41-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="07c41-143">可选</span><span class="sxs-lookup"><span data-stu-id="07c41-143">optional</span></span>  <br/> |<span data-ttu-id="07c41-144">指定行的从 1 开始标识符。</span><span class="sxs-lookup"><span data-stu-id="07c41-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="07c41-145">它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。</span><span class="sxs-lookup"><span data-stu-id="07c41-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="07c41-146">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="07c41-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="07c41-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07c41-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="07c41-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="07c41-148">LocalName</span></span>  <br/> |<span data-ttu-id="07c41-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="07c41-149">xsd:string</span></span>  <br/> |<span data-ttu-id="07c41-150">可选</span><span class="sxs-lookup"><span data-stu-id="07c41-150">optional</span></span>  <br/> |<span data-ttu-id="07c41-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="07c41-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="07c41-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07c41-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="07c41-153">N</span><span class="sxs-lookup"><span data-stu-id="07c41-153">N</span></span>  <br/> |<span data-ttu-id="07c41-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="07c41-154">xsd:string</span></span>  <br/> |<span data-ttu-id="07c41-155">可选</span><span class="sxs-lookup"><span data-stu-id="07c41-155">optional</span></span>  <br/> |<span data-ttu-id="07c41-156">指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="07c41-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="07c41-157">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="07c41-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="07c41-158">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07c41-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="07c41-159">T</span><span class="sxs-lookup"><span data-stu-id="07c41-159">T</span></span>  <br/> |<span data-ttu-id="07c41-160">xsd：string</span><span class="sxs-lookup"><span data-stu-id="07c41-160">xsd:string</span></span>  <br/> |<span data-ttu-id="07c41-161">可选</span><span class="sxs-lookup"><span data-stu-id="07c41-161">optional</span></span>  <br/> |<span data-ttu-id="07c41-162">指定由行表示的几何路径类型，并用于几何可视化。</span><span class="sxs-lookup"><span data-stu-id="07c41-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="07c41-163">T 属性仅用于"Geometry"内容。</span><span class="sxs-lookup"><span data-stu-id="07c41-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="07c41-164">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07c41-164">Values of the xsd:string type.</span></span>  <br/> |
   

