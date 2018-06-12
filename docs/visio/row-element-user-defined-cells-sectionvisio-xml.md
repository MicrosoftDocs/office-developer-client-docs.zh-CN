---
title: Row 元素 （用户定义的单元格部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9fc27888-2809-aa29-4dbb-7e4f8a0c4758
description: 一个用户指定的可由其他单元格和加载项工具引用的信息。
ms.openlocfilehash: 10a0e0e5f7255274de528a34d5faa2de6137446e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781168"
---
# <a name="row-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="d7d5b-103">Row 元素 （用户定义的单元格部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d7d5b-103">Row element (User-defined Cells Section) ('Visio XML')</span></span>

<span data-ttu-id="d7d5b-104">一个用户指定的可由其他单元格和加载项工具引用的信息。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-104">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d7d5b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d7d5b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d7d5b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d7d5b-107">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="d7d5b-107">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d7d5b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d7d5b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d7d5b-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d7d5b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d7d5b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d7d5b-112">document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml</span><span class="sxs-lookup"><span data-stu-id="d7d5b-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d7d5b-113">定义</span><span class="sxs-lookup"><span data-stu-id="d7d5b-113">Definition</span></span>

```XML
< xs:element name="Row" type="UserRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d7d5b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d7d5b-114">Elements and attributes</span></span>

<span data-ttu-id="d7d5b-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d7d5b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d7d5b-116">Parent elements</span></span>

|<span data-ttu-id="d7d5b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-117">**Element**</span></span>|<span data-ttu-id="d7d5b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-118">**Type**</span></span>|<span data-ttu-id="d7d5b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d7d5b-120">节</span><span class="sxs-lookup"><span data-stu-id="d7d5b-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7d5b-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="d7d5b-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d7d5b-122">一个用户指定的可由其他单元格和加载项工具引用的信息。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-122">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d7d5b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d7d5b-123">Child elements</span></span>

|<span data-ttu-id="d7d5b-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-124">**Element**</span></span>|<span data-ttu-id="d7d5b-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-125">**Type**</span></span>|<span data-ttu-id="d7d5b-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d7d5b-127">Cell</span><span class="sxs-lookup"><span data-stu-id="d7d5b-127">Cell</span></span>](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d7d5b-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d7d5b-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d7d5b-129">用户指定的可由其他单元格和加载项工具引用的信息片段一个属性。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-129">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d7d5b-130">属性</span><span class="sxs-lookup"><span data-stu-id="d7d5b-130">Attributes</span></span>

|<span data-ttu-id="d7d5b-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-131">**Attribute**</span></span>|<span data-ttu-id="d7d5b-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-132">**Type**</span></span>|<span data-ttu-id="d7d5b-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-133">**Required**</span></span>|<span data-ttu-id="d7d5b-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-134">**Description**</span></span>|<span data-ttu-id="d7d5b-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d7d5b-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7d5b-136">Del</span><span class="sxs-lookup"><span data-stu-id="d7d5b-136">Del</span></span>  <br/> |<span data-ttu-id="d7d5b-137">化</span><span class="sxs-lookup"><span data-stu-id="d7d5b-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d7d5b-138">可选</span><span class="sxs-lookup"><span data-stu-id="d7d5b-138">optional</span></span>  <br/> |<span data-ttu-id="d7d5b-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="d7d5b-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d7d5b-141">IX</span><span class="sxs-lookup"><span data-stu-id="d7d5b-141">IX</span></span>  <br/> |<span data-ttu-id="d7d5b-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7d5b-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7d5b-143">可选</span><span class="sxs-lookup"><span data-stu-id="d7d5b-143">optional</span></span>  <br/> |<span data-ttu-id="d7d5b-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="d7d5b-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="d7d5b-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="d7d5b-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7d5b-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="d7d5b-148">LocalName</span></span>  <br/> |<span data-ttu-id="d7d5b-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d7d5b-149">xsd:string</span></span>  <br/> |<span data-ttu-id="d7d5b-150">可选</span><span class="sxs-lookup"><span data-stu-id="d7d5b-150">optional</span></span>  <br/> |<span data-ttu-id="d7d5b-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="d7d5b-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d7d5b-153">N</span><span class="sxs-lookup"><span data-stu-id="d7d5b-153">N</span></span>  <br/> |<span data-ttu-id="d7d5b-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d7d5b-154">xsd:string</span></span>  <br/> |<span data-ttu-id="d7d5b-155">可选</span><span class="sxs-lookup"><span data-stu-id="d7d5b-155">optional</span></span>  <br/> |<span data-ttu-id="d7d5b-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="d7d5b-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="d7d5b-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d7d5b-159">T</span><span class="sxs-lookup"><span data-stu-id="d7d5b-159">T</span></span>  <br/> |<span data-ttu-id="d7d5b-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d7d5b-160">xsd:string</span></span>  <br/> |<span data-ttu-id="d7d5b-161">可选</span><span class="sxs-lookup"><span data-stu-id="d7d5b-161">optional</span></span>  <br/> |<span data-ttu-id="d7d5b-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="d7d5b-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="d7d5b-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7d5b-164">Values of the xsd:string type.</span></span>  <br/> |
   

