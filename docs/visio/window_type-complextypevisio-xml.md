---
title: Window_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c514ce79-0920-4f1b-5332-0bdef146e802
ms.openlocfilehash: 340326213de4029201d21e627ed4b27c53b33d1e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339926"
---
# <a name="windowtype-complextype-visio-xml"></a><span data-ttu-id="b346a-102">Window_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b346a-102">Window_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b346a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b346a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b346a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b346a-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b346a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b346a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b346a-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b346a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b346a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b346a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b346a-108">无</span><span class="sxs-lookup"><span data-stu-id="b346a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b346a-109">定义</span><span class="sxs-lookup"><span data-stu-id="b346a-109">Definition</span></span>

```XML
          <xs:complexType name="Window_Type">
          
          <xs:sequence>
    <xs:element name="StencilGroup"  type="StencilGroup_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="StencilGroupPos"  type="StencilGroupPos_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ShowRulers"  type="ShowRulers_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ShowGrid"  type="ShowGrid_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ShowPageBreaks"  type="ShowPageBreaks_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ShowGuides"  type="ShowGuides_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ShowConnectionPoints"  type="ShowConnectionPoints_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="GlueSettings"  type="GlueSettings_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="SnapSettings"  type="SnapSettings_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="SnapExtensions"  type="SnapExtensions_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="SnapAngles"  type="SnapAngles_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="DynamicGridEnabled"  type="DynamicGridEnabled_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="TabSplitterPos"  type="TabSplitterPos_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="WindowType"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="WindowState"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Document"
  type="xsd:string"
    />
    <xs:attribute name="WindowLeft"
  type="xsd:short"
    />
    <xs:attribute name="WindowTop"
  type="xsd:short"
    />
    <xs:attribute name="WindowWidth"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="WindowHeight"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Master"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ContainerType"
  type="xsd:token"
    />
    <xs:attribute name="Container"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Sheet"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ReadOnly"
  type="xsd:boolean"
    />
    <xs:attribute name="ParentWindow"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Page"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ViewScale"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterX"
  type="xsd:double"
    />
    <xs:attribute name="ViewCenterY"
  type="xsd:double"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b346a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b346a-110">Elements and attributes</span></span>

<span data-ttu-id="b346a-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b346a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b346a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b346a-112">Child elements</span></span>

|<span data-ttu-id="b346a-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b346a-113">**Element**</span></span>|<span data-ttu-id="b346a-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b346a-114">**Type**</span></span>|<span data-ttu-id="b346a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b346a-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b346a-116">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="b346a-116">DynamicGridEnabled</span></span>](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-117">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-117">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-118">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="b346a-118">GlueSettings</span></span>](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-119">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-119">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-120">ShowConnectionPoints</span><span class="sxs-lookup"><span data-stu-id="b346a-120">ShowConnectionPoints</span></span>](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-121">ShowConnectionPoints_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-121">ShowConnectionPoints_Type</span></span>](showconnectionpoints_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-122">ShowGrid</span><span class="sxs-lookup"><span data-stu-id="b346a-122">ShowGrid</span></span>](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-123">ShowGrid_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-123">ShowGrid_Type</span></span>](showgrid_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-124">ShowGuides</span><span class="sxs-lookup"><span data-stu-id="b346a-124">ShowGuides</span></span>](showguides-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-125">ShowGuides_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-125">ShowGuides_Type</span></span>](showguides_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-126">ShowPageBreaks</span><span class="sxs-lookup"><span data-stu-id="b346a-126">ShowPageBreaks</span></span>](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-127">ShowPageBreaks_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-127">ShowPageBreaks_Type</span></span>](showpagebreaks_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-128">ShowRulers</span><span class="sxs-lookup"><span data-stu-id="b346a-128">ShowRulers</span></span>](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-129">ShowRulers_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-129">ShowRulers_Type</span></span>](showrulers_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-130">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="b346a-130">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-131">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-131">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-132">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="b346a-132">SnapExtensions</span></span>](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-133">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-133">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-134">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="b346a-134">SnapSettings</span></span>](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-135">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-135">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-136">StencilGroup</span><span class="sxs-lookup"><span data-stu-id="b346a-136">StencilGroup</span></span>](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-137">StencilGroup_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-137">StencilGroup_Type</span></span>](stencilgroup_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-138">StencilGroupPos</span><span class="sxs-lookup"><span data-stu-id="b346a-138">StencilGroupPos</span></span>](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-139">StencilGroupPos_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-139">StencilGroupPos_Type</span></span>](stencilgrouppos_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b346a-140">TabSplitterPos</span><span class="sxs-lookup"><span data-stu-id="b346a-140">TabSplitterPos</span></span>](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b346a-141">TabSplitterPos_Type</span><span class="sxs-lookup"><span data-stu-id="b346a-141">TabSplitterPos_Type</span></span>](tabsplitterpos_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b346a-142">属性</span><span class="sxs-lookup"><span data-stu-id="b346a-142">Attributes</span></span>

|<span data-ttu-id="b346a-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="b346a-143">**Attribute**</span></span>|<span data-ttu-id="b346a-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="b346a-144">**Type**</span></span>|<span data-ttu-id="b346a-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="b346a-145">**Required**</span></span>|<span data-ttu-id="b346a-146">**描述**</span><span class="sxs-lookup"><span data-stu-id="b346a-146">**Description**</span></span>|<span data-ttu-id="b346a-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b346a-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b346a-148">Container</span><span class="sxs-lookup"><span data-stu-id="b346a-148">Container</span></span>  <br/> |<span data-ttu-id="b346a-149">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-150">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-150">optional</span></span>  <br/> ||<span data-ttu-id="b346a-151">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-152">ContainerType</span><span class="sxs-lookup"><span data-stu-id="b346a-152">ContainerType</span></span>  <br/> |<span data-ttu-id="b346a-153">xsd: token</span><span class="sxs-lookup"><span data-stu-id="b346a-153">xsd:token</span></span>  <br/> |<span data-ttu-id="b346a-154">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-154">optional</span></span>  <br/> ||<span data-ttu-id="b346a-155">xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-155">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="b346a-156">Document</span><span class="sxs-lookup"><span data-stu-id="b346a-156">Document</span></span>  <br/> |<span data-ttu-id="b346a-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b346a-157">xsd:string</span></span>  <br/> |<span data-ttu-id="b346a-158">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-158">optional</span></span>  <br/> ||<span data-ttu-id="b346a-159">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-159">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b346a-160">ID</span><span class="sxs-lookup"><span data-stu-id="b346a-160">ID</span></span>  <br/> |<span data-ttu-id="b346a-161">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-161">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-162">必需</span><span class="sxs-lookup"><span data-stu-id="b346a-162">required</span></span>  <br/> ||<span data-ttu-id="b346a-163">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-164">Master</span><span class="sxs-lookup"><span data-stu-id="b346a-164">Master</span></span>  <br/> |<span data-ttu-id="b346a-165">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-165">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-166">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-166">optional</span></span>  <br/> ||<span data-ttu-id="b346a-167">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-168">Page</span><span class="sxs-lookup"><span data-stu-id="b346a-168">Page</span></span>  <br/> |<span data-ttu-id="b346a-169">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-169">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-170">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-170">optional</span></span>  <br/> ||<span data-ttu-id="b346a-171">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-171">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-172">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="b346a-172">ParentWindow</span></span>  <br/> |<span data-ttu-id="b346a-173">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-173">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-174">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-174">optional</span></span>  <br/> ||<span data-ttu-id="b346a-175">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-175">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-176">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="b346a-176">ReadOnly</span></span>  <br/> |<span data-ttu-id="b346a-177">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="b346a-177">xsd:boolean</span></span>  <br/> |<span data-ttu-id="b346a-178">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-178">optional</span></span>  <br/> ||<span data-ttu-id="b346a-179">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-179">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="b346a-180">Sheet</span><span class="sxs-lookup"><span data-stu-id="b346a-180">Sheet</span></span>  <br/> |<span data-ttu-id="b346a-181">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-181">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-182">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-182">optional</span></span>  <br/> ||<span data-ttu-id="b346a-183">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-183">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-184">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="b346a-184">ViewCenterX</span></span>  <br/> |<span data-ttu-id="b346a-185">xsd: double</span><span class="sxs-lookup"><span data-stu-id="b346a-185">xsd:double</span></span>  <br/> |<span data-ttu-id="b346a-186">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-186">optional</span></span>  <br/> ||<span data-ttu-id="b346a-187">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-187">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="b346a-188">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="b346a-188">ViewCenterY</span></span>  <br/> |<span data-ttu-id="b346a-189">xsd: double</span><span class="sxs-lookup"><span data-stu-id="b346a-189">xsd:double</span></span>  <br/> |<span data-ttu-id="b346a-190">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-190">optional</span></span>  <br/> ||<span data-ttu-id="b346a-191">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-191">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="b346a-192">ViewScale</span><span class="sxs-lookup"><span data-stu-id="b346a-192">ViewScale</span></span>  <br/> |<span data-ttu-id="b346a-193">xsd: double</span><span class="sxs-lookup"><span data-stu-id="b346a-193">xsd:double</span></span>  <br/> |<span data-ttu-id="b346a-194">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-194">optional</span></span>  <br/> ||<span data-ttu-id="b346a-195">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-195">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="b346a-196">WindowHeight</span><span class="sxs-lookup"><span data-stu-id="b346a-196">WindowHeight</span></span>  <br/> |<span data-ttu-id="b346a-197">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-197">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-198">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-198">optional</span></span>  <br/> ||<span data-ttu-id="b346a-199">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-199">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-200">WindowLeft</span><span class="sxs-lookup"><span data-stu-id="b346a-200">WindowLeft</span></span>  <br/> |<span data-ttu-id="b346a-201">xsd: short</span><span class="sxs-lookup"><span data-stu-id="b346a-201">xsd:short</span></span>  <br/> |<span data-ttu-id="b346a-202">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-202">optional</span></span>  <br/> ||<span data-ttu-id="b346a-203">xsd: short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-203">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="b346a-204">WindowState</span><span class="sxs-lookup"><span data-stu-id="b346a-204">WindowState</span></span>  <br/> |<span data-ttu-id="b346a-205">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-205">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-206">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-206">optional</span></span>  <br/> ||<span data-ttu-id="b346a-207">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-207">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b346a-208">WindowTop</span><span class="sxs-lookup"><span data-stu-id="b346a-208">WindowTop</span></span>  <br/> |<span data-ttu-id="b346a-209">xsd: short</span><span class="sxs-lookup"><span data-stu-id="b346a-209">xsd:short</span></span>  <br/> |<span data-ttu-id="b346a-210">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-210">optional</span></span>  <br/> ||<span data-ttu-id="b346a-211">xsd: short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-211">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="b346a-212">WindowType</span><span class="sxs-lookup"><span data-stu-id="b346a-212">WindowType</span></span>  <br/> |<span data-ttu-id="b346a-213">xsd: token</span><span class="sxs-lookup"><span data-stu-id="b346a-213">xsd:token</span></span>  <br/> |<span data-ttu-id="b346a-214">必需</span><span class="sxs-lookup"><span data-stu-id="b346a-214">required</span></span>  <br/> ||<span data-ttu-id="b346a-215">xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-215">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="b346a-216">WindowWidth</span><span class="sxs-lookup"><span data-stu-id="b346a-216">WindowWidth</span></span>  <br/> |<span data-ttu-id="b346a-217">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b346a-217">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b346a-218">可选</span><span class="sxs-lookup"><span data-stu-id="b346a-218">optional</span></span>  <br/> ||<span data-ttu-id="b346a-219">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b346a-219">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

