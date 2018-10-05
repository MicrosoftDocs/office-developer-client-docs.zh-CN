---
title: Cell_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 38519bac-ce3e-9ded-d024-93dd7f34b107
ms.openlocfilehash: ae5f481d787ae5d07968df8cd0ef0eba6af26f9c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389461"
---
# <a name="celltype-complextype-visio-xml"></a><span data-ttu-id="00961-102">Cell_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="00961-102">Cell_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="00961-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="00961-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="00961-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="00961-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="00961-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="00961-105">**Schema file**</span></span> <br/> |<span data-ttu-id="00961-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="00961-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="00961-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="00961-107">**Extension base**</span></span> <br/> |<span data-ttu-id="00961-108">无</span><span class="sxs-lookup"><span data-stu-id="00961-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="00961-109">定义</span><span class="sxs-lookup"><span data-stu-id="00961-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="00961-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="00961-110">Elements and attributes</span></span>

<span data-ttu-id="00961-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="00961-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="00961-112">子元素</span><span class="sxs-lookup"><span data-stu-id="00961-112">Child elements</span></span>

|<span data-ttu-id="00961-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="00961-113">**Element**</span></span>|<span data-ttu-id="00961-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="00961-114">**Type**</span></span>|<span data-ttu-id="00961-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="00961-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="00961-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="00961-116">RefBy</span></span>](refby-element-cell_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="00961-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="00961-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="00961-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="00961-118">Attributes</span></span>

|<span data-ttu-id="00961-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="00961-119">**Attribute**</span></span>|<span data-ttu-id="00961-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="00961-120">**Type**</span></span>|<span data-ttu-id="00961-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="00961-121">**Required**</span></span>|<span data-ttu-id="00961-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="00961-122">**Description**</span></span>|<span data-ttu-id="00961-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="00961-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="00961-124">E</span><span class="sxs-lookup"><span data-stu-id="00961-124">E</span></span>  <br/> |<span data-ttu-id="00961-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="00961-125">xsd:string</span></span>  <br/> |<span data-ttu-id="00961-126">可选</span><span class="sxs-lookup"><span data-stu-id="00961-126">optional</span></span>  <br/> ||<span data-ttu-id="00961-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="00961-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="00961-128">F</span><span class="sxs-lookup"><span data-stu-id="00961-128">F</span></span>  <br/> |<span data-ttu-id="00961-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="00961-129">xsd:string</span></span>  <br/> |<span data-ttu-id="00961-130">可选</span><span class="sxs-lookup"><span data-stu-id="00961-130">optional</span></span>  <br/> ||<span data-ttu-id="00961-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="00961-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="00961-132">N</span><span class="sxs-lookup"><span data-stu-id="00961-132">N</span></span>  <br/> |<span data-ttu-id="00961-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="00961-133">xsd:string</span></span>  <br/> |<span data-ttu-id="00961-134">必需</span><span class="sxs-lookup"><span data-stu-id="00961-134">required</span></span>  <br/> ||<span data-ttu-id="00961-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="00961-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="00961-136">U</span><span class="sxs-lookup"><span data-stu-id="00961-136">U</span></span>  <br/> |<span data-ttu-id="00961-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="00961-137">xsd:string</span></span>  <br/> |<span data-ttu-id="00961-138">可选</span><span class="sxs-lookup"><span data-stu-id="00961-138">optional</span></span>  <br/> ||<span data-ttu-id="00961-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="00961-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="00961-140">V</span><span class="sxs-lookup"><span data-stu-id="00961-140">V</span></span>  <br/> |<span data-ttu-id="00961-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="00961-141">xsd:string</span></span>  <br/> |<span data-ttu-id="00961-142">可选</span><span class="sxs-lookup"><span data-stu-id="00961-142">optional</span></span>  <br/> ||<span data-ttu-id="00961-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="00961-143">Values of the xsd:string type.</span></span>  <br/> |
   

