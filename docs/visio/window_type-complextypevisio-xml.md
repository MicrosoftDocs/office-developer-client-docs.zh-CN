---
title: Window_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c514ce79-0920-4f1b-5332-0bdef146e802
ms.openlocfilehash: dc4dda48c037f7af03ee22a07bee288ce5d30872
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781662"
---
# <a name="windowtype-complextype-visio-xml"></a><span data-ttu-id="80626-102">Window_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="80626-102">Window_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="80626-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="80626-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="80626-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="80626-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="80626-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="80626-105">**Schema file**</span></span> <br/> |<span data-ttu-id="80626-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="80626-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="80626-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="80626-107">**Extension base**</span></span> <br/> |<span data-ttu-id="80626-108">无</span><span class="sxs-lookup"><span data-stu-id="80626-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="80626-109">定义</span><span class="sxs-lookup"><span data-stu-id="80626-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="80626-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="80626-110">Elements and attributes</span></span>

<span data-ttu-id="80626-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="80626-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="80626-112">子元素</span><span class="sxs-lookup"><span data-stu-id="80626-112">Child elements</span></span>

|<span data-ttu-id="80626-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="80626-113">**Element**</span></span>|<span data-ttu-id="80626-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="80626-114">**Type**</span></span>|<span data-ttu-id="80626-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="80626-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="80626-116">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="80626-116">DynamicGridEnabled</span></span>](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-117">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="80626-117">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-118">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="80626-118">GlueSettings</span></span>](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-119">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="80626-119">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-120">ShowConnectionPoints</span><span class="sxs-lookup"><span data-stu-id="80626-120">ShowConnectionPoints</span></span>](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-121">ShowConnectionPoints_Type</span><span class="sxs-lookup"><span data-stu-id="80626-121">ShowConnectionPoints_Type</span></span>](showconnectionpoints_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-122">ShowGrid</span><span class="sxs-lookup"><span data-stu-id="80626-122">ShowGrid</span></span>](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-123">ShowGrid_Type</span><span class="sxs-lookup"><span data-stu-id="80626-123">ShowGrid_Type</span></span>](showgrid_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-124">ShowGuides</span><span class="sxs-lookup"><span data-stu-id="80626-124">ShowGuides</span></span>](showguides-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-125">ShowGuides_Type</span><span class="sxs-lookup"><span data-stu-id="80626-125">ShowGuides_Type</span></span>](showguides_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-126">ShowPageBreaks</span><span class="sxs-lookup"><span data-stu-id="80626-126">ShowPageBreaks</span></span>](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-127">ShowPageBreaks_Type</span><span class="sxs-lookup"><span data-stu-id="80626-127">ShowPageBreaks_Type</span></span>](showpagebreaks_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-128">ShowRulers</span><span class="sxs-lookup"><span data-stu-id="80626-128">ShowRulers</span></span>](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-129">ShowRulers_Type</span><span class="sxs-lookup"><span data-stu-id="80626-129">ShowRulers_Type</span></span>](showrulers_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-130">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="80626-130">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-131">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="80626-131">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-132">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="80626-132">SnapExtensions</span></span>](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-133">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="80626-133">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-134">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="80626-134">SnapSettings</span></span>](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-135">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="80626-135">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-136">StencilGroup</span><span class="sxs-lookup"><span data-stu-id="80626-136">StencilGroup</span></span>](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-137">StencilGroup_Type</span><span class="sxs-lookup"><span data-stu-id="80626-137">StencilGroup_Type</span></span>](stencilgroup_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-138">StencilGroupPos</span><span class="sxs-lookup"><span data-stu-id="80626-138">StencilGroupPos</span></span>](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-139">StencilGroupPos_Type</span><span class="sxs-lookup"><span data-stu-id="80626-139">StencilGroupPos_Type</span></span>](stencilgrouppos_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="80626-140">TabSplitterPos</span><span class="sxs-lookup"><span data-stu-id="80626-140">TabSplitterPos</span></span>](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="80626-141">TabSplitterPos_Type</span><span class="sxs-lookup"><span data-stu-id="80626-141">TabSplitterPos_Type</span></span>](tabsplitterpos_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="80626-142">Attributes</span><span class="sxs-lookup"><span data-stu-id="80626-142">Attributes</span></span>

|<span data-ttu-id="80626-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="80626-143">**Attribute**</span></span>|<span data-ttu-id="80626-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="80626-144">**Type**</span></span>|<span data-ttu-id="80626-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="80626-145">**Required**</span></span>|<span data-ttu-id="80626-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="80626-146">**Description**</span></span>|<span data-ttu-id="80626-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="80626-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80626-148">Container</span><span class="sxs-lookup"><span data-stu-id="80626-148">Container</span></span>  <br/> |<span data-ttu-id="80626-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-150">可选</span><span class="sxs-lookup"><span data-stu-id="80626-150">optional</span></span>  <br/> ||<span data-ttu-id="80626-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-152">ContainerType</span><span class="sxs-lookup"><span data-stu-id="80626-152">ContainerType</span></span>  <br/> |<span data-ttu-id="80626-153">xsd:token</span><span class="sxs-lookup"><span data-stu-id="80626-153">xsd:token</span></span>  <br/> |<span data-ttu-id="80626-154">可选</span><span class="sxs-lookup"><span data-stu-id="80626-154">optional</span></span>  <br/> ||<span data-ttu-id="80626-155">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-155">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="80626-156">文档</span><span class="sxs-lookup"><span data-stu-id="80626-156">Document</span></span>  <br/> |<span data-ttu-id="80626-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="80626-157">xsd:string</span></span>  <br/> |<span data-ttu-id="80626-158">可选</span><span class="sxs-lookup"><span data-stu-id="80626-158">optional</span></span>  <br/> ||<span data-ttu-id="80626-159">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-159">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="80626-160">ID</span><span class="sxs-lookup"><span data-stu-id="80626-160">ID</span></span>  <br/> |<span data-ttu-id="80626-161">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-161">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-162">必需</span><span class="sxs-lookup"><span data-stu-id="80626-162">required</span></span>  <br/> ||<span data-ttu-id="80626-163">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-164">Master</span><span class="sxs-lookup"><span data-stu-id="80626-164">Master</span></span>  <br/> |<span data-ttu-id="80626-165">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-165">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-166">可选</span><span class="sxs-lookup"><span data-stu-id="80626-166">optional</span></span>  <br/> ||<span data-ttu-id="80626-167">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-168">Page</span><span class="sxs-lookup"><span data-stu-id="80626-168">Page</span></span>  <br/> |<span data-ttu-id="80626-169">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-169">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-170">可选</span><span class="sxs-lookup"><span data-stu-id="80626-170">optional</span></span>  <br/> ||<span data-ttu-id="80626-171">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-171">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-172">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="80626-172">ParentWindow</span></span>  <br/> |<span data-ttu-id="80626-173">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-173">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-174">可选</span><span class="sxs-lookup"><span data-stu-id="80626-174">optional</span></span>  <br/> ||<span data-ttu-id="80626-175">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-175">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-176">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="80626-176">ReadOnly</span></span>  <br/> |<span data-ttu-id="80626-177">化</span><span class="sxs-lookup"><span data-stu-id="80626-177">xsd:boolean</span></span>  <br/> |<span data-ttu-id="80626-178">可选</span><span class="sxs-lookup"><span data-stu-id="80626-178">optional</span></span>  <br/> ||<span data-ttu-id="80626-179">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-179">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="80626-180">工作表</span><span class="sxs-lookup"><span data-stu-id="80626-180">Sheet</span></span>  <br/> |<span data-ttu-id="80626-181">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-181">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-182">可选</span><span class="sxs-lookup"><span data-stu-id="80626-182">optional</span></span>  <br/> ||<span data-ttu-id="80626-183">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-183">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-184">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="80626-184">ViewCenterX</span></span>  <br/> |<span data-ttu-id="80626-185">化</span><span class="sxs-lookup"><span data-stu-id="80626-185">xsd:double</span></span>  <br/> |<span data-ttu-id="80626-186">可选</span><span class="sxs-lookup"><span data-stu-id="80626-186">optional</span></span>  <br/> ||<span data-ttu-id="80626-187">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-187">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="80626-188">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="80626-188">ViewCenterY</span></span>  <br/> |<span data-ttu-id="80626-189">化</span><span class="sxs-lookup"><span data-stu-id="80626-189">xsd:double</span></span>  <br/> |<span data-ttu-id="80626-190">可选</span><span class="sxs-lookup"><span data-stu-id="80626-190">optional</span></span>  <br/> ||<span data-ttu-id="80626-191">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-191">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="80626-192">ViewScale</span><span class="sxs-lookup"><span data-stu-id="80626-192">ViewScale</span></span>  <br/> |<span data-ttu-id="80626-193">化</span><span class="sxs-lookup"><span data-stu-id="80626-193">xsd:double</span></span>  <br/> |<span data-ttu-id="80626-194">可选</span><span class="sxs-lookup"><span data-stu-id="80626-194">optional</span></span>  <br/> ||<span data-ttu-id="80626-195">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-195">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="80626-196">WindowHeight</span><span class="sxs-lookup"><span data-stu-id="80626-196">WindowHeight</span></span>  <br/> |<span data-ttu-id="80626-197">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-197">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-198">可选</span><span class="sxs-lookup"><span data-stu-id="80626-198">optional</span></span>  <br/> ||<span data-ttu-id="80626-199">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-199">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-200">WindowLeft</span><span class="sxs-lookup"><span data-stu-id="80626-200">WindowLeft</span></span>  <br/> |<span data-ttu-id="80626-201">xsd:short</span><span class="sxs-lookup"><span data-stu-id="80626-201">xsd:short</span></span>  <br/> |<span data-ttu-id="80626-202">可选</span><span class="sxs-lookup"><span data-stu-id="80626-202">optional</span></span>  <br/> ||<span data-ttu-id="80626-203">Xsd:short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-203">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="80626-204">WindowState</span><span class="sxs-lookup"><span data-stu-id="80626-204">WindowState</span></span>  <br/> |<span data-ttu-id="80626-205">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-205">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-206">可选</span><span class="sxs-lookup"><span data-stu-id="80626-206">optional</span></span>  <br/> ||<span data-ttu-id="80626-207">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-207">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="80626-208">WindowTop</span><span class="sxs-lookup"><span data-stu-id="80626-208">WindowTop</span></span>  <br/> |<span data-ttu-id="80626-209">xsd:short</span><span class="sxs-lookup"><span data-stu-id="80626-209">xsd:short</span></span>  <br/> |<span data-ttu-id="80626-210">可选</span><span class="sxs-lookup"><span data-stu-id="80626-210">optional</span></span>  <br/> ||<span data-ttu-id="80626-211">Xsd:short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-211">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="80626-212">WindowType</span><span class="sxs-lookup"><span data-stu-id="80626-212">WindowType</span></span>  <br/> |<span data-ttu-id="80626-213">xsd:token</span><span class="sxs-lookup"><span data-stu-id="80626-213">xsd:token</span></span>  <br/> |<span data-ttu-id="80626-214">必需</span><span class="sxs-lookup"><span data-stu-id="80626-214">required</span></span>  <br/> ||<span data-ttu-id="80626-215">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-215">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="80626-216">WindowWidth</span><span class="sxs-lookup"><span data-stu-id="80626-216">WindowWidth</span></span>  <br/> |<span data-ttu-id="80626-217">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="80626-217">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="80626-218">可选</span><span class="sxs-lookup"><span data-stu-id="80626-218">optional</span></span>  <br/> ||<span data-ttu-id="80626-219">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="80626-219">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

