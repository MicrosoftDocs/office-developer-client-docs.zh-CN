---
title: 'Row 元素 (Field Section)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7883cb55-a7db-10c0-be20-5d3c561e490f
description: 显示使用“域”对话框在形状的文本中插入的函数和公式。
ms.openlocfilehash: c05f704610d7061b9e2c8b742adc39f2b72ba4ae
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541755"
---
# <a name="row-element-field-section-visio-xml"></a><span data-ttu-id="39809-103">Row 元素 (Field Section)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="39809-103">Row element (Field Section) (Visio XML)</span></span>

<span data-ttu-id="39809-104">显示使用“域”对话框在形状的文本中插入的函数和公式。</span><span class="sxs-lookup"><span data-stu-id="39809-104">Displays functions and formulas inserted in the shape's text by using the Field dialog box.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="39809-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="39809-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39809-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="39809-106">**Element type**</span></span> <br/> |[<span data-ttu-id="39809-107">FieldRow_Type</span><span class="sxs-lookup"><span data-stu-id="39809-107">FieldRow_Type</span></span>](fieldrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="39809-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="39809-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="39809-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="39809-109">**Schema file**</span></span> <br/> |<span data-ttu-id="39809-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="39809-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="39809-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="39809-111">**Document parts**</span></span> <br/> |<span data-ttu-id="39809-112">master#.xml，page#.xml</span><span class="sxs-lookup"><span data-stu-id="39809-112">master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="39809-113">定义</span><span class="sxs-lookup"><span data-stu-id="39809-113">Definition</span></span>

```XML
< xs:element name="Row" type="FieldRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="39809-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="39809-114">Elements and attributes</span></span>

<span data-ttu-id="39809-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="39809-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="39809-116">父元素</span><span class="sxs-lookup"><span data-stu-id="39809-116">Parent elements</span></span>

|<span data-ttu-id="39809-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="39809-117">**Element**</span></span>|<span data-ttu-id="39809-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="39809-118">**Type**</span></span>|<span data-ttu-id="39809-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="39809-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="39809-120">Section</span><span class="sxs-lookup"><span data-stu-id="39809-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="39809-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="39809-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="39809-122">显示使用“域”对话框在形状的文本中插入的函数和公式。</span><span class="sxs-lookup"><span data-stu-id="39809-122">Displays functions and formulas inserted in the shape's text by using the Field dialog box.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="39809-123">子元素</span><span class="sxs-lookup"><span data-stu-id="39809-123">Child elements</span></span>

|<span data-ttu-id="39809-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="39809-124">**Element**</span></span>|<span data-ttu-id="39809-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="39809-125">**Type**</span></span>|<span data-ttu-id="39809-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="39809-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="39809-127">Cell</span><span class="sxs-lookup"><span data-stu-id="39809-127">Cell</span></span>](cell-element-field-sectionvisio-xml.md) <br/> |[<span data-ttu-id="39809-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="39809-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="39809-129">使用"域"对话框显示形状文本中插入的函数和公式</span><span class="sxs-lookup"><span data-stu-id="39809-129">Displays functions and formulas inserted in the shape's text by using the Field dialog box</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="39809-130">属性</span><span class="sxs-lookup"><span data-stu-id="39809-130">Attributes</span></span>

|<span data-ttu-id="39809-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="39809-131">**Attribute**</span></span>|<span data-ttu-id="39809-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="39809-132">**Type**</span></span>|<span data-ttu-id="39809-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="39809-133">**Required**</span></span>|<span data-ttu-id="39809-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="39809-134">**Description**</span></span>|<span data-ttu-id="39809-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="39809-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39809-136">Del</span><span class="sxs-lookup"><span data-stu-id="39809-136">Del</span></span>  <br/> |<span data-ttu-id="39809-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="39809-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="39809-138">可选</span><span class="sxs-lookup"><span data-stu-id="39809-138">optional</span></span>  <br/> |<span data-ttu-id="39809-139">指定是否已删除从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="39809-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="39809-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39809-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="39809-141">IX</span><span class="sxs-lookup"><span data-stu-id="39809-141">IX</span></span>  <br/> |<span data-ttu-id="39809-142">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="39809-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="39809-143">可选</span><span class="sxs-lookup"><span data-stu-id="39809-143">optional</span></span>  <br/> |<span data-ttu-id="39809-144">指定行的从 1 开始标识符。</span><span class="sxs-lookup"><span data-stu-id="39809-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="39809-145">它应不唯一，并且大于同一节中的其他标识符。IX 属性仅用于 Character、Connection、Field、FillGradient、Geometry、Layer、LineGradient、Paragraph、Reviewer、Scratch 和 Tabs 部分。</span><span class="sxs-lookup"><span data-stu-id="39809-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="39809-146">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="39809-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="39809-147">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39809-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="39809-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="39809-148">LocalName</span></span>  <br/> |<span data-ttu-id="39809-149">xsd：string</span><span class="sxs-lookup"><span data-stu-id="39809-149">xsd:string</span></span>  <br/> |<span data-ttu-id="39809-150">可选</span><span class="sxs-lookup"><span data-stu-id="39809-150">optional</span></span>  <br/> |<span data-ttu-id="39809-151">指定行的唯一依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="39809-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="39809-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39809-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="39809-153">N</span><span class="sxs-lookup"><span data-stu-id="39809-153">N</span></span>  <br/> |<span data-ttu-id="39809-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="39809-154">xsd:string</span></span>  <br/> |<span data-ttu-id="39809-155">可选</span><span class="sxs-lookup"><span data-stu-id="39809-155">optional</span></span>  <br/> |<span data-ttu-id="39809-156">指定行的唯一与语言无关的名称。N 属性仅用于 User、Property、Actions、Control、Connection、Hyperlink 和 ActionTag 部分。</span><span class="sxs-lookup"><span data-stu-id="39809-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="39809-157">一行只能有一个 IX 或 N 属性。</span><span class="sxs-lookup"><span data-stu-id="39809-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="39809-158">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39809-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="39809-159">T</span><span class="sxs-lookup"><span data-stu-id="39809-159">T</span></span>  <br/> |<span data-ttu-id="39809-160">xsd：string</span><span class="sxs-lookup"><span data-stu-id="39809-160">xsd:string</span></span>  <br/> |<span data-ttu-id="39809-161">可选</span><span class="sxs-lookup"><span data-stu-id="39809-161">optional</span></span>  <br/> |<span data-ttu-id="39809-162">指定由行表示的几何路径类型，并用于几何可视化。</span><span class="sxs-lookup"><span data-stu-id="39809-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="39809-163">T 属性仅用于"Geometry"内容。</span><span class="sxs-lookup"><span data-stu-id="39809-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="39809-164">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="39809-164">Values of the xsd:string type.</span></span>  <br/> |
   

