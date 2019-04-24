---
title: Cell_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 38519bac-ce3e-9ded-d024-93dd7f34b107
ms.openlocfilehash: ae5f481d787ae5d07968df8cd0ef0eba6af26f9c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327116"
---
# <a name="celltype-complextype-visio-xml"></a><span data-ttu-id="91a8d-102">Cell_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="91a8d-102">Cell_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="91a8d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="91a8d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="91a8d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="91a8d-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="91a8d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="91a8d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="91a8d-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="91a8d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="91a8d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="91a8d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="91a8d-108">无</span><span class="sxs-lookup"><span data-stu-id="91a8d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="91a8d-109">定义</span><span class="sxs-lookup"><span data-stu-id="91a8d-109">Definition</span></span>

```XML
          <xs:complexType name="Cell_Type">
          
          <xs:sequence>
    <xs:element name="RefBy"  type="RefBy_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="U"
  type="xsd:string"
    />
    <xs:attribute name="E"
  type="xsd:string"
    />
    <xs:attribute name="F"
  type="xsd:string"
    />
    <xs:attribute name="V"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="91a8d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="91a8d-110">Elements and attributes</span></span>

<span data-ttu-id="91a8d-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="91a8d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="91a8d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="91a8d-112">Child elements</span></span>

|<span data-ttu-id="91a8d-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="91a8d-113">**Element**</span></span>|<span data-ttu-id="91a8d-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="91a8d-114">**Type**</span></span>|<span data-ttu-id="91a8d-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="91a8d-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="91a8d-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="91a8d-116">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="91a8d-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="91a8d-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="91a8d-118">属性</span><span class="sxs-lookup"><span data-stu-id="91a8d-118">Attributes</span></span>

|<span data-ttu-id="91a8d-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="91a8d-119">**Attribute**</span></span>|<span data-ttu-id="91a8d-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="91a8d-120">**Type**</span></span>|<span data-ttu-id="91a8d-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="91a8d-121">**Required**</span></span>|<span data-ttu-id="91a8d-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="91a8d-122">**Description**</span></span>|<span data-ttu-id="91a8d-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="91a8d-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91a8d-124">E</span><span class="sxs-lookup"><span data-stu-id="91a8d-124">E</span></span>  <br/> |<span data-ttu-id="91a8d-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91a8d-125">xsd:string</span></span>  <br/> |<span data-ttu-id="91a8d-126">可选</span><span class="sxs-lookup"><span data-stu-id="91a8d-126">optional</span></span>  <br/> ||<span data-ttu-id="91a8d-127">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a8d-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91a8d-128">F</span><span class="sxs-lookup"><span data-stu-id="91a8d-128">F</span></span>  <br/> |<span data-ttu-id="91a8d-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91a8d-129">xsd:string</span></span>  <br/> |<span data-ttu-id="91a8d-130">可选</span><span class="sxs-lookup"><span data-stu-id="91a8d-130">optional</span></span>  <br/> ||<span data-ttu-id="91a8d-131">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a8d-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91a8d-132">N</span><span class="sxs-lookup"><span data-stu-id="91a8d-132">N</span></span>  <br/> |<span data-ttu-id="91a8d-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91a8d-133">xsd:string</span></span>  <br/> |<span data-ttu-id="91a8d-134">必需</span><span class="sxs-lookup"><span data-stu-id="91a8d-134">required</span></span>  <br/> ||<span data-ttu-id="91a8d-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a8d-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91a8d-136">U</span><span class="sxs-lookup"><span data-stu-id="91a8d-136">U</span></span>  <br/> |<span data-ttu-id="91a8d-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91a8d-137">xsd:string</span></span>  <br/> |<span data-ttu-id="91a8d-138">可选</span><span class="sxs-lookup"><span data-stu-id="91a8d-138">optional</span></span>  <br/> ||<span data-ttu-id="91a8d-139">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a8d-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="91a8d-140">部分</span><span class="sxs-lookup"><span data-stu-id="91a8d-140">V</span></span>  <br/> |<span data-ttu-id="91a8d-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="91a8d-141">xsd:string</span></span>  <br/> |<span data-ttu-id="91a8d-142">可选</span><span class="sxs-lookup"><span data-stu-id="91a8d-142">optional</span></span>  <br/> ||<span data-ttu-id="91a8d-143">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="91a8d-143">Values of the xsd:string type.</span></span>  <br/> |
   

