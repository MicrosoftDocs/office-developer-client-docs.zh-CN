---
title: MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定文档中定义的主控形状快捷方式。
ms.openlocfilehash: 03196c6fc1f3424c61bcce406dc050f2d5a73365
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392954"
---
# <a name="mastershortcut-element-masterstype-complextype-visio-xml"></a><span data-ttu-id="f9c22-103">MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f9c22-103">MasterShortcut element (Masters_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="f9c22-104">指定文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="f9c22-104">Specifies a master shortcut defined in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f9c22-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f9c22-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f9c22-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f9c22-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f9c22-107">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="f9c22-107">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f9c22-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f9c22-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f9c22-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f9c22-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f9c22-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="f9c22-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f9c22-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f9c22-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f9c22-112">主 #.xml</span><span class="sxs-lookup"><span data-stu-id="f9c22-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f9c22-113">定义</span><span class="sxs-lookup"><span data-stu-id="f9c22-113">Definition</span></span>

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f9c22-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f9c22-114">Elements and attributes</span></span>

<span data-ttu-id="f9c22-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f9c22-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f9c22-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f9c22-116">Parent elements</span></span>

|<span data-ttu-id="f9c22-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9c22-117">**Element**</span></span>|<span data-ttu-id="f9c22-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9c22-118">**Type**</span></span>|<span data-ttu-id="f9c22-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9c22-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9c22-120">Masters</span><span class="sxs-lookup"><span data-stu-id="f9c22-120">Masters</span></span>](masters-elementvisio-xml.md) <br/> |[<span data-ttu-id="f9c22-121">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="f9c22-121">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9c22-122">包含文档的**主控形状**元素。</span><span class="sxs-lookup"><span data-stu-id="f9c22-122">Contains the **Master** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f9c22-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f9c22-123">Child elements</span></span>

|<span data-ttu-id="f9c22-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f9c22-124">**Element**</span></span>|<span data-ttu-id="f9c22-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9c22-125">**Type**</span></span>|<span data-ttu-id="f9c22-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9c22-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f9c22-127">图标</span><span class="sxs-lookup"><span data-stu-id="f9c22-127">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f9c22-128">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="f9c22-128">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f9c22-129">指定的 MIME （多用途 Internet 邮件扩展） 的文档中的**主控形状**或**MasterShortcut**元素编码二进制图标 （.ico 格式）。</span><span class="sxs-lookup"><span data-stu-id="f9c22-129">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a **Master** or **MasterShortcut** element in a document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f9c22-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="f9c22-130">Attributes</span></span>

|<span data-ttu-id="f9c22-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="f9c22-131">**Attribute**</span></span>|<span data-ttu-id="f9c22-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="f9c22-132">**Type**</span></span>|<span data-ttu-id="f9c22-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="f9c22-133">**Required**</span></span>|<span data-ttu-id="f9c22-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9c22-134">**Description**</span></span>|<span data-ttu-id="f9c22-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f9c22-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f9c22-136">AlignName</span><span class="sxs-lookup"><span data-stu-id="f9c22-136">AlignName</span></span>  <br/> |<span data-ttu-id="f9c22-137">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f9c22-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f9c22-138">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-138">optional</span></span>  <br/> |<span data-ttu-id="f9c22-139">指定模具窗口中的元素的文本是左、 右对齐还是中心。</span><span class="sxs-lookup"><span data-stu-id="f9c22-139">Specifies whether the element's text in the stencil window is aligned left, right, or center.</span></span>  <br/> |<span data-ttu-id="f9c22-140">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-141">IconSize</span><span class="sxs-lookup"><span data-stu-id="f9c22-141">IconSize</span></span>  <br/> |<span data-ttu-id="f9c22-142">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f9c22-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f9c22-143">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-143">optional</span></span>  <br/> |<span data-ttu-id="f9c22-144">元素的图标的大小。</span><span class="sxs-lookup"><span data-stu-id="f9c22-144">The size of the element's icon.</span></span>  <br/> |<span data-ttu-id="f9c22-145">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-146">ID</span><span class="sxs-lookup"><span data-stu-id="f9c22-146">ID</span></span>  <br/> |<span data-ttu-id="f9c22-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f9c22-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f9c22-148">必需</span><span class="sxs-lookup"><span data-stu-id="f9c22-148">required</span></span>  <br/> |<span data-ttu-id="f9c22-149">其父元素中的元素的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f9c22-149">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="f9c22-150">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-151">名称</span><span class="sxs-lookup"><span data-stu-id="f9c22-151">Name</span></span>  <br/> |<span data-ttu-id="f9c22-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9c22-152">xsd:string</span></span>  <br/> |<span data-ttu-id="f9c22-153">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-153">optional</span></span>  <br/> |<span data-ttu-id="f9c22-154">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="f9c22-154">The name of the element.</span></span>  <br/> |<span data-ttu-id="f9c22-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-156">NameU</span><span class="sxs-lookup"><span data-stu-id="f9c22-156">NameU</span></span>  <br/> |<span data-ttu-id="f9c22-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9c22-157">xsd:string</span></span>  <br/> |<span data-ttu-id="f9c22-158">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-158">optional</span></span>  <br/> |<span data-ttu-id="f9c22-159">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="f9c22-159">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="f9c22-160">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-160">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-161">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="f9c22-161">PatternFlags</span></span>  <br/> |<span data-ttu-id="f9c22-162">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f9c22-162">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f9c22-163">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-163">optional</span></span>  <br/> |<span data-ttu-id="f9c22-164">确定是否主控形状表现为自定义模式。</span><span class="sxs-lookup"><span data-stu-id="f9c22-164">Determines whether a master behaves as a custom pattern.</span></span>  <br/> |<span data-ttu-id="f9c22-165">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-165">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-166">提示</span><span class="sxs-lookup"><span data-stu-id="f9c22-166">Prompt</span></span>  <br/> |<span data-ttu-id="f9c22-167">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9c22-167">xsd:string</span></span>  <br/> |<span data-ttu-id="f9c22-168">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-168">optional</span></span>  <br/> |<span data-ttu-id="f9c22-169">状态栏和工具提示提示的元素。</span><span class="sxs-lookup"><span data-stu-id="f9c22-169">The status bar and tool tip prompt for the element.</span></span>  <br/> |<span data-ttu-id="f9c22-170">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-170">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-171">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="f9c22-171">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="f9c22-172">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9c22-172">xsd:string</span></span>  <br/> |<span data-ttu-id="f9c22-173">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-173">optional</span></span>  <br/> |<span data-ttu-id="f9c22-174">元素的帮助字符串。</span><span class="sxs-lookup"><span data-stu-id="f9c22-174">A help string for the element.</span></span>  <br/> |<span data-ttu-id="f9c22-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="f9c22-176">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="f9c22-176">ShortcutURL</span></span>  <br/> |<span data-ttu-id="f9c22-177">xsd: string</span><span class="sxs-lookup"><span data-stu-id="f9c22-177">xsd:string</span></span>  <br/> |<span data-ttu-id="f9c22-178">可选</span><span class="sxs-lookup"><span data-stu-id="f9c22-178">optional</span></span>  <br/> |<span data-ttu-id="f9c22-179">指向**MasterShortcut**元素的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9c22-179">A URL to a **MasterShortcut** element.</span></span>  <br/> |<span data-ttu-id="f9c22-180">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f9c22-180">Values of the xsd:string type.</span></span>  <br/> |
   

