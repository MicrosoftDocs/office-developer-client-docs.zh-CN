---
title: Row 元素 ("线条渐变" 部分) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4d823766-5cb0-925c-f622-18025f44426c
description: 包含颜色、透明度以及线条渐变的渐变停止点的位置。
ms.openlocfilehash: 105d93344343f223a6b5d909f1174f7df56ffb4d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358427"
---
# <a name="row-element-line-gradient-section-visio-xml"></a><span data-ttu-id="e581d-103">Row 元素 ("线条渐变" 部分) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e581d-103">Row element (Line Gradient Section) ('Visio XML')</span></span>

<span data-ttu-id="e581d-104">包含颜色、透明度以及线条渐变的渐变停止点的位置。</span><span class="sxs-lookup"><span data-stu-id="e581d-104">Contains the color, transparency, and position of a gradient stop for a line gradient.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e581d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e581d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e581d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e581d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e581d-107">LineGradientRow_Type</span><span class="sxs-lookup"><span data-stu-id="e581d-107">LineGradientRow_Type</span></span>](linegradientrow_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e581d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e581d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e581d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e581d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e581d-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e581d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e581d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e581d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e581d-112">document .xml、master # .xml、第 .xml 页</span><span class="sxs-lookup"><span data-stu-id="e581d-112">document.xml, master#.xml, page#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e581d-113">定义</span><span class="sxs-lookup"><span data-stu-id="e581d-113">Definition</span></span>

