---
title: Master_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2d799074-13d9-3c98-3bee-b57af9966c81
ms.openlocfilehash: b4dde4d00552525a5ec17116f96151f39c6d0957
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780689"
---
# <a name="mastertype-complextype-visio-xml"></a><span data-ttu-id="c50be-102">Master_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c50be-102">Master_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="c50be-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c50be-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c50be-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c50be-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c50be-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c50be-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c50be-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="c50be-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c50be-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c50be-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c50be-108">无</span><span class="sxs-lookup"><span data-stu-id="c50be-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c50be-109">定义</span><span class="sxs-lookup"><span data-stu-id="c50be-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="c50be-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c50be-110">Elements and attributes</span></span>

<span data-ttu-id="c50be-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c50be-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c50be-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c50be-112">Child elements</span></span>

|<span data-ttu-id="c50be-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="c50be-113">**Element**</span></span>|<span data-ttu-id="c50be-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="c50be-114">**Type**</span></span>|<span data-ttu-id="c50be-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="c50be-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c50be-116">图标</span><span class="sxs-lookup"><span data-stu-id="c50be-116">Icon</span></span>](icon-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c50be-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="c50be-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="c50be-118">PageSheet</span><span class="sxs-lookup"><span data-stu-id="c50be-118">PageSheet</span></span>](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c50be-119">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="c50be-119">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="c50be-120">Rel</span><span class="sxs-lookup"><span data-stu-id="c50be-120">Rel</span></span>](rel-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c50be-121">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="c50be-121">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="c50be-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="c50be-122">Attributes</span></span>

|<span data-ttu-id="c50be-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="c50be-123">**Attribute**</span></span>|<span data-ttu-id="c50be-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="c50be-124">**Type**</span></span>|<span data-ttu-id="c50be-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="c50be-125">**Required**</span></span>|<span data-ttu-id="c50be-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c50be-126">**Description**</span></span>|<span data-ttu-id="c50be-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c50be-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c50be-128">AlignName</span><span class="sxs-lookup"><span data-stu-id="c50be-128">AlignName</span></span>  <br/> |<span data-ttu-id="c50be-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c50be-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c50be-130">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-130">optional</span></span>  <br/> ||<span data-ttu-id="c50be-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c50be-132">BaseID</span><span class="sxs-lookup"><span data-stu-id="c50be-132">BaseID</span></span>  <br/> |<span data-ttu-id="c50be-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c50be-133">xsd:string</span></span>  <br/> |<span data-ttu-id="c50be-134">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-134">optional</span></span>  <br/> ||<span data-ttu-id="c50be-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c50be-136">隐藏</span><span class="sxs-lookup"><span data-stu-id="c50be-136">Hidden</span></span>  <br/> |<span data-ttu-id="c50be-137">化</span><span class="sxs-lookup"><span data-stu-id="c50be-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c50be-138">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-138">optional</span></span>  <br/> ||<span data-ttu-id="c50be-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c50be-140">IconSize</span><span class="sxs-lookup"><span data-stu-id="c50be-140">IconSize</span></span>  <br/> |<span data-ttu-id="c50be-141">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c50be-141">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c50be-142">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-142">optional</span></span>  <br/> ||<span data-ttu-id="c50be-143">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-143">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c50be-144">IconUpdate</span><span class="sxs-lookup"><span data-stu-id="c50be-144">IconUpdate</span></span>  <br/> |<span data-ttu-id="c50be-145">化</span><span class="sxs-lookup"><span data-stu-id="c50be-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c50be-146">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-146">optional</span></span>  <br/> ||<span data-ttu-id="c50be-147">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-147">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c50be-148">ID</span><span class="sxs-lookup"><span data-stu-id="c50be-148">ID</span></span>  <br/> |<span data-ttu-id="c50be-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c50be-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c50be-150">必需</span><span class="sxs-lookup"><span data-stu-id="c50be-150">required</span></span>  <br/> ||<span data-ttu-id="c50be-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c50be-152">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="c50be-152">IsCustomName</span></span>  <br/> |<span data-ttu-id="c50be-153">化</span><span class="sxs-lookup"><span data-stu-id="c50be-153">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c50be-154">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-154">optional</span></span>  <br/> ||<span data-ttu-id="c50be-155">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-155">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c50be-156">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="c50be-156">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="c50be-157">化</span><span class="sxs-lookup"><span data-stu-id="c50be-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c50be-158">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-158">optional</span></span>  <br/> ||<span data-ttu-id="c50be-159">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-159">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c50be-160">MasterType</span><span class="sxs-lookup"><span data-stu-id="c50be-160">MasterType</span></span>  <br/> |<span data-ttu-id="c50be-161">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c50be-161">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c50be-162">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-162">optional</span></span>  <br/> ||<span data-ttu-id="c50be-163">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-163">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c50be-164">MatchByName</span><span class="sxs-lookup"><span data-stu-id="c50be-164">MatchByName</span></span>  <br/> |<span data-ttu-id="c50be-165">化</span><span class="sxs-lookup"><span data-stu-id="c50be-165">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c50be-166">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-166">optional</span></span>  <br/> ||<span data-ttu-id="c50be-167">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-167">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c50be-168">名称</span><span class="sxs-lookup"><span data-stu-id="c50be-168">Name</span></span>  <br/> |<span data-ttu-id="c50be-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c50be-169">xsd:string</span></span>  <br/> |<span data-ttu-id="c50be-170">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-170">optional</span></span>  <br/> ||<span data-ttu-id="c50be-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c50be-172">NameU</span><span class="sxs-lookup"><span data-stu-id="c50be-172">NameU</span></span>  <br/> |<span data-ttu-id="c50be-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c50be-173">xsd:string</span></span>  <br/> |<span data-ttu-id="c50be-174">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-174">optional</span></span>  <br/> ||<span data-ttu-id="c50be-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c50be-176">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="c50be-176">PatternFlags</span></span>  <br/> |<span data-ttu-id="c50be-177">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c50be-177">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c50be-178">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-178">optional</span></span>  <br/> ||<span data-ttu-id="c50be-179">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-179">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c50be-180">提示</span><span class="sxs-lookup"><span data-stu-id="c50be-180">Prompt</span></span>  <br/> |<span data-ttu-id="c50be-181">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c50be-181">xsd:string</span></span>  <br/> |<span data-ttu-id="c50be-182">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-182">optional</span></span>  <br/> ||<span data-ttu-id="c50be-183">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-183">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c50be-184">UniqueID</span><span class="sxs-lookup"><span data-stu-id="c50be-184">UniqueID</span></span>  <br/> |<span data-ttu-id="c50be-185">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c50be-185">xsd:string</span></span>  <br/> |<span data-ttu-id="c50be-186">可选</span><span class="sxs-lookup"><span data-stu-id="c50be-186">optional</span></span>  <br/> ||<span data-ttu-id="c50be-187">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c50be-187">Values of the xsd:string type.</span></span>  <br/> |
   

