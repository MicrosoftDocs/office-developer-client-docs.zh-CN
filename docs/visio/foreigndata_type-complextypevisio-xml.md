---
title: ForeignData_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21b394a6-6f95-fc17-482c-4cb648a0d9bb
ms.openlocfilehash: 1d9358de2f88a1b9e035ecf4966544ea935f8b2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780311"
---
# <a name="foreigndatatype-complextype-visio-xml"></a><span data-ttu-id="f6192-102">ForeignData_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f6192-102">ForeignData_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="f6192-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f6192-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f6192-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f6192-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f6192-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f6192-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f6192-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="f6192-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f6192-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f6192-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f6192-108">无</span><span class="sxs-lookup"><span data-stu-id="f6192-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f6192-109">定义</span><span class="sxs-lookup"><span data-stu-id="f6192-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="f6192-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f6192-110">Elements and attributes</span></span>

<span data-ttu-id="f6192-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f6192-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f6192-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f6192-112">Child elements</span></span>

|<span data-ttu-id="f6192-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f6192-113">**Element**</span></span>|<span data-ttu-id="f6192-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6192-114">**Type**</span></span>|<span data-ttu-id="f6192-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6192-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f6192-116">Rel</span><span class="sxs-lookup"><span data-stu-id="f6192-116">Rel</span></span>](rel-element-foreigndata_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f6192-117">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="f6192-117">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f6192-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f6192-118">Attributes</span></span>

|<span data-ttu-id="f6192-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="f6192-119">**Attribute**</span></span>|<span data-ttu-id="f6192-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="f6192-120">**Type**</span></span>|<span data-ttu-id="f6192-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="f6192-121">**Required**</span></span>|<span data-ttu-id="f6192-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="f6192-122">**Description**</span></span>|<span data-ttu-id="f6192-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f6192-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6192-124">CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="f6192-124">CompressionLevel</span></span>  <br/> |<span data-ttu-id="f6192-125">化</span><span class="sxs-lookup"><span data-stu-id="f6192-125">xsd:double</span></span>  <br/> |<span data-ttu-id="f6192-126">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-126">optional</span></span>  <br/> ||<span data-ttu-id="f6192-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-127">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="f6192-128">CompressionType</span><span class="sxs-lookup"><span data-stu-id="f6192-128">CompressionType</span></span>  <br/> |<span data-ttu-id="f6192-129">xsd:token</span><span class="sxs-lookup"><span data-stu-id="f6192-129">xsd:token</span></span>  <br/> |<span data-ttu-id="f6192-130">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-130">optional</span></span>  <br/> ||<span data-ttu-id="f6192-131">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-131">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="f6192-132">ExtentX</span><span class="sxs-lookup"><span data-stu-id="f6192-132">ExtentX</span></span>  <br/> |<span data-ttu-id="f6192-133">化</span><span class="sxs-lookup"><span data-stu-id="f6192-133">xsd:double</span></span>  <br/> |<span data-ttu-id="f6192-134">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-134">optional</span></span>  <br/> ||<span data-ttu-id="f6192-135">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-135">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="f6192-136">ExtentY</span><span class="sxs-lookup"><span data-stu-id="f6192-136">ExtentY</span></span>  <br/> |<span data-ttu-id="f6192-137">化</span><span class="sxs-lookup"><span data-stu-id="f6192-137">xsd:double</span></span>  <br/> |<span data-ttu-id="f6192-138">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-138">optional</span></span>  <br/> ||<span data-ttu-id="f6192-139">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-139">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="f6192-140">ForeignType</span><span class="sxs-lookup"><span data-stu-id="f6192-140">ForeignType</span></span>  <br/> |<span data-ttu-id="f6192-141">xsd:token</span><span class="sxs-lookup"><span data-stu-id="f6192-141">xsd:token</span></span>  <br/> |<span data-ttu-id="f6192-142">必需</span><span class="sxs-lookup"><span data-stu-id="f6192-142">required</span></span>  <br/> ||<span data-ttu-id="f6192-143">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-143">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="f6192-144">MappingMode</span><span class="sxs-lookup"><span data-stu-id="f6192-144">MappingMode</span></span>  <br/> |<span data-ttu-id="f6192-145">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f6192-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f6192-146">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-146">optional</span></span>  <br/> ||<span data-ttu-id="f6192-147">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f6192-148">ObjectHeight</span><span class="sxs-lookup"><span data-stu-id="f6192-148">ObjectHeight</span></span>  <br/> |<span data-ttu-id="f6192-149">化</span><span class="sxs-lookup"><span data-stu-id="f6192-149">xsd:double</span></span>  <br/> |<span data-ttu-id="f6192-150">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-150">optional</span></span>  <br/> ||<span data-ttu-id="f6192-151">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-151">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="f6192-152">ObjectType</span><span class="sxs-lookup"><span data-stu-id="f6192-152">ObjectType</span></span>  <br/> |<span data-ttu-id="f6192-153">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="f6192-153">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="f6192-154">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-154">optional</span></span>  <br/> ||<span data-ttu-id="f6192-155">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="f6192-156">ObjectWidth</span><span class="sxs-lookup"><span data-stu-id="f6192-156">ObjectWidth</span></span>  <br/> |<span data-ttu-id="f6192-157">化</span><span class="sxs-lookup"><span data-stu-id="f6192-157">xsd:double</span></span>  <br/> |<span data-ttu-id="f6192-158">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-158">optional</span></span>  <br/> ||<span data-ttu-id="f6192-159">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-159">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="f6192-160">ShowAsIcon</span><span class="sxs-lookup"><span data-stu-id="f6192-160">ShowAsIcon</span></span>  <br/> |<span data-ttu-id="f6192-161">化</span><span class="sxs-lookup"><span data-stu-id="f6192-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="f6192-162">可选</span><span class="sxs-lookup"><span data-stu-id="f6192-162">optional</span></span>  <br/> ||<span data-ttu-id="f6192-163">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="f6192-163">Values of the xsd:boolean type.</span></span>  <br/> |
   