```XML
< xs:element name="Row" type="LineGradientRow_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e581d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e581d-114">Elements and attributes</span></span>

<span data-ttu-id="e581d-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e581d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e581d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e581d-116">Parent elements</span></span>

|<span data-ttu-id="e581d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e581d-117">**Element**</span></span>|<span data-ttu-id="e581d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e581d-118">**Type**</span></span>|<span data-ttu-id="e581d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e581d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e581d-120">Section</span><span class="sxs-lookup"><span data-stu-id="e581d-120">Section</span></span>](section-element-sheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e581d-121">Section_Type</span><span class="sxs-lookup"><span data-stu-id="e581d-121">Section_Type</span></span>](section_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e581d-122">包含颜色、透明度以及线条渐变的渐变停止点的位置。</span><span class="sxs-lookup"><span data-stu-id="e581d-122">Contains the color, transparency, and position of a gradient stop for a line gradient.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e581d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e581d-123">Child elements</span></span>

|<span data-ttu-id="e581d-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="e581d-124">**Element**</span></span>|<span data-ttu-id="e581d-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e581d-125">**Type**</span></span>|<span data-ttu-id="e581d-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="e581d-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e581d-127">Cell</span><span class="sxs-lookup"><span data-stu-id="e581d-127">Cell</span></span>](cell-element-line-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="e581d-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="e581d-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e581d-129">指定一个属性。</span><span class="sxs-lookup"><span data-stu-id="e581d-129">Specifies a single property.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="e581d-130">属性</span><span class="sxs-lookup"><span data-stu-id="e581d-130">Attributes</span></span>

|<span data-ttu-id="e581d-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="e581d-131">**Attribute**</span></span>|<span data-ttu-id="e581d-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="e581d-132">**Type**</span></span>|<span data-ttu-id="e581d-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="e581d-133">**Required**</span></span>|<span data-ttu-id="e581d-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="e581d-134">**Description**</span></span>|<span data-ttu-id="e581d-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e581d-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e581d-136">键</span><span class="sxs-lookup"><span data-stu-id="e581d-136">Del</span></span>  <br/> |<span data-ttu-id="e581d-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e581d-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e581d-138">可选</span><span class="sxs-lookup"><span data-stu-id="e581d-138">optional</span></span>  <br/> |<span data-ttu-id="e581d-139">指定是否已删除要从主控形状继承的行。</span><span class="sxs-lookup"><span data-stu-id="e581d-139">Specifies whether a row that would otherwise be inherited from a master shape has been deleted.</span></span>  <br/> |<span data-ttu-id="e581d-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e581d-140">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e581d-141">IX</span><span class="sxs-lookup"><span data-stu-id="e581d-141">IX</span></span>  <br/> |<span data-ttu-id="e581d-142">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e581d-142">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e581d-143">可选</span><span class="sxs-lookup"><span data-stu-id="e581d-143">optional</span></span>  <br/> |<span data-ttu-id="e581d-144">指定行的从1开始的标识符。</span><span class="sxs-lookup"><span data-stu-id="e581d-144">Specifies the one-based identifier for the row.</span></span> <span data-ttu-id="e581d-145">它应是唯一, 并且大于同一节中的其他标识符。IX 属性仅用于字符、Connection、Field、FillGradient、Geometry、Layer、LineGradient、段落、审阅者、草稿和选项卡部分。</span><span class="sxs-lookup"><span data-stu-id="e581d-145">It should be unqiue and greater than other identifiers in the same section.The IX attribute is only used for the Character, Connection, Field, FillGradient, Geometry, Layer, LineGradient, Paragraph, Reviewer, Scratch, and Tabs sections.</span></span> <span data-ttu-id="e581d-146">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="e581d-146">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="e581d-147">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e581d-147">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e581d-148">LocalName</span><span class="sxs-lookup"><span data-stu-id="e581d-148">LocalName</span></span>  <br/> |<span data-ttu-id="e581d-149">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e581d-149">xsd:string</span></span>  <br/> |<span data-ttu-id="e581d-150">可选</span><span class="sxs-lookup"><span data-stu-id="e581d-150">optional</span></span>  <br/> |<span data-ttu-id="e581d-151">指定行的与语言相关的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="e581d-151">Specifies the unique language-dependent name of the row.</span></span>  <br/> |<span data-ttu-id="e581d-152">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e581d-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e581d-153">N</span><span class="sxs-lookup"><span data-stu-id="e581d-153">N</span></span>  <br/> |<span data-ttu-id="e581d-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e581d-154">xsd:string</span></span>  <br/> |<span data-ttu-id="e581d-155">可选</span><span class="sxs-lookup"><span data-stu-id="e581d-155">optional</span></span>  <br/> |<span data-ttu-id="e581d-156">指定行的与语言无关的唯一名称。N 属性仅用于用户、属性、操作、控制、Connection、Hyperlink 和 ActionTag 节。</span><span class="sxs-lookup"><span data-stu-id="e581d-156">Specifies the unique language-independent name of the row.The N attribute is only used for the User, Property, Actions, Control, Connection, Hyperlink, and ActionTag sections.</span></span> <span data-ttu-id="e581d-157">行只能具有 IX 或 N 属性中的一个。</span><span class="sxs-lookup"><span data-stu-id="e581d-157">A row can only have one of the IX or N attributes.</span></span>  <br/> |<span data-ttu-id="e581d-158">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e581d-158">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e581d-159">T</span><span class="sxs-lookup"><span data-stu-id="e581d-159">T</span></span>  <br/> |<span data-ttu-id="e581d-160">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e581d-160">xsd:string</span></span>  <br/> |<span data-ttu-id="e581d-161">可选</span><span class="sxs-lookup"><span data-stu-id="e581d-161">optional</span></span>  <br/> |<span data-ttu-id="e581d-162">指定由行表示并在几何图形可视化中使用的几何路径的类型。</span><span class="sxs-lookup"><span data-stu-id="e581d-162">Specifies the type of the geometric path represented by the row and used in geometry visualization.</span></span> <span data-ttu-id="e581d-163">T 属性仅用于 "Geometry" 部分。</span><span class="sxs-lookup"><span data-stu-id="e581d-163">The T attribute is only used for the Geometry section.</span></span>  <br/> |<span data-ttu-id="e581d-164">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e581d-164">Values of the xsd:string type.</span></span>  <br/> |
   

