---
title: ForeignData_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 21b394a6-6f95-fc17-482c-4cb648a0d9bb
ms.openlocfilehash: 39396ef0db5b78d6f32d8828103eecd105f8b91d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539861"
---
# <a name="foreigndatatype-complextype-visio-xml"></a><span data-ttu-id="3cb3a-102">ForeignData_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3cb3a-102">ForeignData_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="3cb3a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3cb3a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3cb3a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3cb3a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3cb3a-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="3cb3a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3cb3a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3cb3a-108">无</span><span class="sxs-lookup"><span data-stu-id="3cb3a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3cb3a-109">定义</span><span class="sxs-lookup"><span data-stu-id="3cb3a-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="3cb3a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3cb3a-110">Elements and attributes</span></span>

<span data-ttu-id="3cb3a-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3cb3a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3cb3a-112">Child elements</span></span>

|<span data-ttu-id="3cb3a-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-113">**Element**</span></span>|<span data-ttu-id="3cb3a-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-114">**Type**</span></span>|<span data-ttu-id="3cb3a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3cb3a-116">相对</span><span class="sxs-lookup"><span data-stu-id="3cb3a-116">Rel</span></span>](rel-element-foreigndata_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3cb3a-117">Rel_Type</span><span class="sxs-lookup"><span data-stu-id="3cb3a-117">Rel_Type</span></span>](rel_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="3cb3a-118">属性</span><span class="sxs-lookup"><span data-stu-id="3cb3a-118">Attributes</span></span>

|<span data-ttu-id="3cb3a-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-119">**Attribute**</span></span>|<span data-ttu-id="3cb3a-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-120">**Type**</span></span>|<span data-ttu-id="3cb3a-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-121">**Required**</span></span>|<span data-ttu-id="3cb3a-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-122">**Description**</span></span>|<span data-ttu-id="3cb3a-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cb3a-124">CompressionLevel</span><span class="sxs-lookup"><span data-stu-id="3cb3a-124">CompressionLevel</span></span>  <br/> |<span data-ttu-id="3cb3a-125">xsd: double</span><span class="sxs-lookup"><span data-stu-id="3cb3a-125">xsd:double</span></span>  <br/> |<span data-ttu-id="3cb3a-126">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-126">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-127">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-127">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-128">CompressionType</span><span class="sxs-lookup"><span data-stu-id="3cb3a-128">CompressionType</span></span>  <br/> |<span data-ttu-id="3cb3a-129">xsd: token</span><span class="sxs-lookup"><span data-stu-id="3cb3a-129">xsd:token</span></span>  <br/> |<span data-ttu-id="3cb3a-130">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-130">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-131">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-131">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-132">ExtentX</span><span class="sxs-lookup"><span data-stu-id="3cb3a-132">ExtentX</span></span>  <br/> |<span data-ttu-id="3cb3a-133">xsd: double</span><span class="sxs-lookup"><span data-stu-id="3cb3a-133">xsd:double</span></span>  <br/> |<span data-ttu-id="3cb3a-134">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-134">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-135">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-135">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-136">ExtentY</span><span class="sxs-lookup"><span data-stu-id="3cb3a-136">ExtentY</span></span>  <br/> |<span data-ttu-id="3cb3a-137">xsd: double</span><span class="sxs-lookup"><span data-stu-id="3cb3a-137">xsd:double</span></span>  <br/> |<span data-ttu-id="3cb3a-138">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-138">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-139">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-139">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-140">ForeignType</span><span class="sxs-lookup"><span data-stu-id="3cb3a-140">ForeignType</span></span>  <br/> |<span data-ttu-id="3cb3a-141">xsd: token</span><span class="sxs-lookup"><span data-stu-id="3cb3a-141">xsd:token</span></span>  <br/> |<span data-ttu-id="3cb3a-142">必需</span><span class="sxs-lookup"><span data-stu-id="3cb3a-142">required</span></span>  <br/> ||<span data-ttu-id="3cb3a-143">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-143">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-144">MappingMode</span><span class="sxs-lookup"><span data-stu-id="3cb3a-144">MappingMode</span></span>  <br/> |<span data-ttu-id="3cb3a-145">xsd: unsignedShort</span><span class="sxs-lookup"><span data-stu-id="3cb3a-145">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="3cb3a-146">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-146">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-147">Xsd: unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-147">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-148">ObjectHeight</span><span class="sxs-lookup"><span data-stu-id="3cb3a-148">ObjectHeight</span></span>  <br/> |<span data-ttu-id="3cb3a-149">xsd: double</span><span class="sxs-lookup"><span data-stu-id="3cb3a-149">xsd:double</span></span>  <br/> |<span data-ttu-id="3cb3a-150">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-150">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-151">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-151">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-152">ObjectType</span><span class="sxs-lookup"><span data-stu-id="3cb3a-152">ObjectType</span></span>  <br/> |<span data-ttu-id="3cb3a-153">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3cb3a-153">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3cb3a-154">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-154">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-155">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-156">ObjectWidth</span><span class="sxs-lookup"><span data-stu-id="3cb3a-156">ObjectWidth</span></span>  <br/> |<span data-ttu-id="3cb3a-157">xsd: double</span><span class="sxs-lookup"><span data-stu-id="3cb3a-157">xsd:double</span></span>  <br/> |<span data-ttu-id="3cb3a-158">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-158">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-159">Xsd: double 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-159">Values of the xsd:double type.</span></span>  <br/> |
|<span data-ttu-id="3cb3a-160">ShowAsIcon</span><span class="sxs-lookup"><span data-stu-id="3cb3a-160">ShowAsIcon</span></span>  <br/> |<span data-ttu-id="3cb3a-161">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="3cb3a-161">xsd:boolean</span></span>  <br/> |<span data-ttu-id="3cb3a-162">可选</span><span class="sxs-lookup"><span data-stu-id="3cb3a-162">optional</span></span>  <br/> ||<span data-ttu-id="3cb3a-163">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3cb3a-163">Values of the xsd:boolean type.</span></span>  <br/> |
   

