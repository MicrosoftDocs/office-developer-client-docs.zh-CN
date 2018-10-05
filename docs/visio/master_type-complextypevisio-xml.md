---
title: Master_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2d799074-13d9-3c98-3bee-b57af9966c81
ms.openlocfilehash: 186099d495849706f68113abb269de4a1f5a2ce7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397708"
---
# <a name="mastertype-complextype-visio-xml"></a><span data-ttu-id="2c7ab-102">Master_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2c7ab-102">Master_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2c7ab-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2c7ab-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2c7ab-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2c7ab-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2c7ab-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="2c7ab-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2c7ab-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2c7ab-108">无</span><span class="sxs-lookup"><span data-stu-id="2c7ab-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2c7ab-109">定义</span><span class="sxs-lookup"><span data-stu-id="2c7ab-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="2c7ab-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2c7ab-110">Elements and attributes</span></span>

<span data-ttu-id="2c7ab-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2c7ab-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2c7ab-112">Child elements</span></span>

|<span data-ttu-id="2c7ab-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-113">**Element**</span></span>|<span data-ttu-id="2c7ab-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-114">**Type**</span></span>|<span data-ttu-id="2c7ab-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2c7ab-116">图标</span><span class="sxs-lookup"><span data-stu-id="2c7ab-116">Icon</span></span>](icon-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2c7ab-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="2c7ab-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="2c7ab-118">PageSheet</span><span class="sxs-lookup"><span data-stu-id="2c7ab-118">PageSheet</span></span>](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2c7ab-119">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="2c7ab-119">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="2c7ab-120">Rel</span><span class="sxs-lookup"><span data-stu-id="2c7ab-120">Rel</span></span>](rel-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2c7ab-121">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="2c7ab-121">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2c7ab-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="2c7ab-122">Attributes</span></span>

|<span data-ttu-id="2c7ab-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-123">**Attribute**</span></span>|<span data-ttu-id="2c7ab-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-124">**Type**</span></span>|<span data-ttu-id="2c7ab-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-125">**Required**</span></span>|<span data-ttu-id="2c7ab-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-126">**Description**</span></span>|<span data-ttu-id="2c7ab-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2c7ab-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c7ab-128">AlignName</span><span class="sxs-lookup"><span data-stu-id="2c7ab-128">AlignName</span></span>  <br/> |<span data-ttu-id="2c7ab-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2c7ab-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2c7ab-130">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-130">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-132">BaseID</span><span class="sxs-lookup"><span data-stu-id="2c7ab-132">BaseID</span></span>  <br/> |<span data-ttu-id="2c7ab-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2c7ab-133">xsd:string</span></span>  <br/> |<span data-ttu-id="2c7ab-134">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-134">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-136">隐藏</span><span class="sxs-lookup"><span data-stu-id="2c7ab-136">Hidden</span></span>  <br/> |<span data-ttu-id="2c7ab-137">化</span><span class="sxs-lookup"><span data-stu-id="2c7ab-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2c7ab-138">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-138">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-140">IconSize</span><span class="sxs-lookup"><span data-stu-id="2c7ab-140">IconSize</span></span>  <br/> |<span data-ttu-id="2c7ab-141">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2c7ab-141">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2c7ab-142">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-142">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-143">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-143">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-144">IconUpdate</span><span class="sxs-lookup"><span data-stu-id="2c7ab-144">IconUpdate</span></span>  <br/> |<span data-ttu-id="2c7ab-145">化</span><span class="sxs-lookup"><span data-stu-id="2c7ab-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2c7ab-146">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-146">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-147">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-147">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-148">ID</span><span class="sxs-lookup"><span data-stu-id="2c7ab-148">ID</span></span>  <br/> |<span data-ttu-id="2c7ab-149">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2c7ab-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2c7ab-150">必需</span><span class="sxs-lookup"><span data-stu-id="2c7ab-150">required</span></span>  <br/> ||<span data-ttu-id="2c7ab-151">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-152">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="2c7ab-152">IsCustomName</span></span>  <br/> |<span data-ttu-id="2c7ab-153">化</span><span class="sxs-lookup"><span data-stu-id="2c7ab-153">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2c7ab-154">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-154">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-155">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-155">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-156">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="2c7ab-156">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="2c7ab-157">化</span><span class="sxs-lookup"><span data-stu-id="2c7ab-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2c7ab-158">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-158">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-159">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-159">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-160">MasterType</span><span class="sxs-lookup"><span data-stu-id="2c7ab-160">MasterType</span></span>  <br/> |<span data-ttu-id="2c7ab-161">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2c7ab-161">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2c7ab-162">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-162">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-163">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-163">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-164">MatchByName</span><span class="sxs-lookup"><span data-stu-id="2c7ab-164">MatchByName</span></span>  <br/> |<span data-ttu-id="2c7ab-165">化</span><span class="sxs-lookup"><span data-stu-id="2c7ab-165">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2c7ab-166">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-166">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-167">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-167">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-168">名称</span><span class="sxs-lookup"><span data-stu-id="2c7ab-168">Name</span></span>  <br/> |<span data-ttu-id="2c7ab-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2c7ab-169">xsd:string</span></span>  <br/> |<span data-ttu-id="2c7ab-170">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-170">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-171">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-172">NameU</span><span class="sxs-lookup"><span data-stu-id="2c7ab-172">NameU</span></span>  <br/> |<span data-ttu-id="2c7ab-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2c7ab-173">xsd:string</span></span>  <br/> |<span data-ttu-id="2c7ab-174">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-174">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-175">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-176">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="2c7ab-176">PatternFlags</span></span>  <br/> |<span data-ttu-id="2c7ab-177">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2c7ab-177">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2c7ab-178">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-178">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-179">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-179">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-180">提示</span><span class="sxs-lookup"><span data-stu-id="2c7ab-180">Prompt</span></span>  <br/> |<span data-ttu-id="2c7ab-181">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2c7ab-181">xsd:string</span></span>  <br/> |<span data-ttu-id="2c7ab-182">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-182">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-183">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-183">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2c7ab-184">UniqueID</span><span class="sxs-lookup"><span data-stu-id="2c7ab-184">UniqueID</span></span>  <br/> |<span data-ttu-id="2c7ab-185">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2c7ab-185">xsd:string</span></span>  <br/> |<span data-ttu-id="2c7ab-186">可选</span><span class="sxs-lookup"><span data-stu-id="2c7ab-186">optional</span></span>  <br/> ||<span data-ttu-id="2c7ab-187">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2c7ab-187">Values of the xsd:string type.</span></span>  <br/> |
   

