---
title: Window_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c514ce79-0920-4f1b-5332-0bdef146e802
ms.openlocfilehash: 340326213de4029201d21e627ed4b27c53b33d1e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400584"
---
# <a name="windowtype-complextype-visio-xml"></a><span data-ttu-id="244ee-102">Window_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="244ee-102">Window_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="244ee-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="244ee-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="244ee-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="244ee-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="244ee-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="244ee-105">**Schema file**</span></span> <br/> |<span data-ttu-id="244ee-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="244ee-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="244ee-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="244ee-107">**Extension base**</span></span> <br/> |<span data-ttu-id="244ee-108">无</span><span class="sxs-lookup"><span data-stu-id="244ee-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="244ee-109">定义</span><span class="sxs-lookup"><span data-stu-id="244ee-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="244ee-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="244ee-110">Elements and attributes</span></span>

<span data-ttu-id="244ee-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="244ee-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="244ee-112">子元素</span><span class="sxs-lookup"><span data-stu-id="244ee-112">Child elements</span></span>

|<span data-ttu-id="244ee-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="244ee-113">**Element**</span></span>|<span data-ttu-id="244ee-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="244ee-114">**Type**</span></span>|<span data-ttu-id="244ee-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="244ee-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="244ee-116">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="244ee-116">DynamicGridEnabled</span></span>](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-117">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-117">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-118">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="244ee-118">GlueSettings</span></span>](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-119">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-119">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-120">ShowConnectionPoints</span><span class="sxs-lookup"><span data-stu-id="244ee-120">ShowConnectionPoints</span></span>](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-121">ShowConnectionPoints_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-121">ShowConnectionPoints_Type</span></span>](showconnectionpoints_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-122">ShowGrid</span><span class="sxs-lookup"><span data-stu-id="244ee-122">ShowGrid</span></span>](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-123">ShowGrid_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-123">ShowGrid_Type</span></span>](showgrid_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-124">ShowGuides</span><span class="sxs-lookup"><span data-stu-id="244ee-124">ShowGuides</span></span>](showguides-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-125">ShowGuides_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-125">ShowGuides_Type</span></span>](showguides_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-126">ShowPageBreaks</span><span class="sxs-lookup"><span data-stu-id="244ee-126">ShowPageBreaks</span></span>](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-127">ShowPageBreaks_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-127">ShowPageBreaks_Type</span></span>](showpagebreaks_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-128">ShowRulers</span><span class="sxs-lookup"><span data-stu-id="244ee-128">ShowRulers</span></span>](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-129">ShowRulers_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-129">ShowRulers_Type</span></span>](showrulers_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-130">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="244ee-130">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-131">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-131">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-132">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="244ee-132">SnapExtensions</span></span>](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-133">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-133">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-134">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="244ee-134">SnapSettings</span></span>](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-135">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-135">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-136">StencilGroup</span><span class="sxs-lookup"><span data-stu-id="244ee-136">StencilGroup</span></span>](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-137">StencilGroup_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-137">StencilGroup_Type</span></span>](stencilgroup_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-138">StencilGroupPos</span><span class="sxs-lookup"><span data-stu-id="244ee-138">StencilGroupPos</span></span>](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-139">StencilGroupPos_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-139">StencilGroupPos_Type</span></span>](stencilgrouppos_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="244ee-140">TabSplitterPos</span><span class="sxs-lookup"><span data-stu-id="244ee-140">TabSplitterPos</span></span>](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="244ee-141">TabSplitterPos_Type</span><span class="sxs-lookup"><span data-stu-id="244ee-141">TabSplitterPos_Type</span></span>](tabsplitterpos_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="244ee-142">Attributes</span><span class="sxs-lookup"><span data-stu-id="244ee-142">Attributes</span></span>

|<span data-ttu-id="244ee-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="244ee-143">**Attribute**</span></span>|<span data-ttu-id="244ee-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="244ee-144">**Type**</span></span>|<span data-ttu-id="244ee-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="244ee-145">**Required**</span></span>|<span data-ttu-id="244ee-146">**说明**</span><span class="sxs-lookup"><span data-stu-id="244ee-146">**Description**</span></span>|<span data-ttu-id="244ee-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="244ee-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="244ee-148">Container</span><span class="sxs-lookup"><span data-stu-id="244ee-148">Container</span></span>  <br/> |<span data-ttu-id="244ee-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-150">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-150">optional</span></span>  <br/> ||<span data-ttu-id="244ee-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-152">ContainerType</span><span class="sxs-lookup"><span data-stu-id="244ee-152">ContainerType</span></span>  <br/> |<span data-ttu-id="244ee-153">xsd:token</span><span class="sxs-lookup"><span data-stu-id="244ee-153">xsd:token</span></span>  <br/> |<span data-ttu-id="244ee-154">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-154">optional</span></span>  <br/> ||<span data-ttu-id="244ee-155">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-155">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="244ee-156">文档</span><span class="sxs-lookup"><span data-stu-id="244ee-156">Document</span></span>  <br/> |<span data-ttu-id="244ee-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="244ee-157">xsd:string</span></span>  <br/> |<span data-ttu-id="244ee-158">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-158">optional</span></span>  <br/> ||<span data-ttu-id="244ee-159">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-159">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="244ee-160">ID</span><span class="sxs-lookup"><span data-stu-id="244ee-160">ID</span></span>  <br/> |<span data-ttu-id="244ee-161">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-161">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-162">必需</span><span class="sxs-lookup"><span data-stu-id="244ee-162">required</span></span>  <br/> ||<span data-ttu-id="244ee-163">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-164">Master</span><span class="sxs-lookup"><span data-stu-id="244ee-164">Master</span></span>  <br/> |<span data-ttu-id="244ee-165">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-165">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-166">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-166">optional</span></span>  <br/> ||<span data-ttu-id="244ee-167">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-168">Page</span><span class="sxs-lookup"><span data-stu-id="244ee-168">Page</span></span>  <br/> |<span data-ttu-id="244ee-169">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-169">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-170">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-170">optional</span></span>  <br/> ||<span data-ttu-id="244ee-171">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-171">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-172">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="244ee-172">ParentWindow</span></span>  <br/> |<span data-ttu-id="244ee-173">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-173">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-174">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-174">optional</span></span>  <br/> ||<span data-ttu-id="244ee-175">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-175">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-176">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="244ee-176">ReadOnly</span></span>  <br/> |<span data-ttu-id="244ee-177">化</span><span class="sxs-lookup"><span data-stu-id="244ee-177">xsd:boolean</span></span>  <br/> |<span data-ttu-id="244ee-178">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-178">optional</span></span>  <br/> ||<span data-ttu-id="244ee-179">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-179">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="244ee-180">工作表</span><span class="sxs-lookup"><span data-stu-id="244ee-180">Sheet</span></span>  <br/> |<span data-ttu-id="244ee-181">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-181">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-182">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-182">optional</span></span>  <br/> ||<span data-ttu-id="244ee-183">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-183">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-184">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="244ee-184">ViewCenterX</span></span>  <br/> |<span data-ttu-id="244ee-185">化</span><span class="sxs-lookup"><span data-stu-id="244ee-185">xsd:double</span></span>  <br/> |<span data-ttu-id="244ee-186">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-186">optional</span></span>  <br/> ||<span data-ttu-id="244ee-187">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-187">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="244ee-188">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="244ee-188">ViewCenterY</span></span>  <br/> |<span data-ttu-id="244ee-189">化</span><span class="sxs-lookup"><span data-stu-id="244ee-189">xsd:double</span></span>  <br/> |<span data-ttu-id="244ee-190">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-190">optional</span></span>  <br/> ||<span data-ttu-id="244ee-191">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-191">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="244ee-192">ViewScale</span><span class="sxs-lookup"><span data-stu-id="244ee-192">ViewScale</span></span>  <br/> |<span data-ttu-id="244ee-193">化</span><span class="sxs-lookup"><span data-stu-id="244ee-193">xsd:double</span></span>  <br/> |<span data-ttu-id="244ee-194">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-194">optional</span></span>  <br/> ||<span data-ttu-id="244ee-195">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-195">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="244ee-196">WindowHeight</span><span class="sxs-lookup"><span data-stu-id="244ee-196">WindowHeight</span></span>  <br/> |<span data-ttu-id="244ee-197">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-197">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-198">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-198">optional</span></span>  <br/> ||<span data-ttu-id="244ee-199">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-199">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-200">WindowLeft</span><span class="sxs-lookup"><span data-stu-id="244ee-200">WindowLeft</span></span>  <br/> |<span data-ttu-id="244ee-201">xsd:short</span><span class="sxs-lookup"><span data-stu-id="244ee-201">xsd:short</span></span>  <br/> |<span data-ttu-id="244ee-202">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-202">optional</span></span>  <br/> ||<span data-ttu-id="244ee-203">Xsd:short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-203">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="244ee-204">WindowState</span><span class="sxs-lookup"><span data-stu-id="244ee-204">WindowState</span></span>  <br/> |<span data-ttu-id="244ee-205">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-205">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-206">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-206">optional</span></span>  <br/> ||<span data-ttu-id="244ee-207">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-207">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="244ee-208">WindowTop</span><span class="sxs-lookup"><span data-stu-id="244ee-208">WindowTop</span></span>  <br/> |<span data-ttu-id="244ee-209">xsd:short</span><span class="sxs-lookup"><span data-stu-id="244ee-209">xsd:short</span></span>  <br/> |<span data-ttu-id="244ee-210">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-210">optional</span></span>  <br/> ||<span data-ttu-id="244ee-211">Xsd:short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-211">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="244ee-212">WindowType</span><span class="sxs-lookup"><span data-stu-id="244ee-212">WindowType</span></span>  <br/> |<span data-ttu-id="244ee-213">xsd:token</span><span class="sxs-lookup"><span data-stu-id="244ee-213">xsd:token</span></span>  <br/> |<span data-ttu-id="244ee-214">必需</span><span class="sxs-lookup"><span data-stu-id="244ee-214">required</span></span>  <br/> ||<span data-ttu-id="244ee-215">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-215">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="244ee-216">WindowWidth</span><span class="sxs-lookup"><span data-stu-id="244ee-216">WindowWidth</span></span>  <br/> |<span data-ttu-id="244ee-217">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="244ee-217">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="244ee-218">可选</span><span class="sxs-lookup"><span data-stu-id="244ee-218">optional</span></span>  <br/> ||<span data-ttu-id="244ee-219">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="244ee-219">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

