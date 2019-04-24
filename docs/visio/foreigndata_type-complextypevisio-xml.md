---
title: ForeignData_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21b394a6-6f95-fc17-482c-4cb648a0d9bb
ms.openlocfilehash: 6630c8b33dc1c4c7cbb12bb9727d4f0b1e1b19d2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346009"
---
# <a name="foreigndatatype-complextype-visio-xml"></a><span data-ttu-id="6c36b-102">ForeignData_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="6c36b-102">ForeignData_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="6c36b-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="6c36b-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6c36b-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6c36b-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="6c36b-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6c36b-105">**Schema file**</span></span> <br/> |<span data-ttu-id="6c36b-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="6c36b-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="6c36b-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="6c36b-107">**Extension base**</span></span> <br/> |<span data-ttu-id="6c36b-108">无</span><span class="sxs-lookup"><span data-stu-id="6c36b-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6c36b-109">定义</span><span class="sxs-lookup"><span data-stu-id="6c36b-109">Definition</span></span>

```XML
          <xs:complexType name="ForeignData_Type">
          
          <xs:sequence>
    <xs:element name="Rel"  type="Rel_Type"
     minOccurs="1"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ForeignType"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="ObjectType"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="ShowAsIcon"
  type="xsd:boolean"
    />
    <xs:attribute name="ObjectWidth"
  type="xsd:double"
    />
    <xs:attribute name="ObjectHeight"
  type="xsd:double"
    />
    <xs:attribute name="MappingMode"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="ExtentX"
  type="xsd:double"
    />
    <xs:attribute name="ExtentY"
  type="xsd:double"
    />
    <xs:attribute name="CompressionType"
  type="xsd:token"
    />
    <xs:attribute name="CompressionLevel"
  type="xsd:double"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6c36b-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6c36b-110">Elements and attributes</span></span>

<span data-ttu-id="6c36b-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="6c36b-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="6c36b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6c36b-112">Child elements</span></span>

|<span data-ttu-id="6c36b-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="6c36b-113">**Element**</span></span>|<span data-ttu-id="6c36b-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="6c36b-114">**Type**</span></span>|<span data-ttu-id="6c36b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c36b-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6c36b-116">相对</span><span class="sxs-lookup"><span data-stu-id="6c36b-116">Rel</span></span>](rel-element-foreigndata_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6c36b-117">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="6c36b-117">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="6c36b-118">属性</span><span class="sxs-lookup"><span data-stu-id="6c36b-118">Attributes</span></span>

|<span data-ttu-id="6c36b-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="6c36b-119">**Attribute**</span></span>|<span data-ttu-id="6c36b-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="6c36b-120">**Type**</span></span>|<span data-ttu-id="6c36b-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="6c36b-121">**Required**</span></span>|<span data-ttu-id="6c36b-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="6c36b-122">**Description**</span></span>|<span data-ttu-id="6c36b-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6c36b-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c36b-124">CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="6c36b-124">CompressionLevel</span></span>  <br/> |<span data-ttu-id="6c36b-125">xsd: double</span><span class="sxs-lookup"><span data-stu-id="6c36b-125">xsd:double</span></span>  <br/> |<span data-ttu-id="6c36b-126">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-126">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-127">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-127">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-128">CompressionType</span><span class="sxs-lookup"><span data-stu-id="6c36b-128">CompressionType</span></span>  <br/> |<span data-ttu-id="6c36b-129">xsd: token</span><span class="sxs-lookup"><span data-stu-id="6c36b-129">xsd:token</span></span>  <br/> |<span data-ttu-id="6c36b-130">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-130">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-131">xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-131">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-132">ExtentX</span><span class="sxs-lookup"><span data-stu-id="6c36b-132">ExtentX</span></span>  <br/> |<span data-ttu-id="6c36b-133">xsd: double</span><span class="sxs-lookup"><span data-stu-id="6c36b-133">xsd:double</span></span>  <br/> |<span data-ttu-id="6c36b-134">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-134">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-135">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-135">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-136">ExtentY</span><span class="sxs-lookup"><span data-stu-id="6c36b-136">ExtentY</span></span>  <br/> |<span data-ttu-id="6c36b-137">xsd: double</span><span class="sxs-lookup"><span data-stu-id="6c36b-137">xsd:double</span></span>  <br/> |<span data-ttu-id="6c36b-138">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-138">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-139">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-139">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-140">ForeignType</span><span class="sxs-lookup"><span data-stu-id="6c36b-140">ForeignType</span></span>  <br/> |<span data-ttu-id="6c36b-141">xsd: token</span><span class="sxs-lookup"><span data-stu-id="6c36b-141">xsd:token</span></span>  <br/> |<span data-ttu-id="6c36b-142">必需</span><span class="sxs-lookup"><span data-stu-id="6c36b-142">required</span></span>  <br/> ||<span data-ttu-id="6c36b-143">xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-143">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-144">MappingMode</span><span class="sxs-lookup"><span data-stu-id="6c36b-144">MappingMode</span></span>  <br/> |<span data-ttu-id="6c36b-145">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="6c36b-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="6c36b-146">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-146">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-147">xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-148">ObjectHeight</span><span class="sxs-lookup"><span data-stu-id="6c36b-148">ObjectHeight</span></span>  <br/> |<span data-ttu-id="6c36b-149">xsd: double</span><span class="sxs-lookup"><span data-stu-id="6c36b-149">xsd:double</span></span>  <br/> |<span data-ttu-id="6c36b-150">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-150">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-151">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-151">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-152">ObjectType</span><span class="sxs-lookup"><span data-stu-id="6c36b-152">ObjectType</span></span>  <br/> |<span data-ttu-id="6c36b-153">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6c36b-153">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="6c36b-154">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-154">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-155">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-156">ObjectWidth</span><span class="sxs-lookup"><span data-stu-id="6c36b-156">ObjectWidth</span></span>  <br/> |<span data-ttu-id="6c36b-157">xsd: double</span><span class="sxs-lookup"><span data-stu-id="6c36b-157">xsd:double</span></span>  <br/> |<span data-ttu-id="6c36b-158">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-158">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-159">xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-159">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="6c36b-160">ShowAsIcon</span><span class="sxs-lookup"><span data-stu-id="6c36b-160">ShowAsIcon</span></span>  <br/> |<span data-ttu-id="6c36b-161">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="6c36b-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="6c36b-162">可选</span><span class="sxs-lookup"><span data-stu-id="6c36b-162">optional</span></span>  <br/> ||<span data-ttu-id="6c36b-163">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6c36b-163">Values of the xsd:boolean type.</span></span>  <br/> |
   

