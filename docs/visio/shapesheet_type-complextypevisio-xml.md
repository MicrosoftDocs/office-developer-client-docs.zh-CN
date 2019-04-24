---
title: ShapeSheet_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fb394861-34d7-b7dd-1298-0c68a008528d
ms.openlocfilehash: c48af0def561e01fe5a92a57b7416faab40f1200
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349131"
---
# <a name="shapesheettype-complextype-visio-xml"></a><span data-ttu-id="62997-102">ShapeSheet_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="62997-102">ShapeSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="62997-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="62997-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="62997-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="62997-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="62997-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="62997-105">**Schema file**</span></span> <br/> |<span data-ttu-id="62997-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="62997-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="62997-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="62997-107">**Extension base**</span></span> <br/> |<span data-ttu-id="62997-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="62997-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="62997-109">定义</span><span class="sxs-lookup"><span data-stu-id="62997-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="62997-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="62997-110">Elements and attributes</span></span>

<span data-ttu-id="62997-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="62997-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="62997-112">子元素</span><span class="sxs-lookup"><span data-stu-id="62997-112">Child elements</span></span>

|<span data-ttu-id="62997-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="62997-113">**Element**</span></span>|<span data-ttu-id="62997-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="62997-114">**Type**</span></span>|<span data-ttu-id="62997-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="62997-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="62997-116">Data1</span><span class="sxs-lookup"><span data-stu-id="62997-116">Data1</span></span>](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-117">Data_Type</span><span class="sxs-lookup"><span data-stu-id="62997-117">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="62997-118">Data2</span><span class="sxs-lookup"><span data-stu-id="62997-118">Data2</span></span>](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-119">Data_Type</span><span class="sxs-lookup"><span data-stu-id="62997-119">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="62997-120">Data3</span><span class="sxs-lookup"><span data-stu-id="62997-120">Data3</span></span>](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-121">Data_Type</span><span class="sxs-lookup"><span data-stu-id="62997-121">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="62997-122">ForeignData</span><span class="sxs-lookup"><span data-stu-id="62997-122">ForeignData</span></span>](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-123">ForeignData_Type</span><span class="sxs-lookup"><span data-stu-id="62997-123">ForeignData_Type</span></span>](foreigndata_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="62997-124">Shapes</span><span class="sxs-lookup"><span data-stu-id="62997-124">Shapes</span></span>](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-125">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="62997-125">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="62997-126">Text</span><span class="sxs-lookup"><span data-stu-id="62997-126">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="62997-127">Text_Type</span><span class="sxs-lookup"><span data-stu-id="62997-127">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="62997-128">属性</span><span class="sxs-lookup"><span data-stu-id="62997-128">Attributes</span></span>

|<span data-ttu-id="62997-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="62997-129">**Attribute**</span></span>|<span data-ttu-id="62997-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="62997-130">**Type**</span></span>|<span data-ttu-id="62997-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="62997-131">**Required**</span></span>|<span data-ttu-id="62997-132">**描述**</span><span class="sxs-lookup"><span data-stu-id="62997-132">**Description**</span></span>|<span data-ttu-id="62997-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="62997-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62997-134">键</span><span class="sxs-lookup"><span data-stu-id="62997-134">Del</span></span>  <br/> |<span data-ttu-id="62997-135">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="62997-135">xsd:boolean</span></span>  <br/> |<span data-ttu-id="62997-136">可选</span><span class="sxs-lookup"><span data-stu-id="62997-136">optional</span></span>  <br/> ||<span data-ttu-id="62997-137">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-137">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="62997-138">ID</span><span class="sxs-lookup"><span data-stu-id="62997-138">ID</span></span>  <br/> |<span data-ttu-id="62997-139">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="62997-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="62997-140">必需</span><span class="sxs-lookup"><span data-stu-id="62997-140">required</span></span>  <br/> ||<span data-ttu-id="62997-141">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="62997-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="62997-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="62997-143">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="62997-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="62997-144">可选</span><span class="sxs-lookup"><span data-stu-id="62997-144">optional</span></span>  <br/> ||<span data-ttu-id="62997-145">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="62997-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="62997-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="62997-147">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="62997-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="62997-148">可选</span><span class="sxs-lookup"><span data-stu-id="62997-148">optional</span></span>  <br/> ||<span data-ttu-id="62997-149">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="62997-150">Master</span><span class="sxs-lookup"><span data-stu-id="62997-150">Master</span></span>  <br/> |<span data-ttu-id="62997-151">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="62997-151">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="62997-152">可选</span><span class="sxs-lookup"><span data-stu-id="62997-152">optional</span></span>  <br/> ||<span data-ttu-id="62997-153">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-153">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="62997-154">MasterShape</span><span class="sxs-lookup"><span data-stu-id="62997-154">MasterShape</span></span>  <br/> |<span data-ttu-id="62997-155">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="62997-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="62997-156">可选</span><span class="sxs-lookup"><span data-stu-id="62997-156">optional</span></span>  <br/> ||<span data-ttu-id="62997-157">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="62997-158">名称</span><span class="sxs-lookup"><span data-stu-id="62997-158">Name</span></span>  <br/> |<span data-ttu-id="62997-159">xsd: string</span><span class="sxs-lookup"><span data-stu-id="62997-159">xsd:string</span></span>  <br/> |<span data-ttu-id="62997-160">可选</span><span class="sxs-lookup"><span data-stu-id="62997-160">optional</span></span>  <br/> ||<span data-ttu-id="62997-161">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="62997-162">NameU</span><span class="sxs-lookup"><span data-stu-id="62997-162">NameU</span></span>  <br/> |<span data-ttu-id="62997-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="62997-163">xsd:string</span></span>  <br/> |<span data-ttu-id="62997-164">可选</span><span class="sxs-lookup"><span data-stu-id="62997-164">optional</span></span>  <br/> ||<span data-ttu-id="62997-165">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-165">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="62997-166">OriginalID</span><span class="sxs-lookup"><span data-stu-id="62997-166">OriginalID</span></span>  <br/> |<span data-ttu-id="62997-167">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="62997-167">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="62997-168">可选</span><span class="sxs-lookup"><span data-stu-id="62997-168">optional</span></span>  <br/> ||<span data-ttu-id="62997-169">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-169">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="62997-170">类型</span><span class="sxs-lookup"><span data-stu-id="62997-170">Type</span></span>  <br/> |<span data-ttu-id="62997-171">xsd: token</span><span class="sxs-lookup"><span data-stu-id="62997-171">xsd:token</span></span>  <br/> |<span data-ttu-id="62997-172">可选</span><span class="sxs-lookup"><span data-stu-id="62997-172">optional</span></span>  <br/> ||<span data-ttu-id="62997-173">xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-173">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="62997-174">UniqueID</span><span class="sxs-lookup"><span data-stu-id="62997-174">UniqueID</span></span>  <br/> |<span data-ttu-id="62997-175">xsd: string</span><span class="sxs-lookup"><span data-stu-id="62997-175">xsd:string</span></span>  <br/> |<span data-ttu-id="62997-176">可选</span><span class="sxs-lookup"><span data-stu-id="62997-176">optional</span></span>  <br/> ||<span data-ttu-id="62997-177">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="62997-177">Values of the xsd:string type.</span></span>  <br/> |
   

