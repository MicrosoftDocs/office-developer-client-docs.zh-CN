---
title: Row 元素 ("Tabs" 内容) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a30d5701-4b56-c44c-fb62-d9daaee3b86e
description: 包含控制制表位位置和对齐方式的形状或样式的单元格。
ms.openlocfilehash: 530d2e564615f33292b52f9aa860c0cf2794bc67
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538177"
---
# <a name="row-element-tabs-section-visio-xml"></a><span data-ttu-id="cbc38-103">Row 元素 ("Tabs" 内容) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="cbc38-103">Row element (Tabs Section) (Visio XML)</span></span>

<span data-ttu-id="cbc38-104">包含控制制表位位置和对齐方式的形状或样式的单元格。</span><span class="sxs-lookup"><span data-stu-id="cbc38-104">Contains cells for shapes or styles that control tab stop position and alignment.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="cbc38-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="cbc38-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cbc38-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="cbc38-106">**Element type**</span></span> <br/> |[<span data-ttu-id="cbc38-107">TabsRow_Type</span><span class="sxs-lookup"><span data-stu-id="cbc38-107">TabsRow_Type</span></span>](tabsrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="cbc38-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="cbc38-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="cbc38-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="cbc38-109">**Schema file**</span></span> <br/> |<span data-ttu-id="cbc38-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="cbc38-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="cbc38-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="cbc38-111">**Document parts**</span></span> <br/> |<span data-ttu-id="cbc38-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="cbc38-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="cbc38-113">定义</span><span class="sxs-lookup"><span data-stu-id="cbc38-113">Definition</span></span>

```XML
< xs:element name="Row" type="TabsRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="cbc38-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="cbc38-114">Elements and attributes</span></span>

<span data-ttu-id="cbc38-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="cbc38-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="cbc38-116">父元素</span><span class="sxs-lookup"><span data-stu-id="cbc38-116">Parent elements</span></span>

|<span data-ttu-id="cbc38-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="cbc38-117">**Element**</span></span>|<span data-ttu-id="cbc38-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="cbc38-118">**Type**</span></span>|<span data-ttu-id="cbc38-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbc38-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="cbc38-120">Section</span><span class="sxs-lookup"><span data-stu-id="cbc38-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="cbc38-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="cbc38-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="cbc38-122">包含控制制表位位置和对齐方式的形状或样式的单元格。</span><span class="sxs-lookup"><span data-stu-id="cbc38-122">Contains cells for shapes or styles that control tab stop position and alignment.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="cbc38-123">子元素</span><span class="sxs-lookup"><span data-stu-id="cbc38-123">Child elements</span></span>

|<span data-ttu-id="cbc38-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="cbc38-124">**Element**</span></span>|<span data-ttu-id="cbc38-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="cbc38-125">**Type**</span></span>|<span data-ttu-id="cbc38-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbc38-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="cbc38-127">Cell</span><span class="sxs-lookup"><span data-stu-id="cbc38-127">Cell</span></span>](cell-element-tabs-sectionvisio-xml.md) <br/> |[<span data-ttu-id="cbc38-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="cbc38-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="cbc38-129">指定一个属性。</span><span class="sxs-lookup"><span data-stu-id="cbc38-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="cbc38-130">属性</span><span class="sxs-lookup"><span data-stu-id="cbc38-130">Attributes</span></span>

|<span data-ttu-id="cbc38-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="cbc38-131">**Attribute**</span></span>|<span data-ttu-id="cbc38-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="cbc38-132">**Type**</span></span>|<span data-ttu-id="cbc38-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="cbc38-133">**Required**</span></span>|<span data-ttu-id="cbc38-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="cbc38-134">**Description**</span></span>|<span data-ttu-id="cbc38-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="cbc38-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cbc38-136">键</span><span class="sxs-lookup"><span data-stu-id="cbc38-136">Del</span></span>  <br/> |<span data-ttu-id="cbc38-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="cbc38-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="cbc38-138">可选</span><span class="sxs-lookup"><span data-stu-id="cbc38-138">optional</span></span>  <br/> |<span data-ttu-id="cbc38-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="cbc38-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="cbc38-140">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cbc38-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="cbc38-141">IX</span><span class="sxs-lookup"><span data-stu-id="cbc38-141">IX</span></span>  <br/> |<span data-ttu-id="cbc38-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="cbc38-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="cbc38-143">可选</span><span class="sxs-lookup"><span data-stu-id="cbc38-143">optional</span></span>  <br/> |<span data-ttu-id="cbc38-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="cbc38-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="cbc38-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="cbc38-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="cbc38-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="cbc38-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="cbc38-147">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cbc38-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="cbc38-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="cbc38-148">LocalName</span></span>  <br/> |<span data-ttu-id="cbc38-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cbc38-149">xsd:string</span></span>  <br/> |<span data-ttu-id="cbc38-150">可选</span><span class="sxs-lookup"><span data-stu-id="cbc38-150">optional</span></span>  <br/> |<span data-ttu-id="cbc38-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="cbc38-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="cbc38-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cbc38-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="cbc38-153">N</span><span class="sxs-lookup"><span data-stu-id="cbc38-153">N</span></span>  <br/> |<span data-ttu-id="cbc38-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cbc38-154">xsd:string</span></span>  <br/> |<span data-ttu-id="cbc38-155">可选</span><span class="sxs-lookup"><span data-stu-id="cbc38-155">optional</span></span>  <br/> |<span data-ttu-id="cbc38-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="cbc38-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="cbc38-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="cbc38-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="cbc38-158">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cbc38-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="cbc38-159">T</span><span class="sxs-lookup"><span data-stu-id="cbc38-159">T</span></span>  <br/> |<span data-ttu-id="cbc38-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="cbc38-160">xsd:string</span></span>  <br/> |<span data-ttu-id="cbc38-161">可选</span><span class="sxs-lookup"><span data-stu-id="cbc38-161">optional</span></span>  <br/> |<span data-ttu-id="cbc38-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="cbc38-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="cbc38-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="cbc38-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="cbc38-164">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="cbc38-164">Values of the xsd:string type.</span></span>  <br/> |
   

