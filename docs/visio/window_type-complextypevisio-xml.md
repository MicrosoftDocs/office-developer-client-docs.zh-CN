---
title: 'Window_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c514ce79-0920-4f1b-5332-0bdef146e802
ms.openlocfilehash: 08b65a5f0e108c5503e29c7e195d681d0a343521
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538450"
---
# <a name="window_type-complextype-visio-xml"></a><span data-ttu-id="d7841-102">Window_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="d7841-102">Window_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="d7841-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d7841-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d7841-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d7841-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d7841-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d7841-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d7841-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="d7841-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d7841-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d7841-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d7841-108">无</span><span class="sxs-lookup"><span data-stu-id="d7841-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d7841-109">定义</span><span class="sxs-lookup"><span data-stu-id="d7841-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d7841-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d7841-110">Elements and attributes</span></span>

<span data-ttu-id="d7841-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d7841-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d7841-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d7841-112">Child elements</span></span>

|<span data-ttu-id="d7841-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="d7841-113">**Element**</span></span>|<span data-ttu-id="d7841-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7841-114">**Type**</span></span>|<span data-ttu-id="d7841-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7841-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d7841-116">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="d7841-116">DynamicGridEnabled</span></span>](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-117">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-117">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-118">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="d7841-118">GlueSettings</span></span>](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-119">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-119">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-120">ShowConnectionPoints</span><span class="sxs-lookup"><span data-stu-id="d7841-120">ShowConnectionPoints</span></span>](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-121">ShowConnectionPoints_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-121">ShowConnectionPoints_Type</span></span>](showconnectionpoints_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-122">ShowGrid</span><span class="sxs-lookup"><span data-stu-id="d7841-122">ShowGrid</span></span>](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-123">ShowGrid_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-123">ShowGrid_Type</span></span>](showgrid_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-124">ShowGuides</span><span class="sxs-lookup"><span data-stu-id="d7841-124">ShowGuides</span></span>](showguides-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-125">ShowGuides_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-125">ShowGuides_Type</span></span>](showguides_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-126">ShowPageBreaks</span><span class="sxs-lookup"><span data-stu-id="d7841-126">ShowPageBreaks</span></span>](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-127">ShowPageBreaks_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-127">ShowPageBreaks_Type</span></span>](showpagebreaks_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-128">ShowRulers</span><span class="sxs-lookup"><span data-stu-id="d7841-128">ShowRulers</span></span>](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-129">ShowRulers_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-129">ShowRulers_Type</span></span>](showrulers_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-130">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="d7841-130">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-131">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-131">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-132">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="d7841-132">SnapExtensions</span></span>](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-133">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-133">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-134">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="d7841-134">SnapSettings</span></span>](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-135">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-135">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-136">StencilGroup</span><span class="sxs-lookup"><span data-stu-id="d7841-136">StencilGroup</span></span>](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-137">StencilGroup_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-137">StencilGroup_Type</span></span>](stencilgroup_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-138">StencilGroupPos</span><span class="sxs-lookup"><span data-stu-id="d7841-138">StencilGroupPos</span></span>](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-139">StencilGroupPos_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-139">StencilGroupPos_Type</span></span>](stencilgrouppos_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="d7841-140">TabSplitterPos</span><span class="sxs-lookup"><span data-stu-id="d7841-140">TabSplitterPos</span></span>](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7841-141">TabSplitterPos_Type</span><span class="sxs-lookup"><span data-stu-id="d7841-141">TabSplitterPos_Type</span></span>](tabsplitterpos_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="d7841-142">属性</span><span class="sxs-lookup"><span data-stu-id="d7841-142">Attributes</span></span>

|<span data-ttu-id="d7841-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="d7841-143">**Attribute**</span></span>|<span data-ttu-id="d7841-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7841-144">**Type**</span></span>|<span data-ttu-id="d7841-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="d7841-145">**Required**</span></span>|<span data-ttu-id="d7841-146">**描述**</span><span class="sxs-lookup"><span data-stu-id="d7841-146">**Description**</span></span>|<span data-ttu-id="d7841-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d7841-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7841-148">容器</span><span class="sxs-lookup"><span data-stu-id="d7841-148">Container</span></span>  <br/> |<span data-ttu-id="d7841-149">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-150">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-150">optional</span></span>  <br/> ||<span data-ttu-id="d7841-151">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-152">ContainerType</span><span class="sxs-lookup"><span data-stu-id="d7841-152">ContainerType</span></span>  <br/> |<span data-ttu-id="d7841-153">xsd：token</span><span class="sxs-lookup"><span data-stu-id="d7841-153">xsd:token</span></span>  <br/> |<span data-ttu-id="d7841-154">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-154">optional</span></span>  <br/> ||<span data-ttu-id="d7841-155">xsd：token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-155">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="d7841-156">文档</span><span class="sxs-lookup"><span data-stu-id="d7841-156">Document</span></span>  <br/> |<span data-ttu-id="d7841-157">xsd：string</span><span class="sxs-lookup"><span data-stu-id="d7841-157">xsd:string</span></span>  <br/> |<span data-ttu-id="d7841-158">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-158">optional</span></span>  <br/> ||<span data-ttu-id="d7841-159">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-159">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d7841-160">ID</span><span class="sxs-lookup"><span data-stu-id="d7841-160">ID</span></span>  <br/> |<span data-ttu-id="d7841-161">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-161">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-162">必需</span><span class="sxs-lookup"><span data-stu-id="d7841-162">required</span></span>  <br/> ||<span data-ttu-id="d7841-163">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-164">Master</span><span class="sxs-lookup"><span data-stu-id="d7841-164">Master</span></span>  <br/> |<span data-ttu-id="d7841-165">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-165">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-166">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-166">optional</span></span>  <br/> ||<span data-ttu-id="d7841-167">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-168">Page</span><span class="sxs-lookup"><span data-stu-id="d7841-168">Page</span></span>  <br/> |<span data-ttu-id="d7841-169">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-169">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-170">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-170">optional</span></span>  <br/> ||<span data-ttu-id="d7841-171">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-171">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-172">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="d7841-172">ParentWindow</span></span>  <br/> |<span data-ttu-id="d7841-173">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-173">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-174">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-174">optional</span></span>  <br/> ||<span data-ttu-id="d7841-175">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-175">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-176">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="d7841-176">ReadOnly</span></span>  <br/> |<span data-ttu-id="d7841-177">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="d7841-177">xsd:boolean</span></span>  <br/> |<span data-ttu-id="d7841-178">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-178">optional</span></span>  <br/> ||<span data-ttu-id="d7841-179">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-179">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="d7841-180">Sheet</span><span class="sxs-lookup"><span data-stu-id="d7841-180">Sheet</span></span>  <br/> |<span data-ttu-id="d7841-181">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-181">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-182">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-182">optional</span></span>  <br/> ||<span data-ttu-id="d7841-183">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-183">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-184">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="d7841-184">ViewCenterX</span></span>  <br/> |<span data-ttu-id="d7841-185">xsd：double</span><span class="sxs-lookup"><span data-stu-id="d7841-185">xsd:double</span></span>  <br/> |<span data-ttu-id="d7841-186">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-186">optional</span></span>  <br/> ||<span data-ttu-id="d7841-187">xsd：double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-187">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="d7841-188">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="d7841-188">ViewCenterY</span></span>  <br/> |<span data-ttu-id="d7841-189">xsd：double</span><span class="sxs-lookup"><span data-stu-id="d7841-189">xsd:double</span></span>  <br/> |<span data-ttu-id="d7841-190">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-190">optional</span></span>  <br/> ||<span data-ttu-id="d7841-191">xsd：double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-191">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="d7841-192">ViewScale</span><span class="sxs-lookup"><span data-stu-id="d7841-192">ViewScale</span></span>  <br/> |<span data-ttu-id="d7841-193">xsd：double</span><span class="sxs-lookup"><span data-stu-id="d7841-193">xsd:double</span></span>  <br/> |<span data-ttu-id="d7841-194">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-194">optional</span></span>  <br/> ||<span data-ttu-id="d7841-195">xsd：double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-195">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="d7841-196">WindowHeight</span><span class="sxs-lookup"><span data-stu-id="d7841-196">WindowHeight</span></span>  <br/> |<span data-ttu-id="d7841-197">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-197">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-198">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-198">optional</span></span>  <br/> ||<span data-ttu-id="d7841-199">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-199">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-200">WindowLeft</span><span class="sxs-lookup"><span data-stu-id="d7841-200">WindowLeft</span></span>  <br/> |<span data-ttu-id="d7841-201">xsd：short</span><span class="sxs-lookup"><span data-stu-id="d7841-201">xsd:short</span></span>  <br/> |<span data-ttu-id="d7841-202">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-202">optional</span></span>  <br/> ||<span data-ttu-id="d7841-203">xsd：short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-203">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="d7841-204">WindowState</span><span class="sxs-lookup"><span data-stu-id="d7841-204">WindowState</span></span>  <br/> |<span data-ttu-id="d7841-205">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-205">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-206">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-206">optional</span></span>  <br/> ||<span data-ttu-id="d7841-207">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-207">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7841-208">WindowTop</span><span class="sxs-lookup"><span data-stu-id="d7841-208">WindowTop</span></span>  <br/> |<span data-ttu-id="d7841-209">xsd：short</span><span class="sxs-lookup"><span data-stu-id="d7841-209">xsd:short</span></span>  <br/> |<span data-ttu-id="d7841-210">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-210">optional</span></span>  <br/> ||<span data-ttu-id="d7841-211">xsd：short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-211">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="d7841-212">WindowType</span><span class="sxs-lookup"><span data-stu-id="d7841-212">WindowType</span></span>  <br/> |<span data-ttu-id="d7841-213">xsd：token</span><span class="sxs-lookup"><span data-stu-id="d7841-213">xsd:token</span></span>  <br/> |<span data-ttu-id="d7841-214">必需</span><span class="sxs-lookup"><span data-stu-id="d7841-214">required</span></span>  <br/> ||<span data-ttu-id="d7841-215">xsd：token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-215">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="d7841-216">WindowWidth</span><span class="sxs-lookup"><span data-stu-id="d7841-216">WindowWidth</span></span>  <br/> |<span data-ttu-id="d7841-217">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7841-217">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7841-218">可选</span><span class="sxs-lookup"><span data-stu-id="d7841-218">optional</span></span>  <br/> ||<span data-ttu-id="d7841-219">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7841-219">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

