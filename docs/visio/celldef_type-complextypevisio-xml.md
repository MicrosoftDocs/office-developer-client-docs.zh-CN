---
title: CellDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ea346d-1786-dc87-073d-8e7459b7fef1
ms.openlocfilehash: bdcfadc36f278fc97b8589b2989d214e5f4b3333
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399982"
---
# <a name="celldeftype-complextype-visio-xml"></a><span data-ttu-id="0124f-102">CellDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0124f-102">CellDef_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="0124f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0124f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0124f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0124f-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0124f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0124f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0124f-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="0124f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0124f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0124f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0124f-108">无</span><span class="sxs-lookup"><span data-stu-id="0124f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0124f-109">定义</span><span class="sxs-lookup"><span data-stu-id="0124f-109">Definition</span></span>

```XML
      <xs:complexType name="CellDef_Type">
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:token"
     use="required"
    />
    <xs:attribute name="F"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedByte"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0124f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0124f-110">Elements and attributes</span></span>

<span data-ttu-id="0124f-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0124f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0124f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0124f-112">Child elements</span></span>

<span data-ttu-id="0124f-113">无。</span><span class="sxs-lookup"><span data-stu-id="0124f-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0124f-114">属性</span><span class="sxs-lookup"><span data-stu-id="0124f-114">Attributes</span></span>

|<span data-ttu-id="0124f-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="0124f-115">**Attribute**</span></span>|<span data-ttu-id="0124f-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="0124f-116">**Type**</span></span>|<span data-ttu-id="0124f-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="0124f-117">**Required**</span></span>|<span data-ttu-id="0124f-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="0124f-118">**Description**</span></span>|<span data-ttu-id="0124f-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0124f-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0124f-120">F</span><span class="sxs-lookup"><span data-stu-id="0124f-120">F</span></span>  <br/> |<span data-ttu-id="0124f-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0124f-121">xsd:string</span></span>  <br/> |<span data-ttu-id="0124f-122">可选</span><span class="sxs-lookup"><span data-stu-id="0124f-122">optional</span></span>  <br/> ||<span data-ttu-id="0124f-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0124f-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0124f-124">IX</span><span class="sxs-lookup"><span data-stu-id="0124f-124">IX</span></span>  <br/> |<span data-ttu-id="0124f-125">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0124f-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0124f-126">可选</span><span class="sxs-lookup"><span data-stu-id="0124f-126">optional</span></span>  <br/> ||<span data-ttu-id="0124f-127">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0124f-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0124f-128">N</span><span class="sxs-lookup"><span data-stu-id="0124f-128">N</span></span>  <br/> |<span data-ttu-id="0124f-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0124f-129">xsd:string</span></span>  <br/> |<span data-ttu-id="0124f-130">必需</span><span class="sxs-lookup"><span data-stu-id="0124f-130">required</span></span>  <br/> ||<span data-ttu-id="0124f-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0124f-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="0124f-132">S</span><span class="sxs-lookup"><span data-stu-id="0124f-132">S</span></span>  <br/> |<span data-ttu-id="0124f-133">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0124f-133">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="0124f-134">可选</span><span class="sxs-lookup"><span data-stu-id="0124f-134">optional</span></span>  <br/> ||<span data-ttu-id="0124f-135">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0124f-135">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="0124f-136">T</span><span class="sxs-lookup"><span data-stu-id="0124f-136">T</span></span>  <br/> |<span data-ttu-id="0124f-137">xsd:token</span><span class="sxs-lookup"><span data-stu-id="0124f-137">xsd:token</span></span>  <br/> |<span data-ttu-id="0124f-138">必需</span><span class="sxs-lookup"><span data-stu-id="0124f-138">required</span></span>  <br/> ||<span data-ttu-id="0124f-139">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0124f-139">Values of the xsd:token type.</span></span>  <br/> |
   

