---
title: MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 62f0e093-5385-e552-f91a-02a65eb0e6e1
description: 指定文档中定义的主控形状快捷方式。
ms.openlocfilehash: be3e7d207e58d8c249598a7e156356d4f9e61849
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780704"
---
# <a name="mastershortcut-element-masterstype-complextype-visio-xml"></a><span data-ttu-id="44658-103">MasterShortcut 元素 （Masters_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="44658-103">MasterShortcut element (Masters_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="44658-104">指定文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="44658-104">Specifies a master shortcut defined in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="44658-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="44658-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="44658-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="44658-106">**Element type**</span></span> <br/> |[<span data-ttu-id="44658-107">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="44658-107">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="44658-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="44658-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="44658-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="44658-109">**Schema file**</span></span> <br/> |<span data-ttu-id="44658-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="44658-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="44658-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="44658-111">**Document parts**</span></span> <br/> |<span data-ttu-id="44658-112">主 #.xml</span><span class="sxs-lookup"><span data-stu-id="44658-112">master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="44658-113">定义</span><span class="sxs-lookup"><span data-stu-id="44658-113">Definition</span></span>

```XML
< xs:element name="MasterShortcut" type="MasterShortcut_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="44658-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="44658-114">Elements and attributes</span></span>

<span data-ttu-id="44658-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="44658-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="44658-116">父元素</span><span class="sxs-lookup"><span data-stu-id="44658-116">Parent elements</span></span>

|<span data-ttu-id="44658-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="44658-117">**Element**</span></span>|<span data-ttu-id="44658-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="44658-118">**Type**</span></span>|<span data-ttu-id="44658-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="44658-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="44658-120">Masters</span><span class="sxs-lookup"><span data-stu-id="44658-120">Masters</span></span>](masters-elementvisio-xml.md) <br/> |[<span data-ttu-id="44658-121">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="44658-121">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44658-122">包含文档的**主控形状**元素。</span><span class="sxs-lookup"><span data-stu-id="44658-122">Contains the **Master** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="44658-123">子元素</span><span class="sxs-lookup"><span data-stu-id="44658-123">Child elements</span></span>

|<span data-ttu-id="44658-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="44658-124">**Element**</span></span>|<span data-ttu-id="44658-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="44658-125">**Type**</span></span>|<span data-ttu-id="44658-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="44658-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="44658-127">图标</span><span class="sxs-lookup"><span data-stu-id="44658-127">Icon</span></span>](icon-element-mastershortcut_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="44658-128">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="44658-128">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44658-129">指定的 MIME （多用途 Internet 邮件扩展） 的文档中的**主控形状**或**MasterShortcut**元素编码二进制图标 （.ico 格式）。</span><span class="sxs-lookup"><span data-stu-id="44658-129">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a **Master** or **MasterShortcut** element in a document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="44658-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="44658-130">Attributes</span></span>

|<span data-ttu-id="44658-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="44658-131">**Attribute**</span></span>|<span data-ttu-id="44658-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="44658-132">**Type**</span></span>|<span data-ttu-id="44658-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="44658-133">**Required**</span></span>|<span data-ttu-id="44658-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="44658-134">**Description**</span></span>|<span data-ttu-id="44658-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="44658-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44658-136">AlignName</span><span class="sxs-lookup"><span data-stu-id="44658-136">AlignName</span></span>  <br/> |<span data-ttu-id="44658-137">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="44658-137">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="44658-138">可选</span><span class="sxs-lookup"><span data-stu-id="44658-138">optional</span></span>  <br/> |<span data-ttu-id="44658-139">指定模具窗口中的元素的文本是左、 右对齐还是中心。</span><span class="sxs-lookup"><span data-stu-id="44658-139">Specifies whether the element's text in the stencil window is aligned left, right, or center.</span></span>  <br/> |<span data-ttu-id="44658-140">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-140">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="44658-141">IconSize</span><span class="sxs-lookup"><span data-stu-id="44658-141">IconSize</span></span>  <br/> |<span data-ttu-id="44658-142">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="44658-142">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="44658-143">可选</span><span class="sxs-lookup"><span data-stu-id="44658-143">optional</span></span>  <br/> |<span data-ttu-id="44658-144">元素的图标的大小。</span><span class="sxs-lookup"><span data-stu-id="44658-144">The size of the element's icon.</span></span>  <br/> |<span data-ttu-id="44658-145">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-145">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="44658-146">ID</span><span class="sxs-lookup"><span data-stu-id="44658-146">ID</span></span>  <br/> |<span data-ttu-id="44658-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="44658-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="44658-148">必需</span><span class="sxs-lookup"><span data-stu-id="44658-148">required</span></span>  <br/> |<span data-ttu-id="44658-149">其父元素中的元素的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="44658-149">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="44658-150">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-150">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="44658-151">名称</span><span class="sxs-lookup"><span data-stu-id="44658-151">Name</span></span>  <br/> |<span data-ttu-id="44658-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44658-152">xsd:string</span></span>  <br/> |<span data-ttu-id="44658-153">可选</span><span class="sxs-lookup"><span data-stu-id="44658-153">optional</span></span>  <br/> |<span data-ttu-id="44658-154">元素的名称。</span><span class="sxs-lookup"><span data-stu-id="44658-154">The name of the element.</span></span>  <br/> |<span data-ttu-id="44658-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="44658-156">NameU</span><span class="sxs-lookup"><span data-stu-id="44658-156">NameU</span></span>  <br/> |<span data-ttu-id="44658-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44658-157">xsd:string</span></span>  <br/> |<span data-ttu-id="44658-158">可选</span><span class="sxs-lookup"><span data-stu-id="44658-158">optional</span></span>  <br/> |<span data-ttu-id="44658-159">元素的通用名称。</span><span class="sxs-lookup"><span data-stu-id="44658-159">The universal name of the element.</span></span>  <br/> |<span data-ttu-id="44658-160">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-160">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="44658-161">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="44658-161">PatternFlags</span></span>  <br/> |<span data-ttu-id="44658-162">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="44658-162">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="44658-163">可选</span><span class="sxs-lookup"><span data-stu-id="44658-163">optional</span></span>  <br/> |<span data-ttu-id="44658-164">确定是否主控形状表现为自定义模式。</span><span class="sxs-lookup"><span data-stu-id="44658-164">Determines whether a master behaves as a custom pattern.</span></span>  <br/> |<span data-ttu-id="44658-165">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-165">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="44658-166">提示</span><span class="sxs-lookup"><span data-stu-id="44658-166">Prompt</span></span>  <br/> |<span data-ttu-id="44658-167">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44658-167">xsd:string</span></span>  <br/> |<span data-ttu-id="44658-168">可选</span><span class="sxs-lookup"><span data-stu-id="44658-168">optional</span></span>  <br/> |<span data-ttu-id="44658-169">状态栏和工具提示提示的元素。</span><span class="sxs-lookup"><span data-stu-id="44658-169">The status bar and tool tip prompt for the element.</span></span>  <br/> |<span data-ttu-id="44658-170">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-170">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="44658-171">ShortcutHelp</span><span class="sxs-lookup"><span data-stu-id="44658-171">ShortcutHelp</span></span>  <br/> |<span data-ttu-id="44658-172">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44658-172">xsd:string</span></span>  <br/> |<span data-ttu-id="44658-173">可选</span><span class="sxs-lookup"><span data-stu-id="44658-173">optional</span></span>  <br/> |<span data-ttu-id="44658-174">元素的帮助字符串。</span><span class="sxs-lookup"><span data-stu-id="44658-174">A help string for the element.</span></span>  <br/> |<span data-ttu-id="44658-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="44658-176">ShortcutURL</span><span class="sxs-lookup"><span data-stu-id="44658-176">ShortcutURL</span></span>  <br/> |<span data-ttu-id="44658-177">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44658-177">xsd:string</span></span>  <br/> |<span data-ttu-id="44658-178">可选</span><span class="sxs-lookup"><span data-stu-id="44658-178">optional</span></span>  <br/> |<span data-ttu-id="44658-179">指向**MasterShortcut**元素的 URL。</span><span class="sxs-lookup"><span data-stu-id="44658-179">A URL to a **MasterShortcut** element.</span></span>  <br/> |<span data-ttu-id="44658-180">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44658-180">Values of the xsd:string type.</span></span>  <br/> |
   

