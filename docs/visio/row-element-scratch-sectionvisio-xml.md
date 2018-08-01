---
title: Row 元素 （草稿的部分） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bdbaf263-ae57-2807-f100-8d590ab92927
description: 用于输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: 078205b08ab40c2b88320779b1fbabc31c781eb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781161"
---
# <a name="row-element-scratch-section-visio-xml"></a><span data-ttu-id="b712a-103">Row 元素 （草稿的部分） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b712a-103">Row element (Scratch Section) ('Visio XML')</span></span>

<span data-ttu-id="b712a-104">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="b712a-104">A work area for entering and testing formulas that can be referred to by other cells.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b712a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b712a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b712a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b712a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b712a-107">ScratchRow_Type</span><span class="sxs-lookup"><span data-stu-id="b712a-107">ScratchRow_Type</span></span>](scratchrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b712a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b712a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b712a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b712a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b712a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b712a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b712a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b712a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b712a-112">document.xml、 masters.xml、 主 #.xml、 pages.xml、 页 #.xml</span><span class="sxs-lookup"><span data-stu-id="b712a-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b712a-113">定义</span><span class="sxs-lookup"><span data-stu-id="b712a-113">Definition</span></span>

```XML
< xs:element name="Row" type="ScratchRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b712a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b712a-114">Elements and attributes</span></span>

<span data-ttu-id="b712a-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b712a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b712a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b712a-116">Parent elements</span></span>

|<span data-ttu-id="b712a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b712a-117">**Element**</span></span>|<span data-ttu-id="b712a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b712a-118">**Type**</span></span>|<span data-ttu-id="b712a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b712a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b712a-120">Section</span><span class="sxs-lookup"><span data-stu-id="b712a-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b712a-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="b712a-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b712a-122">用于输入和测试可由其他单元格引用的公式的工作区。</span><span class="sxs-lookup"><span data-stu-id="b712a-122">A work area for entering and testing formulas that can be referred to by other cells.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b712a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b712a-123">Child elements</span></span>

|<span data-ttu-id="b712a-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="b712a-124">**Element**</span></span>|<span data-ttu-id="b712a-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="b712a-125">**Type**</span></span>|<span data-ttu-id="b712a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b712a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b712a-127">Cell</span><span class="sxs-lookup"><span data-stu-id="b712a-127">Cell</span></span>](cell-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="b712a-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="b712a-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b712a-129">指定单个属性。</span><span class="sxs-lookup"><span data-stu-id="b712a-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b712a-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="b712a-130">Attributes</span></span>

|<span data-ttu-id="b712a-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="b712a-131">**Attribute**</span></span>|<span data-ttu-id="b712a-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="b712a-132">**Type**</span></span>|<span data-ttu-id="b712a-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="b712a-133">**Required**</span></span>|<span data-ttu-id="b712a-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="b712a-134">**Description**</span></span>|<span data-ttu-id="b712a-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b712a-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b712a-136">Del</span><span class="sxs-lookup"><span data-stu-id="b712a-136">Del</span></span>  <br/> |<span data-ttu-id="b712a-137">化</span><span class="sxs-lookup"><span data-stu-id="b712a-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="b712a-138">可选</span><span class="sxs-lookup"><span data-stu-id="b712a-138">optional</span></span>  <br/> |<span data-ttu-id="b712a-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="b712a-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="b712a-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="b712a-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="b712a-141">IX</span><span class="sxs-lookup"><span data-stu-id="b712a-141">IX</span></span>  <br/> |<span data-ttu-id="b712a-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b712a-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b712a-143">可选</span><span class="sxs-lookup"><span data-stu-id="b712a-143">optional</span></span>  <br/> |<span data-ttu-id="b712a-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="b712a-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="b712a-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="b712a-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="b712a-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="b712a-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="b712a-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b712a-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b712a-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="b712a-148">LocalName</span></span>  <br/> |<span data-ttu-id="b712a-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b712a-149">xsd:string</span></span>  <br/> |<span data-ttu-id="b712a-150">可选</span><span class="sxs-lookup"><span data-stu-id="b712a-150">optional</span></span>  <br/> |<span data-ttu-id="b712a-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="b712a-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="b712a-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b712a-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b712a-153">N</span><span class="sxs-lookup"><span data-stu-id="b712a-153">N</span></span>  <br/> |<span data-ttu-id="b712a-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b712a-154">xsd:string</span></span>  <br/> |<span data-ttu-id="b712a-155">可选</span><span class="sxs-lookup"><span data-stu-id="b712a-155">optional</span></span>  <br/> |<span data-ttu-id="b712a-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="b712a-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="b712a-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="b712a-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="b712a-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b712a-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b712a-159">T</span><span class="sxs-lookup"><span data-stu-id="b712a-159">T</span></span>  <br/> |<span data-ttu-id="b712a-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b712a-160">xsd:string</span></span>  <br/> |<span data-ttu-id="b712a-161">可选</span><span class="sxs-lookup"><span data-stu-id="b712a-161">optional</span></span>  <br/> |<span data-ttu-id="b712a-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="b712a-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="b712a-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="b712a-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="b712a-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b712a-164">Values of the xsd:string type.</span></span>  <br/> |
   

