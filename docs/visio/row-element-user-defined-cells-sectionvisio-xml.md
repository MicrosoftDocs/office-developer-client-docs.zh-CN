---
title: Row 元素 ("用户定义的单元格" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9fc27888-2809-aa29-4dbb-7e4f8a0c4758
description: 用户指定的一段信息, 可由其他单元格和附加工具引用。
ms.openlocfilehash: 8852c1db31e9a9b8f0860c111da32de6d44dc7f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332485"
---
# <a name="row-element-user-defined-cells-section-visio-xml"></a><span data-ttu-id="8b548-103">Row 元素 ("用户定义的单元格" 部分) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="8b548-103">Row element (User-defined Cells Section) ('Visio XML')</span></span>

<span data-ttu-id="8b548-104">用户指定的一段信息, 可由其他单元格和附加工具引用。</span><span class="sxs-lookup"><span data-stu-id="8b548-104">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8b548-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8b548-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8b548-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8b548-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8b548-107">UserRow_Type</span><span class="sxs-lookup"><span data-stu-id="8b548-107">UserRow_Type</span></span>](userrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8b548-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8b548-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8b548-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8b548-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8b548-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="8b548-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8b548-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8b548-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8b548-112">document .xml、.master、master # .xml、pages、.xml 和第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="8b548-112">document.xml, masters.xml, master#.xml, pages.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8b548-113">定义</span><span class="sxs-lookup"><span data-stu-id="8b548-113">Definition</span></span>

```XML
< xs:element name="Row" type="UserRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8b548-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8b548-114">Elements and attributes</span></span>

<span data-ttu-id="8b548-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="8b548-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8b548-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8b548-116">Parent elements</span></span>

|<span data-ttu-id="8b548-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8b548-117">**Element**</span></span>|<span data-ttu-id="8b548-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b548-118">**Type**</span></span>|<span data-ttu-id="8b548-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b548-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8b548-120">Section</span><span class="sxs-lookup"><span data-stu-id="8b548-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8b548-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="8b548-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8b548-122">用户指定的一段信息, 可由其他单元格和附加工具引用。</span><span class="sxs-lookup"><span data-stu-id="8b548-122">A user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8b548-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8b548-123">Child elements</span></span>

|<span data-ttu-id="8b548-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="8b548-124">**Element**</span></span>|<span data-ttu-id="8b548-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b548-125">**Type**</span></span>|<span data-ttu-id="8b548-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b548-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8b548-127">Cell</span><span class="sxs-lookup"><span data-stu-id="8b548-127">Cell</span></span>](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="8b548-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="8b548-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8b548-129">用户指定的信息部分的一个属性, 可由其他单元格和附加工具引用。</span><span class="sxs-lookup"><span data-stu-id="8b548-129">One property of a user-specified piece of information that can be referred to by other cells and add-on tools.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="8b548-130">属性</span><span class="sxs-lookup"><span data-stu-id="8b548-130">Attributes</span></span>

|<span data-ttu-id="8b548-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="8b548-131">**Attribute**</span></span>|<span data-ttu-id="8b548-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b548-132">**Type**</span></span>|<span data-ttu-id="8b548-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="8b548-133">**Required**</span></span>|<span data-ttu-id="8b548-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="8b548-134">**Description**</span></span>|<span data-ttu-id="8b548-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8b548-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b548-136">键</span><span class="sxs-lookup"><span data-stu-id="8b548-136">Del</span></span>  <br/> |<span data-ttu-id="8b548-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="8b548-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="8b548-138">可选</span><span class="sxs-lookup"><span data-stu-id="8b548-138">optional</span></span>  <br/> |<span data-ttu-id="8b548-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="8b548-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="8b548-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b548-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="8b548-141">IX</span><span class="sxs-lookup"><span data-stu-id="8b548-141">IX</span></span>  <br/> |<span data-ttu-id="8b548-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8b548-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8b548-143">可选</span><span class="sxs-lookup"><span data-stu-id="8b548-143">optional</span></span>  <br/> |<span data-ttu-id="8b548-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="8b548-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="8b548-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="8b548-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="8b548-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="8b548-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="8b548-147">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b548-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8b548-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="8b548-148">LocalName</span></span>  <br/> |<span data-ttu-id="8b548-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8b548-149">xsd:string</span></span>  <br/> |<span data-ttu-id="8b548-150">可选</span><span class="sxs-lookup"><span data-stu-id="8b548-150">optional</span></span>  <br/> |<span data-ttu-id="8b548-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8b548-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="8b548-152">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b548-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b548-153">N</span><span class="sxs-lookup"><span data-stu-id="8b548-153">N</span></span>  <br/> |<span data-ttu-id="8b548-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8b548-154">xsd:string</span></span>  <br/> |<span data-ttu-id="8b548-155">可选</span><span class="sxs-lookup"><span data-stu-id="8b548-155">optional</span></span>  <br/> |<span data-ttu-id="8b548-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="8b548-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="8b548-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="8b548-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="8b548-158">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b548-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b548-159">T</span><span class="sxs-lookup"><span data-stu-id="8b548-159">T</span></span>  <br/> |<span data-ttu-id="8b548-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8b548-160">xsd:string</span></span>  <br/> |<span data-ttu-id="8b548-161">可选</span><span class="sxs-lookup"><span data-stu-id="8b548-161">optional</span></span>  <br/> |<span data-ttu-id="8b548-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="8b548-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="8b548-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="8b548-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="8b548-164">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b548-164">Values of the xsd:string type.</span></span>  <br/> |
   

