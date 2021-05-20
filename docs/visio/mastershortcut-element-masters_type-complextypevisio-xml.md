---
title: 'MasterShortcut (Masters_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定文档中定义的主控母版快捷方式。
ms.openlocfilehash: 94ac64ff0080bf7d50df67674022ce53f32339a4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538205"
---
# <a name="mastershortcut-element-masters_type-complextype-visio-xml"></a><span data-ttu-id="8b07a-103">MasterShortcut (Masters_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="8b07a-103">MasterShortcut element (Masters_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="8b07a-104">指定文档中定义的主控母版快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8b07a-104">Specifies a master shortcut defined in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8b07a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8b07a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8b07a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8b07a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8b07a-107">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="8b07a-107">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8b07a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8b07a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8b07a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8b07a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8b07a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="8b07a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8b07a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8b07a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8b07a-112">master#.xml</span><span class="sxs-lookup"><span data-stu-id="8b07a-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8b07a-113">定义</span><span class="sxs-lookup"><span data-stu-id="8b07a-113">Definition</span></span>

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8b07a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8b07a-114">Elements and attributes</span></span>

<span data-ttu-id="8b07a-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8b07a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8b07a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8b07a-116">Parent elements</span></span>

|<span data-ttu-id="8b07a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8b07a-117">**Element**</span></span>|<span data-ttu-id="8b07a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b07a-118">**Type**</span></span>|<span data-ttu-id="8b07a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b07a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8b07a-120">Masters</span><span class="sxs-lookup"><span data-stu-id="8b07a-120">Masters</span></span>](masters-elementvisio-xml.md) <br/> |[<span data-ttu-id="8b07a-121">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="8b07a-121">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8b07a-122">包含 **文档的 Master** 元素。</span><span class="sxs-lookup"><span data-stu-id="8b07a-122">Contains the **Master** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8b07a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8b07a-123">Child elements</span></span>

|<span data-ttu-id="8b07a-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="8b07a-124">**Element**</span></span>|<span data-ttu-id="8b07a-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b07a-125">**Type**</span></span>|<span data-ttu-id="8b07a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b07a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8b07a-127">Icon</span><span class="sxs-lookup"><span data-stu-id="8b07a-127">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8b07a-128">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="8b07a-128">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8b07a-129">指定 MIME (Master 或 **MasterShortcut** 元素的 MIME) 编码的二进制图标 (，格式为 .ico ) 。</span><span class="sxs-lookup"><span data-stu-id="8b07a-129">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a **Master** or **MasterShortcut** element in a document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="8b07a-130">属性</span><span class="sxs-lookup"><span data-stu-id="8b07a-130">Attributes</span></span>

|<span data-ttu-id="8b07a-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="8b07a-131">**Attribute**</span></span>|<span data-ttu-id="8b07a-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b07a-132">**Type**</span></span>|<span data-ttu-id="8b07a-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="8b07a-133">**Required**</span></span>|<span data-ttu-id="8b07a-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="8b07a-134">**Description**</span></span>|<span data-ttu-id="8b07a-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8b07a-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b07a-136">AlignName</span><span class="sxs-lookup"><span data-stu-id="8b07a-136">AlignName</span></span>  <br/> |<span data-ttu-id="8b07a-137">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="8b07a-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="8b07a-138">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-138">optional</span></span>  <br/> |<span data-ttu-id="8b07a-139">指定模具窗口中元素的文本是左对齐、右对齐还是居中对齐。</span><span class="sxs-lookup"><span data-stu-id="8b07a-139">Specifies whether the element's text in the stencil window is aligned left, right, or center.</span></span>  <br/> |<span data-ttu-id="8b07a-140">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-141">IconSize</span><span class="sxs-lookup"><span data-stu-id="8b07a-141">IconSize</span></span>  <br/> |<span data-ttu-id="8b07a-142">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="8b07a-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="8b07a-143">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-143">optional</span></span>  <br/> |<span data-ttu-id="8b07a-144">元素图标的大小。</span><span class="sxs-lookup"><span data-stu-id="8b07a-144">The size of the element's icon.</span></span>  <br/> |<span data-ttu-id="8b07a-145">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-146">ID</span><span class="sxs-lookup"><span data-stu-id="8b07a-146">ID</span></span>  <br/> |<span data-ttu-id="8b07a-147">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8b07a-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8b07a-148">必需</span><span class="sxs-lookup"><span data-stu-id="8b07a-148">required</span></span>  <br/> |<span data-ttu-id="8b07a-149">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8b07a-149">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="8b07a-150">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-151">名称</span><span class="sxs-lookup"><span data-stu-id="8b07a-151">Name</span></span>  <br/> |<span data-ttu-id="8b07a-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8b07a-152">xsd:string</span></span>  <br/> |<span data-ttu-id="8b07a-153">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-153">optional</span></span>  <br/> |<span data-ttu-id="8b07a-154">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="8b07a-154">The name of the element.</span></span>  <br/> |<span data-ttu-id="8b07a-155">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-156">NameU</span><span class="sxs-lookup"><span data-stu-id="8b07a-156">NameU</span></span>  <br/> |<span data-ttu-id="8b07a-157">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8b07a-157">xsd:string</span></span>  <br/> |<span data-ttu-id="8b07a-158">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-158">optional</span></span>  <br/> |<span data-ttu-id="8b07a-159">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="8b07a-159">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="8b07a-160">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-160">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-161">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="8b07a-161">PatternFlags</span></span>  <br/> |<span data-ttu-id="8b07a-162">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="8b07a-162">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="8b07a-163">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-163">optional</span></span>  <br/> |<span data-ttu-id="8b07a-164">确定主控形状是否表现为自定义图案。</span><span class="sxs-lookup"><span data-stu-id="8b07a-164">Determines whether a master behaves as a custom pattern.</span></span>  <br/> |<span data-ttu-id="8b07a-165">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-165">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-166">Prompt</span><span class="sxs-lookup"><span data-stu-id="8b07a-166">Prompt</span></span>  <br/> |<span data-ttu-id="8b07a-167">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8b07a-167">xsd:string</span></span>  <br/> |<span data-ttu-id="8b07a-168">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-168">optional</span></span>  <br/> |<span data-ttu-id="8b07a-169">元素的状态栏和工具提示提示。</span><span class="sxs-lookup"><span data-stu-id="8b07a-169">The status bar and tool tip prompt for the element.</span></span>  <br/> |<span data-ttu-id="8b07a-170">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-170">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-171">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="8b07a-171">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="8b07a-172">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8b07a-172">xsd:string</span></span>  <br/> |<span data-ttu-id="8b07a-173">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-173">optional</span></span>  <br/> |<span data-ttu-id="8b07a-174">元素的帮助字符串。</span><span class="sxs-lookup"><span data-stu-id="8b07a-174">A help string for the element.</span></span>  <br/> |<span data-ttu-id="8b07a-175">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="8b07a-176">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="8b07a-176">ShortcutURL</span></span>  <br/> |<span data-ttu-id="8b07a-177">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8b07a-177">xsd:string</span></span>  <br/> |<span data-ttu-id="8b07a-178">可选</span><span class="sxs-lookup"><span data-stu-id="8b07a-178">optional</span></span>  <br/> |<span data-ttu-id="8b07a-179">**MasterShortcut** 元素的 URL。</span><span class="sxs-lookup"><span data-stu-id="8b07a-179">A URL to a **MasterShortcut** element.</span></span>  <br/> |<span data-ttu-id="8b07a-180">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8b07a-180">Values of the xsd:string type.</span></span>  <br/> |
   

