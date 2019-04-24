---
title: Master_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2d799074-13d9-3c98-3bee-b57af9966c81
ms.openlocfilehash: 186099d495849706f68113abb269de4a1f5a2ce7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341802"
---
# <a name="mastertype-complextype-visio-xml"></a><span data-ttu-id="2b035-102">Master_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="2b035-102">Master_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2b035-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2b035-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b035-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2b035-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2b035-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2b035-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2b035-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="2b035-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2b035-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2b035-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2b035-108">无</span><span class="sxs-lookup"><span data-stu-id="2b035-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2b035-109">定义</span><span class="sxs-lookup"><span data-stu-id="2b035-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="2b035-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2b035-110">Elements and attributes</span></span>

<span data-ttu-id="2b035-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2b035-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2b035-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b035-112">Child elements</span></span>

|<span data-ttu-id="2b035-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b035-113">**Element**</span></span>|<span data-ttu-id="2b035-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b035-114">**Type**</span></span>|<span data-ttu-id="2b035-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b035-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2b035-116">Icon</span><span class="sxs-lookup"><span data-stu-id="2b035-116">Icon</span></span>](icon-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2b035-117">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="2b035-117">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="2b035-118">PageSheet</span><span class="sxs-lookup"><span data-stu-id="2b035-118">PageSheet</span></span>](pagesheet-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2b035-119">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="2b035-119">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="2b035-120">相对</span><span class="sxs-lookup"><span data-stu-id="2b035-120">Rel</span></span>](rel-element-master_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2b035-121">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="2b035-121">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2b035-122">属性</span><span class="sxs-lookup"><span data-stu-id="2b035-122">Attributes</span></span>

|<span data-ttu-id="2b035-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="2b035-123">**Attribute**</span></span>|<span data-ttu-id="2b035-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b035-124">**Type**</span></span>|<span data-ttu-id="2b035-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="2b035-125">**Required**</span></span>|<span data-ttu-id="2b035-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="2b035-126">**Description**</span></span>|<span data-ttu-id="2b035-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2b035-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b035-128">AlignName</span><span class="sxs-lookup"><span data-stu-id="2b035-128">AlignName</span></span>  <br/> |<span data-ttu-id="2b035-129">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2b035-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2b035-130">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-130">optional</span></span>  <br/> ||<span data-ttu-id="2b035-131">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2b035-132">BaseID</span><span class="sxs-lookup"><span data-stu-id="2b035-132">BaseID</span></span>  <br/> |<span data-ttu-id="2b035-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b035-133">xsd:string</span></span>  <br/> |<span data-ttu-id="2b035-134">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-134">optional</span></span>  <br/> ||<span data-ttu-id="2b035-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b035-136">Hidden</span><span class="sxs-lookup"><span data-stu-id="2b035-136">Hidden</span></span>  <br/> |<span data-ttu-id="2b035-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="2b035-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2b035-138">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-138">optional</span></span>  <br/> ||<span data-ttu-id="2b035-139">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-139">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2b035-140">IconSize</span><span class="sxs-lookup"><span data-stu-id="2b035-140">IconSize</span></span>  <br/> |<span data-ttu-id="2b035-141">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2b035-141">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2b035-142">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-142">optional</span></span>  <br/> ||<span data-ttu-id="2b035-143">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-143">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2b035-144">IconUpdate</span><span class="sxs-lookup"><span data-stu-id="2b035-144">IconUpdate</span></span>  <br/> |<span data-ttu-id="2b035-145">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="2b035-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2b035-146">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-146">optional</span></span>  <br/> ||<span data-ttu-id="2b035-147">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-147">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2b035-148">ID</span><span class="sxs-lookup"><span data-stu-id="2b035-148">ID</span></span>  <br/> |<span data-ttu-id="2b035-149">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2b035-149">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2b035-150">必需</span><span class="sxs-lookup"><span data-stu-id="2b035-150">required</span></span>  <br/> ||<span data-ttu-id="2b035-151">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-151">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="2b035-152">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="2b035-152">IsCustomName</span></span>  <br/> |<span data-ttu-id="2b035-153">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="2b035-153">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2b035-154">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-154">optional</span></span>  <br/> ||<span data-ttu-id="2b035-155">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-155">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2b035-156">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="2b035-156">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="2b035-157">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="2b035-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2b035-158">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-158">optional</span></span>  <br/> ||<span data-ttu-id="2b035-159">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-159">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2b035-160">MasterType</span><span class="sxs-lookup"><span data-stu-id="2b035-160">MasterType</span></span>  <br/> |<span data-ttu-id="2b035-161">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2b035-161">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2b035-162">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-162">optional</span></span>  <br/> ||<span data-ttu-id="2b035-163">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-163">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2b035-164">MatchByName</span><span class="sxs-lookup"><span data-stu-id="2b035-164">MatchByName</span></span>  <br/> |<span data-ttu-id="2b035-165">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="2b035-165">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2b035-166">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-166">optional</span></span>  <br/> ||<span data-ttu-id="2b035-167">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-167">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2b035-168">名称</span><span class="sxs-lookup"><span data-stu-id="2b035-168">Name</span></span>  <br/> |<span data-ttu-id="2b035-169">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b035-169">xsd:string</span></span>  <br/> |<span data-ttu-id="2b035-170">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-170">optional</span></span>  <br/> ||<span data-ttu-id="2b035-171">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-171">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b035-172">NameU</span><span class="sxs-lookup"><span data-stu-id="2b035-172">NameU</span></span>  <br/> |<span data-ttu-id="2b035-173">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b035-173">xsd:string</span></span>  <br/> |<span data-ttu-id="2b035-174">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-174">optional</span></span>  <br/> ||<span data-ttu-id="2b035-175">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-175">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b035-176">PatternFlags</span><span class="sxs-lookup"><span data-stu-id="2b035-176">PatternFlags</span></span>  <br/> |<span data-ttu-id="2b035-177">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2b035-177">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="2b035-178">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-178">optional</span></span>  <br/> ||<span data-ttu-id="2b035-179">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-179">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="2b035-180">Prompt</span><span class="sxs-lookup"><span data-stu-id="2b035-180">Prompt</span></span>  <br/> |<span data-ttu-id="2b035-181">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b035-181">xsd:string</span></span>  <br/> |<span data-ttu-id="2b035-182">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-182">optional</span></span>  <br/> ||<span data-ttu-id="2b035-183">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-183">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2b035-184">UniqueID</span><span class="sxs-lookup"><span data-stu-id="2b035-184">UniqueID</span></span>  <br/> |<span data-ttu-id="2b035-185">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b035-185">xsd:string</span></span>  <br/> |<span data-ttu-id="2b035-186">可选</span><span class="sxs-lookup"><span data-stu-id="2b035-186">optional</span></span>  <br/> ||<span data-ttu-id="2b035-187">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b035-187">Values of the xsd:string type.</span></span>  <br/> |
   

