---
title: MasterShortcut 元素 (Masters_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定在文档中定义的主控形状快捷方式。
ms.openlocfilehash: 03196c6fc1f3424c61bcce406dc050f2d5a73365
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341732"
---
# <a name="mastershortcut-element-masterstype-complextype-visio-xml"></a><span data-ttu-id="791d3-103">MasterShortcut 元素 (Masters_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="791d3-103">MasterShortcut element (Masters_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="791d3-104">指定在文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="791d3-104">Specifies a master shortcut defined in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="791d3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="791d3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="791d3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="791d3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="791d3-107">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="791d3-107">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="791d3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="791d3-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="791d3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="791d3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="791d3-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="791d3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="791d3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="791d3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="791d3-112">master # .xml</span><span class="sxs-lookup"><span data-stu-id="791d3-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="791d3-113">定义</span><span class="sxs-lookup"><span data-stu-id="791d3-113">Definition</span></span>

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="791d3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="791d3-114">Elements and attributes</span></span>

<span data-ttu-id="791d3-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="791d3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="791d3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="791d3-116">Parent elements</span></span>

|<span data-ttu-id="791d3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="791d3-117">**Element**</span></span>|<span data-ttu-id="791d3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="791d3-118">**Type**</span></span>|<span data-ttu-id="791d3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="791d3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="791d3-120">Masters</span><span class="sxs-lookup"><span data-stu-id="791d3-120">Masters</span></span>](masters-elementvisio-xml.md) <br/> |[<span data-ttu-id="791d3-121">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="791d3-121">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="791d3-122">包含文档的**主控形状**元素。</span><span class="sxs-lookup"><span data-stu-id="791d3-122">Contains the **Master** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="791d3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="791d3-123">Child elements</span></span>

|<span data-ttu-id="791d3-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="791d3-124">**Element**</span></span>|<span data-ttu-id="791d3-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="791d3-125">**Type**</span></span>|<span data-ttu-id="791d3-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="791d3-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="791d3-127">Icon</span><span class="sxs-lookup"><span data-stu-id="791d3-127">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="791d3-128">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="791d3-128">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="791d3-129">为文档中的**主控形状**或**MasterShortcut**元素指定 MIME (多用途 Internet 邮件扩展) 编码的二进制图标 (在 .ico 格式中)。</span><span class="sxs-lookup"><span data-stu-id="791d3-129">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a **Master** or **MasterShortcut** element in a document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="791d3-130">属性</span><span class="sxs-lookup"><span data-stu-id="791d3-130">Attributes</span></span>

|<span data-ttu-id="791d3-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="791d3-131">**Attribute**</span></span>|<span data-ttu-id="791d3-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="791d3-132">**Type**</span></span>|<span data-ttu-id="791d3-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="791d3-133">**Required**</span></span>|<span data-ttu-id="791d3-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="791d3-134">**Description**</span></span>|<span data-ttu-id="791d3-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="791d3-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="791d3-136">AlignName</span><span class="sxs-lookup"><span data-stu-id="791d3-136">AlignName</span></span>  <br/> |<span data-ttu-id="791d3-137">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="791d3-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="791d3-138">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-138">optional</span></span>  <br/> |<span data-ttu-id="791d3-139">指定是否在模具窗口中左对齐、右对齐或居中对齐元素的文本。</span><span class="sxs-lookup"><span data-stu-id="791d3-139">Specifies whether the element's text in the stencil window is aligned left, right, or center.</span></span>  <br/> |<span data-ttu-id="791d3-140">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="791d3-141">IconSize</span><span class="sxs-lookup"><span data-stu-id="791d3-141">IconSize</span></span>  <br/> |<span data-ttu-id="791d3-142">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="791d3-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="791d3-143">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-143">optional</span></span>  <br/> |<span data-ttu-id="791d3-144">元素的图标的大小。</span><span class="sxs-lookup"><span data-stu-id="791d3-144">The size of the element's icon.</span></span>  <br/> |<span data-ttu-id="791d3-145">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="791d3-146">ID</span><span class="sxs-lookup"><span data-stu-id="791d3-146">ID</span></span>  <br/> |<span data-ttu-id="791d3-147">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="791d3-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="791d3-148">必需</span><span class="sxs-lookup"><span data-stu-id="791d3-148">required</span></span>  <br/> |<span data-ttu-id="791d3-149">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="791d3-149">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="791d3-150">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="791d3-151">名称</span><span class="sxs-lookup"><span data-stu-id="791d3-151">Name</span></span>  <br/> |<span data-ttu-id="791d3-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="791d3-152">xsd:string</span></span>  <br/> |<span data-ttu-id="791d3-153">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-153">optional</span></span>  <br/> |<span data-ttu-id="791d3-154">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="791d3-154">The name of the element.</span></span>  <br/> |<span data-ttu-id="791d3-155">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="791d3-156">NameU</span><span class="sxs-lookup"><span data-stu-id="791d3-156">NameU</span></span>  <br/> |<span data-ttu-id="791d3-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="791d3-157">xsd:string</span></span>  <br/> |<span data-ttu-id="791d3-158">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-158">optional</span></span>  <br/> |<span data-ttu-id="791d3-159">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="791d3-159">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="791d3-160">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-160">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="791d3-161">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="791d3-161">PatternFlags</span></span>  <br/> |<span data-ttu-id="791d3-162">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="791d3-162">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="791d3-163">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-163">optional</span></span>  <br/> |<span data-ttu-id="791d3-164">确定主控形状是否表现为自定义图案。</span><span class="sxs-lookup"><span data-stu-id="791d3-164">Determines whether a master behaves as a custom pattern.</span></span>  <br/> |<span data-ttu-id="791d3-165">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-165">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="791d3-166">Prompt</span><span class="sxs-lookup"><span data-stu-id="791d3-166">Prompt</span></span>  <br/> |<span data-ttu-id="791d3-167">xsd: string</span><span class="sxs-lookup"><span data-stu-id="791d3-167">xsd:string</span></span>  <br/> |<span data-ttu-id="791d3-168">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-168">optional</span></span>  <br/> |<span data-ttu-id="791d3-169">元素的状态栏和工具提示提示。</span><span class="sxs-lookup"><span data-stu-id="791d3-169">The status bar and tool tip prompt for the element.</span></span>  <br/> |<span data-ttu-id="791d3-170">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-170">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="791d3-171">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="791d3-171">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="791d3-172">xsd: string</span><span class="sxs-lookup"><span data-stu-id="791d3-172">xsd:string</span></span>  <br/> |<span data-ttu-id="791d3-173">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-173">optional</span></span>  <br/> |<span data-ttu-id="791d3-174">元素的帮助字符串。</span><span class="sxs-lookup"><span data-stu-id="791d3-174">A help string for the element.</span></span>  <br/> |<span data-ttu-id="791d3-175">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="791d3-176">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="791d3-176">ShortcutURL</span></span>  <br/> |<span data-ttu-id="791d3-177">xsd: string</span><span class="sxs-lookup"><span data-stu-id="791d3-177">xsd:string</span></span>  <br/> |<span data-ttu-id="791d3-178">可选</span><span class="sxs-lookup"><span data-stu-id="791d3-178">optional</span></span>  <br/> |<span data-ttu-id="791d3-179">指向**MasterShortcut**元素的 URL。</span><span class="sxs-lookup"><span data-stu-id="791d3-179">A URL to a **MasterShortcut** element.</span></span>  <br/> |<span data-ttu-id="791d3-180">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="791d3-180">Values of the xsd:string type.</span></span>  <br/> |
   

