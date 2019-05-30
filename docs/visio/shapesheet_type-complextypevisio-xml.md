---
title: ShapeSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fb394861-34d7-b7dd-1298-0c68a008528d
ms.openlocfilehash: 0094bc9643cc1331e0b47bd11a59769a553e17f7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542056"
---
# <a name="shapesheettype-complextype-visio-xml"></a><span data-ttu-id="79249-102">ShapeSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="79249-102">ShapeSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="79249-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="79249-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="79249-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="79249-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="79249-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="79249-105">**Schema file**</span></span> <br/> |<span data-ttu-id="79249-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="79249-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="79249-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="79249-107">**Extension base**</span></span> <br/> |<span data-ttu-id="79249-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="79249-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="79249-109">定义</span><span class="sxs-lookup"><span data-stu-id="79249-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="79249-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="79249-110">Elements and attributes</span></span>

<span data-ttu-id="79249-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="79249-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="79249-112">子元素</span><span class="sxs-lookup"><span data-stu-id="79249-112">Child elements</span></span>

|<span data-ttu-id="79249-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="79249-113">**Element**</span></span>|<span data-ttu-id="79249-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="79249-114">**Type**</span></span>|<span data-ttu-id="79249-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="79249-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="79249-116">Data1</span><span class="sxs-lookup"><span data-stu-id="79249-116">Data1</span></span>](data1-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-117">Data_Type</span><span class="sxs-lookup"><span data-stu-id="79249-117">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="79249-118">Data2</span><span class="sxs-lookup"><span data-stu-id="79249-118">Data2</span></span>](data2-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-119">Data_Type</span><span class="sxs-lookup"><span data-stu-id="79249-119">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="79249-120">Data3</span><span class="sxs-lookup"><span data-stu-id="79249-120">Data3</span></span>](data3-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-121">Data_Type</span><span class="sxs-lookup"><span data-stu-id="79249-121">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="79249-122">ForeignData</span><span class="sxs-lookup"><span data-stu-id="79249-122">ForeignData</span></span>](foreigndata-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-123">ForeignData_Type</span><span class="sxs-lookup"><span data-stu-id="79249-123">ForeignData_Type</span></span>](foreigndata_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="79249-124">Shapes</span><span class="sxs-lookup"><span data-stu-id="79249-124">Shapes</span></span>](shapes-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-125">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="79249-125">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="79249-126">Text</span><span class="sxs-lookup"><span data-stu-id="79249-126">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="79249-127">Text_Type</span><span class="sxs-lookup"><span data-stu-id="79249-127">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="79249-128">属性</span><span class="sxs-lookup"><span data-stu-id="79249-128">Attributes</span></span>

|<span data-ttu-id="79249-129">**属性**</span><span class="sxs-lookup"><span data-stu-id="79249-129">**Attribute**</span></span>|<span data-ttu-id="79249-130">**类型**</span><span class="sxs-lookup"><span data-stu-id="79249-130">**Type**</span></span>|<span data-ttu-id="79249-131">**必需**</span><span class="sxs-lookup"><span data-stu-id="79249-131">**Required**</span></span>|<span data-ttu-id="79249-132">**描述**</span><span class="sxs-lookup"><span data-stu-id="79249-132">**Description**</span></span>|<span data-ttu-id="79249-133">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="79249-133">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79249-134">键</span><span class="sxs-lookup"><span data-stu-id="79249-134">Del</span></span>  <br/> |<span data-ttu-id="79249-135">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="79249-135">xsd:boolean</span></span>  <br/> |<span data-ttu-id="79249-136">可选</span><span class="sxs-lookup"><span data-stu-id="79249-136">optional</span></span>  <br/> ||<span data-ttu-id="79249-137">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-137">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="79249-138">ID</span><span class="sxs-lookup"><span data-stu-id="79249-138">ID</span></span>  <br/> |<span data-ttu-id="79249-139">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="79249-139">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="79249-140">必需</span><span class="sxs-lookup"><span data-stu-id="79249-140">required</span></span>  <br/> ||<span data-ttu-id="79249-141">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-141">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="79249-142">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="79249-142">IsCustomName</span></span>  <br/> |<span data-ttu-id="79249-143">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="79249-143">xsd:boolean</span></span>  <br/> |<span data-ttu-id="79249-144">可选</span><span class="sxs-lookup"><span data-stu-id="79249-144">optional</span></span>  <br/> ||<span data-ttu-id="79249-145">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-145">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="79249-146">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="79249-146">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="79249-147">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="79249-147">xsd:boolean</span></span>  <br/> |<span data-ttu-id="79249-148">可选</span><span class="sxs-lookup"><span data-stu-id="79249-148">optional</span></span>  <br/> ||<span data-ttu-id="79249-149">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-149">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="79249-150">Master</span><span class="sxs-lookup"><span data-stu-id="79249-150">Master</span></span>  <br/> |<span data-ttu-id="79249-151">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="79249-151">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="79249-152">可选</span><span class="sxs-lookup"><span data-stu-id="79249-152">optional</span></span>  <br/> ||<span data-ttu-id="79249-153">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-153">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="79249-154">MasterShape</span><span class="sxs-lookup"><span data-stu-id="79249-154">MasterShape</span></span>  <br/> |<span data-ttu-id="79249-155">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="79249-155">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="79249-156">可选</span><span class="sxs-lookup"><span data-stu-id="79249-156">optional</span></span>  <br/> ||<span data-ttu-id="79249-157">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-157">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="79249-158">名称</span><span class="sxs-lookup"><span data-stu-id="79249-158">Name</span></span>  <br/> |<span data-ttu-id="79249-159">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79249-159">xsd:string</span></span>  <br/> |<span data-ttu-id="79249-160">可选</span><span class="sxs-lookup"><span data-stu-id="79249-160">optional</span></span>  <br/> ||<span data-ttu-id="79249-161">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79249-162">NameU</span><span class="sxs-lookup"><span data-stu-id="79249-162">NameU</span></span>  <br/> |<span data-ttu-id="79249-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79249-163">xsd:string</span></span>  <br/> |<span data-ttu-id="79249-164">可选</span><span class="sxs-lookup"><span data-stu-id="79249-164">optional</span></span>  <br/> ||<span data-ttu-id="79249-165">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-165">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79249-166">OriginalID</span><span class="sxs-lookup"><span data-stu-id="79249-166">OriginalID</span></span>  <br/> |<span data-ttu-id="79249-167">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="79249-167">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="79249-168">可选</span><span class="sxs-lookup"><span data-stu-id="79249-168">optional</span></span>  <br/> ||<span data-ttu-id="79249-169">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-169">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="79249-170">类型</span><span class="sxs-lookup"><span data-stu-id="79249-170">Type</span></span>  <br/> |<span data-ttu-id="79249-171">xsd: token</span><span class="sxs-lookup"><span data-stu-id="79249-171">xsd:token</span></span>  <br/> |<span data-ttu-id="79249-172">可选</span><span class="sxs-lookup"><span data-stu-id="79249-172">optional</span></span>  <br/> ||<span data-ttu-id="79249-173">Xsd: 令牌类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-173">Values of the xsd:token type.</span></span>  <br/> |
|<span data-ttu-id="79249-174">UniqueID</span><span class="sxs-lookup"><span data-stu-id="79249-174">UniqueID</span></span>  <br/> |<span data-ttu-id="79249-175">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79249-175">xsd:string</span></span>  <br/> |<span data-ttu-id="79249-176">可选</span><span class="sxs-lookup"><span data-stu-id="79249-176">optional</span></span>  <br/> ||<span data-ttu-id="79249-177">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79249-177">Values of the xsd:string type.</span></span>  <br/> |
   

