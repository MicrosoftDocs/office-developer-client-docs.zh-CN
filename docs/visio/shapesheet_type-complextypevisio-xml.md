---
title: ShapeSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fb394861-34d7-b7dd-1298-0c68a008528d
ms.openlocfilehash: c48af0def561e01fe5a92a57b7416faab40f1200
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383630"
---
# <a name="shapesheettype-complextype-visio-xml"></a><span data-ttu-id="dee79-102">ShapeSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="dee79-102">ShapeSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="dee79-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="dee79-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dee79-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="dee79-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="dee79-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="dee79-105">**Schema file**</span></span> <br/> |<span data-ttu-id="dee79-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="dee79-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="dee79-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="dee79-107">**Extension base**</span></span> <br/> |<span data-ttu-id="dee79-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="dee79-109">定义</span><span class="sxs-lookup"><span data-stu-id="dee79-109">Definition</span></span>

```XML
          <xs:complexType name="ShapeSheet_Type">
          
          <xs:complexContent>
          <xs:extension base="Sheet_Type">
          <xs:sequence>
    <xs:element name="Shapes"  type="Shapes_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Text"  type="Text_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Data1"  type="Data_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Data2"  type="Data_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Data3"  type="Data_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="ForeignData"  type="ForeignData_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="OriginalID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
    <xs:attribute name="MasterShape"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="UniqueID"
  type="xsd:string"
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
    <xs:attribute name="Master"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="Type"
  type="xsd:token"
    />
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="dee79-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="dee79-110">Elements and attributes</span></span>

<span data-ttu-id="dee79-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="dee79-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="dee79-112">子元素</span><span class="sxs-lookup"><span data-stu-id="dee79-112">Child elements</span></span>

|<span data-ttu-id="dee79-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="dee79-113">**Element**</span></span>|<span data-ttu-id="dee79-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="dee79-114">**Type**</span></span>|<span data-ttu-id="dee79-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="dee79-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="dee79-116">Data1</span><span class="sxs-lookup"><span data-stu-id="dee79-116">Data1</span></span>](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-117">Data_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-117">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="dee79-118">Data2</span><span class="sxs-lookup"><span data-stu-id="dee79-118">Data2</span></span>](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-119">Data_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-119">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="dee79-120">Data3</span><span class="sxs-lookup"><span data-stu-id="dee79-120">Data3</span></span>](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-121">Data_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-121">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="dee79-122">ForeignData</span><span class="sxs-lookup"><span data-stu-id="dee79-122">ForeignData</span></span>](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-123">ForeignData_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-123">ForeignData_Type</span></span>](foreigndata_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="dee79-124">Shapes</span><span class="sxs-lookup"><span data-stu-id="dee79-124">Shapes</span></span>](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-125">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-125">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="dee79-126">Text</span><span class="sxs-lookup"><span data-stu-id="dee79-126">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="dee79-127">Text_Type</span><span class="sxs-lookup"><span data-stu-id="dee79-127">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="dee79-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="dee79-128">Attributes</span></span>

|<span data-ttu-id="dee79-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="dee79-129">**Attribute**</span></span>|<span data-ttu-id="dee79-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="dee79-130">**Type**</span></span>|<span data-ttu-id="dee79-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="dee79-131">**Required**</span></span>|<span data-ttu-id="dee79-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="dee79-132">**Description**</span></span>|<span data-ttu-id="dee79-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="dee79-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dee79-134">Del</span><span class="sxs-lookup"><span data-stu-id="dee79-134">Del</span></span>  <br/> |<span data-ttu-id="dee79-135">化</span><span class="sxs-lookup"><span data-stu-id="dee79-135">xsd:boolean</span></span>  <br/> |<span data-ttu-id="dee79-136">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-136">optional</span></span>  <br/> ||<span data-ttu-id="dee79-137">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-137">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="dee79-138">ID</span><span class="sxs-lookup"><span data-stu-id="dee79-138">ID</span></span>  <br/> |<span data-ttu-id="dee79-139">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dee79-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dee79-140">必需</span><span class="sxs-lookup"><span data-stu-id="dee79-140">required</span></span>  <br/> ||<span data-ttu-id="dee79-141">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="dee79-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="dee79-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="dee79-143">化</span><span class="sxs-lookup"><span data-stu-id="dee79-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="dee79-144">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-144">optional</span></span>  <br/> ||<span data-ttu-id="dee79-145">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="dee79-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="dee79-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="dee79-147">化</span><span class="sxs-lookup"><span data-stu-id="dee79-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="dee79-148">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-148">optional</span></span>  <br/> ||<span data-ttu-id="dee79-149">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="dee79-150">Master</span><span class="sxs-lookup"><span data-stu-id="dee79-150">Master</span></span>  <br/> |<span data-ttu-id="dee79-151">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dee79-151">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dee79-152">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-152">optional</span></span>  <br/> ||<span data-ttu-id="dee79-153">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-153">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="dee79-154">MasterShape</span><span class="sxs-lookup"><span data-stu-id="dee79-154">MasterShape</span></span>  <br/> |<span data-ttu-id="dee79-155">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dee79-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dee79-156">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-156">optional</span></span>  <br/> ||<span data-ttu-id="dee79-157">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="dee79-158">名称</span><span class="sxs-lookup"><span data-stu-id="dee79-158">Name</span></span>  <br/> |<span data-ttu-id="dee79-159">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dee79-159">xsd:string</span></span>  <br/> |<span data-ttu-id="dee79-160">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-160">optional</span></span>  <br/> ||<span data-ttu-id="dee79-161">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="dee79-162">NameU</span><span class="sxs-lookup"><span data-stu-id="dee79-162">NameU</span></span>  <br/> |<span data-ttu-id="dee79-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dee79-163">xsd:string</span></span>  <br/> |<span data-ttu-id="dee79-164">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-164">optional</span></span>  <br/> ||<span data-ttu-id="dee79-165">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-165">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="dee79-166">OriginalID</span><span class="sxs-lookup"><span data-stu-id="dee79-166">OriginalID</span></span>  <br/> |<span data-ttu-id="dee79-167">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="dee79-167">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="dee79-168">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-168">optional</span></span>  <br/> ||<span data-ttu-id="dee79-169">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-169">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="dee79-170">类型</span><span class="sxs-lookup"><span data-stu-id="dee79-170">Type</span></span>  <br/> |<span data-ttu-id="dee79-171">xsd:token</span><span class="sxs-lookup"><span data-stu-id="dee79-171">xsd:token</span></span>  <br/> |<span data-ttu-id="dee79-172">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-172">optional</span></span>  <br/> ||<span data-ttu-id="dee79-173">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-173">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="dee79-174">UniqueID</span><span class="sxs-lookup"><span data-stu-id="dee79-174">UniqueID</span></span>  <br/> |<span data-ttu-id="dee79-175">xsd: string</span><span class="sxs-lookup"><span data-stu-id="dee79-175">xsd:string</span></span>  <br/> |<span data-ttu-id="dee79-176">可选</span><span class="sxs-lookup"><span data-stu-id="dee79-176">optional</span></span>  <br/> ||<span data-ttu-id="dee79-177">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="dee79-177">Values of the xsd:string type.</span></span>  <br/> |
   

