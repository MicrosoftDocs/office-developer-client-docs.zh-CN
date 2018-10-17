---
title: Row 元素 （操作标记内容） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 54c3315f-770f-6995-d0d8-ab66e4fe10d9
description: 定义形状或页上的某个动作标记。
ms.openlocfilehash: 1ecdb256fbde4a667ade747c2c7216cd0d248fc2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387319"
---
# <a name="row-element-action-tag-section-visio-xml"></a><span data-ttu-id="9ca32-103">Row 元素 （操作标记内容） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9ca32-103">Row element (Action Tag Section) ('Visio XML')</span></span>

<span data-ttu-id="9ca32-104">定义形状或页上的某个动作标记。</span><span class="sxs-lookup"><span data-stu-id="9ca32-104">Defines an action tag on a shape or page.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9ca32-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9ca32-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9ca32-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9ca32-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9ca32-107">ActionTagRow_Type</span><span class="sxs-lookup"><span data-stu-id="9ca32-107">ActionTagRow_Type</span></span>](actiontagrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9ca32-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9ca32-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9ca32-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9ca32-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9ca32-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="9ca32-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9ca32-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9ca32-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9ca32-112">masters.xml、 主 #.xml、 pages.xml、 页 #.xml</span><span class="sxs-lookup"><span data-stu-id="9ca32-112">masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9ca32-113">定义</span><span class="sxs-lookup"><span data-stu-id="9ca32-113">Definition</span></span>

```XML
< xs:element name="Row" type="ActionTagRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9ca32-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9ca32-114">Elements and attributes</span></span>

<span data-ttu-id="9ca32-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9ca32-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9ca32-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9ca32-116">Parent elements</span></span>

|<span data-ttu-id="9ca32-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9ca32-117">**Element**</span></span>|<span data-ttu-id="9ca32-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9ca32-118">**Type**</span></span>|<span data-ttu-id="9ca32-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ca32-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9ca32-120">Section</span><span class="sxs-lookup"><span data-stu-id="9ca32-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9ca32-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="9ca32-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9ca32-122">定义形状或页上的某个动作标记。</span><span class="sxs-lookup"><span data-stu-id="9ca32-122">Defines an action tag on a shape or page.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9ca32-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9ca32-123">Child elements</span></span>

|<span data-ttu-id="9ca32-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="9ca32-124">**Element**</span></span>|<span data-ttu-id="9ca32-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="9ca32-125">**Type**</span></span>|<span data-ttu-id="9ca32-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ca32-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9ca32-127">Cell</span><span class="sxs-lookup"><span data-stu-id="9ca32-127">Cell</span></span>](cell-element-action-tag-sectionvisio-xml.md) <br/> |[<span data-ttu-id="9ca32-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="9ca32-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9ca32-129">定义形状或页上的某个动作标记的一个属性。</span><span class="sxs-lookup"><span data-stu-id="9ca32-129">Defines one property for an action tag on a shape or page.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="9ca32-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="9ca32-130">Attributes</span></span>

|<span data-ttu-id="9ca32-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="9ca32-131">**Attribute**</span></span>|<span data-ttu-id="9ca32-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="9ca32-132">**Type**</span></span>|<span data-ttu-id="9ca32-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="9ca32-133">**Required**</span></span>|<span data-ttu-id="9ca32-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="9ca32-134">**Description**</span></span>|<span data-ttu-id="9ca32-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9ca32-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ca32-136">Del</span><span class="sxs-lookup"><span data-stu-id="9ca32-136">Del</span></span>  <br/> |<span data-ttu-id="9ca32-137">化</span><span class="sxs-lookup"><span data-stu-id="9ca32-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="9ca32-138">可选</span><span class="sxs-lookup"><span data-stu-id="9ca32-138">optional</span></span>  <br/> |<span data-ttu-id="9ca32-139">指定是否已删除的行，否则将继承主控形状。</span><span class="sxs-lookup"><span data-stu-id="9ca32-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="9ca32-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="9ca32-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="9ca32-141">IX</span><span class="sxs-lookup"><span data-stu-id="9ca32-141">IX</span></span>  <br/> |<span data-ttu-id="9ca32-142">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9ca32-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9ca32-143">可选</span><span class="sxs-lookup"><span data-stu-id="9ca32-143">optional</span></span>  <br/> |<span data-ttu-id="9ca32-144">指定行的基于一的标识符。</span><span class="sxs-lookup"><span data-stu-id="9ca32-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="9ca32-145">该文件应该是唯一且大于同一节中的其他标识符。IX 属性只用于字符、 连接、 字段、 FillGradient、 geometry、 层、 LineGradient、 段落、 审核、 挑战和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="9ca32-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="9ca32-146">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="9ca32-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="9ca32-147">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9ca32-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9ca32-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="9ca32-148">LocalName</span></span>  <br/> |<span data-ttu-id="9ca32-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9ca32-149">xsd:string</span></span>  <br/> |<span data-ttu-id="9ca32-150">可选</span><span class="sxs-lookup"><span data-stu-id="9ca32-150">optional</span></span>  <br/> |<span data-ttu-id="9ca32-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="9ca32-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="9ca32-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9ca32-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9ca32-153">N</span><span class="sxs-lookup"><span data-stu-id="9ca32-153">N</span></span>  <br/> |<span data-ttu-id="9ca32-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9ca32-154">xsd:string</span></span>  <br/> |<span data-ttu-id="9ca32-155">可选</span><span class="sxs-lookup"><span data-stu-id="9ca32-155">optional</span></span>  <br/> |<span data-ttu-id="9ca32-156">指定行的唯一的独立于语言的名称。N 属性仅用于用户、 属性、 操作、 控件、 连接、 超链接和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="9ca32-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="9ca32-157">行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="9ca32-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="9ca32-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9ca32-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9ca32-159">T</span><span class="sxs-lookup"><span data-stu-id="9ca32-159">T</span></span>  <br/> |<span data-ttu-id="9ca32-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9ca32-160">xsd:string</span></span>  <br/> |<span data-ttu-id="9ca32-161">可选</span><span class="sxs-lookup"><span data-stu-id="9ca32-161">optional</span></span>  <br/> |<span data-ttu-id="9ca32-162">指定由行和 geometry 可视化中使用的几何路径类型。</span><span class="sxs-lookup"><span data-stu-id="9ca32-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="9ca32-163">T 属性只用于 geometry 内容。</span><span class="sxs-lookup"><span data-stu-id="9ca32-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="9ca32-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9ca32-164">Values of the xsd:string type.</span></span>  <br/> |
   
