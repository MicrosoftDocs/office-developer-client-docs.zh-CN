---
title: DocumentSettings_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8fb61b5f-1bab-78b6-c56c-384e52609397
ms.openlocfilehash: 93623133e7d7fd096e063f0d9d5227d65dcc4736
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780145"
---
# <a name="documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="9e809-102">DocumentSettings_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9e809-102">DocumentSettings_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9e809-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9e809-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9e809-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9e809-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9e809-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9e809-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9e809-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="9e809-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9e809-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9e809-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9e809-108">无</span><span class="sxs-lookup"><span data-stu-id="9e809-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9e809-109">定义</span><span class="sxs-lookup"><span data-stu-id="9e809-109">Definition</span></span>

```XML
          <xs:complexType name="DocumentSettings_Type">
          
          <xs:all>
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
    
    <xs:element name="ProtectStyles"  type="ProtectStyles_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ProtectShapes"  type="ProtectShapes_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ProtectMasters"  type="ProtectMasters_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ProtectBkgnds"  type="ProtectBkgnds_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="CustomMenusFile"  type="CustomMenusFile_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="CustomToolbarsFile"  type="CustomToolbarsFile_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="AttachedToolbars"  type="AttachedToolbars_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:all>
    <xs:attribute name="TopPage"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DefaultTextStyle"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DefaultLineStyle"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DefaultFillStyle"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DefaultGuideStyle"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9e809-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9e809-110">Elements and attributes</span></span>

<span data-ttu-id="9e809-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9e809-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9e809-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9e809-112">Child elements</span></span>

|<span data-ttu-id="9e809-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e809-113">**Element**</span></span>|<span data-ttu-id="9e809-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e809-114">**Type**</span></span>|<span data-ttu-id="9e809-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e809-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9e809-116">AttachedToolbars</span><span class="sxs-lookup"><span data-stu-id="9e809-116">AttachedToolbars</span></span>](attachedtoolbars-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-117">AttachedToolbars_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-117">AttachedToolbars_Type</span></span>](attachedtoolbars_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-118">CustomMenusFile</span><span class="sxs-lookup"><span data-stu-id="9e809-118">CustomMenusFile</span></span>](custommenusfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-119">CustomMenusFile_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-119">CustomMenusFile_Type</span></span>](custommenusfile_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-120">CustomToolbarsFile</span><span class="sxs-lookup"><span data-stu-id="9e809-120">CustomToolbarsFile</span></span>](customtoolbarsfile-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-121">CustomToolbarsFile_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-121">CustomToolbarsFile_Type</span></span>](customtoolbarsfile_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-122">DynamicGridEnabled</span><span class="sxs-lookup"><span data-stu-id="9e809-122">DynamicGridEnabled</span></span>](dynamicgridenabled-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-123">DynamicGridEnabled_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-123">DynamicGridEnabled_Type</span></span>](dynamicgridenabled_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-124">GlueSettings</span><span class="sxs-lookup"><span data-stu-id="9e809-124">GlueSettings</span></span>](gluesettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-125">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-125">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-126">ProtectBkgnds</span><span class="sxs-lookup"><span data-stu-id="9e809-126">ProtectBkgnds</span></span>](protectbkgnds-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-127">ProtectBkgnds_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-127">ProtectBkgnds_Type</span></span>](protectbkgnds_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-128">ProtectMasters</span><span class="sxs-lookup"><span data-stu-id="9e809-128">ProtectMasters</span></span>](protectmasters-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-129">ProtectMasters_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-129">ProtectMasters_Type</span></span>](protectmasters_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-130">ProtectShapes</span><span class="sxs-lookup"><span data-stu-id="9e809-130">ProtectShapes</span></span>](protectshapes-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-131">ProtectShapes_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-131">ProtectShapes_Type</span></span>](protectshapes_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-132">ProtectStyles</span><span class="sxs-lookup"><span data-stu-id="9e809-132">ProtectStyles</span></span>](protectstyles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-133">ProtectStyles_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-133">ProtectStyles_Type</span></span>](protectstyles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-134">SnapAngles</span><span class="sxs-lookup"><span data-stu-id="9e809-134">SnapAngles</span></span>](snapangles-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-135">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-135">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-136">SnapExtensions</span><span class="sxs-lookup"><span data-stu-id="9e809-136">SnapExtensions</span></span>](snapextensions-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-137">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-137">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="9e809-138">SnapSettings</span><span class="sxs-lookup"><span data-stu-id="9e809-138">SnapSettings</span></span>](snapsettings-element-documentsettings_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e809-139">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="9e809-139">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="9e809-140">Attributes</span><span class="sxs-lookup"><span data-stu-id="9e809-140">Attributes</span></span>

|<span data-ttu-id="9e809-141">**属性**</span><span class="sxs-lookup"><span data-stu-id="9e809-141">**Attribute**</span></span>|<span data-ttu-id="9e809-142">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e809-142">**Type**</span></span>|<span data-ttu-id="9e809-143">**必需**</span><span class="sxs-lookup"><span data-stu-id="9e809-143">**Required**</span></span>|<span data-ttu-id="9e809-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e809-144">**Description**</span></span>|<span data-ttu-id="9e809-145">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9e809-145">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e809-146">DefaultFillStyle</span><span class="sxs-lookup"><span data-stu-id="9e809-146">DefaultFillStyle</span></span>  <br/> |<span data-ttu-id="9e809-147">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e809-147">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e809-148">可选</span><span class="sxs-lookup"><span data-stu-id="9e809-148">optional</span></span>  <br/> ||<span data-ttu-id="9e809-149">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e809-149">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9e809-150">DefaultGuideStyle</span><span class="sxs-lookup"><span data-stu-id="9e809-150">DefaultGuideStyle</span></span>  <br/> |<span data-ttu-id="9e809-151">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e809-151">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e809-152">可选</span><span class="sxs-lookup"><span data-stu-id="9e809-152">optional</span></span>  <br/> ||<span data-ttu-id="9e809-153">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e809-153">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9e809-154">DefaultLineStyle</span><span class="sxs-lookup"><span data-stu-id="9e809-154">DefaultLineStyle</span></span>  <br/> |<span data-ttu-id="9e809-155">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e809-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e809-156">可选</span><span class="sxs-lookup"><span data-stu-id="9e809-156">optional</span></span>  <br/> ||<span data-ttu-id="9e809-157">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e809-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9e809-158">DefaultTextStyle</span><span class="sxs-lookup"><span data-stu-id="9e809-158">DefaultTextStyle</span></span>  <br/> |<span data-ttu-id="9e809-159">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e809-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e809-160">可选</span><span class="sxs-lookup"><span data-stu-id="9e809-160">optional</span></span>  <br/> ||<span data-ttu-id="9e809-161">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e809-161">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9e809-162">TopPage</span><span class="sxs-lookup"><span data-stu-id="9e809-162">TopPage</span></span>  <br/> |<span data-ttu-id="9e809-163">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e809-163">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e809-164">可选</span><span class="sxs-lookup"><span data-stu-id="9e809-164">optional</span></span>  <br/> ||<span data-ttu-id="9e809-165">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e809-165">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

