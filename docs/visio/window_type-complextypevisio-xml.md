---
title: Window_Type 复杂类型 (Visio XML)
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
# <a name="windowtype-complextype-visio-xml"></a><span data-ttu-id="0c83d-102">Window_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0c83d-102">Window_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="0c83d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0c83d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0c83d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0c83d-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0c83d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0c83d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0c83d-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="0c83d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0c83d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0c83d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0c83d-108">无</span><span class="sxs-lookup"><span data-stu-id="0c83d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0c83d-109">定义</span><span class="sxs-lookup"><span data-stu-id="0c83d-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="0c83d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0c83d-110">Elements and attributes</span></span>

<span data-ttu-id="0c83d-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="0c83d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0c83d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0c83d-112">Child elements</span></span>

|<span data-ttu-id="0c83d-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="0c83d-113">**Element**</span></span>|<span data-ttu-id="0c83d-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c83d-114">**Type**</span></span>|<span data-ttu-id="0c83d-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c83d-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0c83d-116">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="0c83d-116">DynamicGridEnabled</span></span>](dynamicgridenabled-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-117">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-117">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-118">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="0c83d-118">GlueSettings</span></span>](gluesettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-119">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-119">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-120">ShowConnectionPoints</span><span class="sxs-lookup"><span data-stu-id="0c83d-120">ShowConnectionPoints</span></span>](showconnectionpoints-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-121">ShowConnectionPoints_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-121">ShowConnectionPoints_Type</span></span>](showconnectionpoints_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-122">ShowGrid</span><span class="sxs-lookup"><span data-stu-id="0c83d-122">ShowGrid</span></span>](showgrid-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-123">ShowGrid_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-123">ShowGrid_Type</span></span>](showgrid_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-124">ShowGuides</span><span class="sxs-lookup"><span data-stu-id="0c83d-124">ShowGuides</span></span>](showguides-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-125">ShowGuides_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-125">ShowGuides_Type</span></span>](showguides_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-126">ShowPageBreaks</span><span class="sxs-lookup"><span data-stu-id="0c83d-126">ShowPageBreaks</span></span>](showpagebreaks-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-127">ShowPageBreaks_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-127">ShowPageBreaks_Type</span></span>](showpagebreaks_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-128">ShowRulers</span><span class="sxs-lookup"><span data-stu-id="0c83d-128">ShowRulers</span></span>](showrulers-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-129">ShowRulers_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-129">ShowRulers_Type</span></span>](showrulers_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-130">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="0c83d-130">SnapAngles</span></span>](snapangles-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-131">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-131">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-132">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="0c83d-132">SnapExtensions</span></span>](snapextensions-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-133">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-133">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-134">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="0c83d-134">SnapSettings</span></span>](snapsettings-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-135">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-135">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-136">StencilGroup</span><span class="sxs-lookup"><span data-stu-id="0c83d-136">StencilGroup</span></span>](stencilgroup-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-137">StencilGroup_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-137">StencilGroup_Type</span></span>](stencilgroup_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-138">StencilGroupPos</span><span class="sxs-lookup"><span data-stu-id="0c83d-138">StencilGroupPos</span></span>](stencilgrouppos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-139">StencilGroupPos_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-139">StencilGroupPos_Type</span></span>](stencilgrouppos_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="0c83d-140">TabSplitterPos</span><span class="sxs-lookup"><span data-stu-id="0c83d-140">TabSplitterPos</span></span>](tabsplitterpos-element-window_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0c83d-141">TabSplitterPos_Type</span><span class="sxs-lookup"><span data-stu-id="0c83d-141">TabSplitterPos_Type</span></span>](tabsplitterpos_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="0c83d-142">属性</span><span class="sxs-lookup"><span data-stu-id="0c83d-142">Attributes</span></span>

|<span data-ttu-id="0c83d-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="0c83d-143">**Attribute**</span></span>|<span data-ttu-id="0c83d-144">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c83d-144">**Type**</span></span>|<span data-ttu-id="0c83d-145">**必需**</span><span class="sxs-lookup"><span data-stu-id="0c83d-145">**Required**</span></span>|<span data-ttu-id="0c83d-146">**描述**</span><span class="sxs-lookup"><span data-stu-id="0c83d-146">**Description**</span></span>|<span data-ttu-id="0c83d-147">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0c83d-147">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c83d-148">Container</span><span class="sxs-lookup"><span data-stu-id="0c83d-148">Container</span></span>  <br/> |<span data-ttu-id="0c83d-149">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-150">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-150">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-151">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-152">ContainerType</span><span class="sxs-lookup"><span data-stu-id="0c83d-152">ContainerType</span></span>  <br/> |<span data-ttu-id="0c83d-153">xsd: token</span><span class="sxs-lookup"><span data-stu-id="0c83d-153">xsd:token</span></span>  <br/> |<span data-ttu-id="0c83d-154">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-154">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-155">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-155">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-156">Document</span><span class="sxs-lookup"><span data-stu-id="0c83d-156">Document</span></span>  <br/> |<span data-ttu-id="0c83d-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0c83d-157">xsd:string</span></span>  <br/> |<span data-ttu-id="0c83d-158">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-158">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-159">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-159">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-160">ID</span><span class="sxs-lookup"><span data-stu-id="0c83d-160">ID</span></span>  <br/> |<span data-ttu-id="0c83d-161">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-161">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-162">必需</span><span class="sxs-lookup"><span data-stu-id="0c83d-162">required</span></span>  <br/> ||<span data-ttu-id="0c83d-163">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-163">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-164">Master</span><span class="sxs-lookup"><span data-stu-id="0c83d-164">Master</span></span>  <br/> |<span data-ttu-id="0c83d-165">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-165">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-166">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-166">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-167">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-168">Page</span><span class="sxs-lookup"><span data-stu-id="0c83d-168">Page</span></span>  <br/> |<span data-ttu-id="0c83d-169">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-169">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-170">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-170">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-171">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-171">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-172">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="0c83d-172">ParentWindow</span></span>  <br/> |<span data-ttu-id="0c83d-173">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-173">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-174">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-174">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-175">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-175">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-176">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="0c83d-176">ReadOnly</span></span>  <br/> |<span data-ttu-id="0c83d-177">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="0c83d-177">xsd:boolean</span></span>  <br/> |<span data-ttu-id="0c83d-178">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-178">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-179">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-179">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-180">Sheet</span><span class="sxs-lookup"><span data-stu-id="0c83d-180">Sheet</span></span>  <br/> |<span data-ttu-id="0c83d-181">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-181">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-182">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-182">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-183">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-183">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-184">ViewCenterX</span><span class="sxs-lookup"><span data-stu-id="0c83d-184">ViewCenterX</span></span>  <br/> |<span data-ttu-id="0c83d-185">xsd: double</span><span class="sxs-lookup"><span data-stu-id="0c83d-185">xsd:double</span></span>  <br/> |<span data-ttu-id="0c83d-186">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-186">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-187">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-187">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-188">ViewCenterY</span><span class="sxs-lookup"><span data-stu-id="0c83d-188">ViewCenterY</span></span>  <br/> |<span data-ttu-id="0c83d-189">xsd: double</span><span class="sxs-lookup"><span data-stu-id="0c83d-189">xsd:double</span></span>  <br/> |<span data-ttu-id="0c83d-190">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-190">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-191">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-191">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-192">ViewScale</span><span class="sxs-lookup"><span data-stu-id="0c83d-192">ViewScale</span></span>  <br/> |<span data-ttu-id="0c83d-193">xsd: double</span><span class="sxs-lookup"><span data-stu-id="0c83d-193">xsd:double</span></span>  <br/> |<span data-ttu-id="0c83d-194">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-194">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-195">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-195">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-196">WindowHeight</span><span class="sxs-lookup"><span data-stu-id="0c83d-196">WindowHeight</span></span>  <br/> |<span data-ttu-id="0c83d-197">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-197">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-198">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-198">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-199">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-199">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-200">WindowLeft</span><span class="sxs-lookup"><span data-stu-id="0c83d-200">WindowLeft</span></span>  <br/> |<span data-ttu-id="0c83d-201">xsd: short</span><span class="sxs-lookup"><span data-stu-id="0c83d-201">xsd:short</span></span>  <br/> |<span data-ttu-id="0c83d-202">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-202">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-203">Xsd: short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-203">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-204">WindowState</span><span class="sxs-lookup"><span data-stu-id="0c83d-204">WindowState</span></span>  <br/> |<span data-ttu-id="0c83d-205">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-205">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-206">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-206">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-207">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-207">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-208">WindowTop</span><span class="sxs-lookup"><span data-stu-id="0c83d-208">WindowTop</span></span>  <br/> |<span data-ttu-id="0c83d-209">xsd: short</span><span class="sxs-lookup"><span data-stu-id="0c83d-209">xsd:short</span></span>  <br/> |<span data-ttu-id="0c83d-210">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-210">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-211">Xsd: short 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-211">Values of the xsd:short type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-212">WindowType</span><span class="sxs-lookup"><span data-stu-id="0c83d-212">WindowType</span></span>  <br/> |<span data-ttu-id="0c83d-213">xsd: token</span><span class="sxs-lookup"><span data-stu-id="0c83d-213">xsd:token</span></span>  <br/> |<span data-ttu-id="0c83d-214">必需</span><span class="sxs-lookup"><span data-stu-id="0c83d-214">required</span></span>  <br/> ||<span data-ttu-id="0c83d-215">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-215">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="0c83d-216">WindowWidth</span><span class="sxs-lookup"><span data-stu-id="0c83d-216">WindowWidth</span></span>  <br/> |<span data-ttu-id="0c83d-217">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0c83d-217">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0c83d-218">可选</span><span class="sxs-lookup"><span data-stu-id="0c83d-218">optional</span></span>  <br/> ||<span data-ttu-id="0c83d-219">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0c83d-219">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

