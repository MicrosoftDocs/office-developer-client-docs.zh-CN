---
title: 'Master_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2d799074-13d9-3c98-3bee-b57af9966c81
ms.openlocfilehash: 22b619149fc5393f085ca6e245c65ed6058538ae
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538065"
---
# <a name="master_type-complextype-visio-xml"></a><span data-ttu-id="e0242-102">Master_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="e0242-102">Master_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="e0242-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e0242-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e0242-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e0242-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e0242-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e0242-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e0242-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="e0242-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e0242-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e0242-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e0242-108">无</span><span class="sxs-lookup"><span data-stu-id="e0242-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e0242-109">定义</span><span class="sxs-lookup"><span data-stu-id="e0242-109">Definition</span></span>

```XML
          <xs:complexType name="Master_Type">
          
          <xs:all>
    <xs:element name="PageSheet"  type="PageSheet_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Icon"  type="Icon_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:all>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="BaseID"
  type="xsd:string"
    />
    <xs:attribute name="UniqueID"
  type="xsd:string"
    />
    <xs:attribute name="MatchByName"
  type="xsd:boolean"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
    />
    <xs:attribute name="IsCustomName"
  type="xsd:boolean"
    />
    <xs:attribute name="IsCustomNameU"
  type="xsd:boolean"
    />
    <xs:attribute name="IconSize"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="PatternFlags"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="Prompt"
  type="xsd:string"
    />
    <xs:attribute name="Hidden"
  type="xsd:boolean"
    />
    <xs:attribute name="IconUpdate"
  type="xsd:boolean"
    />
    <xs:attribute name="AlignName"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="MasterType"
  type="xsd:unsignedShort"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e0242-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e0242-110">Elements and attributes</span></span>

<span data-ttu-id="e0242-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e0242-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e0242-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e0242-112">Child elements</span></span>

|<span data-ttu-id="e0242-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e0242-113">**Element**</span></span>|<span data-ttu-id="e0242-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e0242-114">**Type**</span></span>|<span data-ttu-id="e0242-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e0242-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e0242-116">Icon</span><span class="sxs-lookup"><span data-stu-id="e0242-116">Icon</span></span>](icon-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e0242-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="e0242-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="e0242-118">PageSheet</span><span class="sxs-lookup"><span data-stu-id="e0242-118">PageSheet</span></span>](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e0242-119">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="e0242-119">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="e0242-120">Rel</span><span class="sxs-lookup"><span data-stu-id="e0242-120">Rel</span></span>](rel-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e0242-121">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="e0242-121">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e0242-122">属性</span><span class="sxs-lookup"><span data-stu-id="e0242-122">Attributes</span></span>

|<span data-ttu-id="e0242-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="e0242-123">**Attribute**</span></span>|<span data-ttu-id="e0242-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="e0242-124">**Type**</span></span>|<span data-ttu-id="e0242-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="e0242-125">**Required**</span></span>|<span data-ttu-id="e0242-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="e0242-126">**Description**</span></span>|<span data-ttu-id="e0242-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e0242-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0242-128">AlignName</span><span class="sxs-lookup"><span data-stu-id="e0242-128">AlignName</span></span>  <br/> |<span data-ttu-id="e0242-129">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="e0242-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="e0242-130">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-130">optional</span></span>  <br/> ||<span data-ttu-id="e0242-131">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="e0242-132">BaseID</span><span class="sxs-lookup"><span data-stu-id="e0242-132">BaseID</span></span>  <br/> |<span data-ttu-id="e0242-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0242-133">xsd:string</span></span>  <br/> |<span data-ttu-id="e0242-134">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-134">optional</span></span>  <br/> ||<span data-ttu-id="e0242-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e0242-136">Hidden</span><span class="sxs-lookup"><span data-stu-id="e0242-136">Hidden</span></span>  <br/> |<span data-ttu-id="e0242-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e0242-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e0242-138">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-138">optional</span></span>  <br/> ||<span data-ttu-id="e0242-139">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e0242-140">IconSize</span><span class="sxs-lookup"><span data-stu-id="e0242-140">IconSize</span></span>  <br/> |<span data-ttu-id="e0242-141">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="e0242-141">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="e0242-142">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-142">optional</span></span>  <br/> ||<span data-ttu-id="e0242-143">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-143">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="e0242-144">IconUpdate</span><span class="sxs-lookup"><span data-stu-id="e0242-144">IconUpdate</span></span>  <br/> |<span data-ttu-id="e0242-145">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e0242-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e0242-146">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-146">optional</span></span>  <br/> ||<span data-ttu-id="e0242-147">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-147">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e0242-148">ID</span><span class="sxs-lookup"><span data-stu-id="e0242-148">ID</span></span>  <br/> |<span data-ttu-id="e0242-149">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e0242-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e0242-150">必需</span><span class="sxs-lookup"><span data-stu-id="e0242-150">required</span></span>  <br/> ||<span data-ttu-id="e0242-151">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e0242-152">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="e0242-152">IsCustomName</span></span>  <br/> |<span data-ttu-id="e0242-153">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e0242-153">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e0242-154">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-154">optional</span></span>  <br/> ||<span data-ttu-id="e0242-155">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-155">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e0242-156">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="e0242-156">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="e0242-157">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e0242-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e0242-158">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-158">optional</span></span>  <br/> ||<span data-ttu-id="e0242-159">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-159">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e0242-160">MasterType</span><span class="sxs-lookup"><span data-stu-id="e0242-160">MasterType</span></span>  <br/> |<span data-ttu-id="e0242-161">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="e0242-161">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="e0242-162">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-162">optional</span></span>  <br/> ||<span data-ttu-id="e0242-163">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-163">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="e0242-164">MatchByName</span><span class="sxs-lookup"><span data-stu-id="e0242-164">MatchByName</span></span>  <br/> |<span data-ttu-id="e0242-165">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="e0242-165">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e0242-166">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-166">optional</span></span>  <br/> ||<span data-ttu-id="e0242-167">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-167">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e0242-168">名称</span><span class="sxs-lookup"><span data-stu-id="e0242-168">Name</span></span>  <br/> |<span data-ttu-id="e0242-169">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0242-169">xsd:string</span></span>  <br/> |<span data-ttu-id="e0242-170">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-170">optional</span></span>  <br/> ||<span data-ttu-id="e0242-171">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e0242-172">NameU</span><span class="sxs-lookup"><span data-stu-id="e0242-172">NameU</span></span>  <br/> |<span data-ttu-id="e0242-173">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0242-173">xsd:string</span></span>  <br/> |<span data-ttu-id="e0242-174">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-174">optional</span></span>  <br/> ||<span data-ttu-id="e0242-175">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e0242-176">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="e0242-176">PatternFlags</span></span>  <br/> |<span data-ttu-id="e0242-177">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="e0242-177">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="e0242-178">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-178">optional</span></span>  <br/> ||<span data-ttu-id="e0242-179">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-179">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="e0242-180">Prompt</span><span class="sxs-lookup"><span data-stu-id="e0242-180">Prompt</span></span>  <br/> |<span data-ttu-id="e0242-181">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0242-181">xsd:string</span></span>  <br/> |<span data-ttu-id="e0242-182">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-182">optional</span></span>  <br/> ||<span data-ttu-id="e0242-183">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-183">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e0242-184">UniqueID</span><span class="sxs-lookup"><span data-stu-id="e0242-184">UniqueID</span></span>  <br/> |<span data-ttu-id="e0242-185">xsd：string</span><span class="sxs-lookup"><span data-stu-id="e0242-185">xsd:string</span></span>  <br/> |<span data-ttu-id="e0242-186">可选</span><span class="sxs-lookup"><span data-stu-id="e0242-186">optional</span></span>  <br/> ||<span data-ttu-id="e0242-187">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e0242-187">Values of the xsd:string type.</span></span>  <br/> |
   

