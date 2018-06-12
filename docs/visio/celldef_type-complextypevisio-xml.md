---
title: CellDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 87ea346d-1786-dc87-073d-8e7459b7fef1
ms.openlocfilehash: 6471158df8c89e8d7b0202f9bdbce196e24b93b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779846"
---
# <a name="celldeftype-complextype-visio-xml"></a><span data-ttu-id="d486b-102">CellDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d486b-102">CellDef_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="d486b-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d486b-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d486b-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d486b-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d486b-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d486b-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d486b-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="d486b-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d486b-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d486b-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d486b-108">无</span><span class="sxs-lookup"><span data-stu-id="d486b-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d486b-109">定义</span><span class="sxs-lookup"><span data-stu-id="d486b-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d486b-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d486b-110">Elements and attributes</span></span>

<span data-ttu-id="d486b-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d486b-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d486b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d486b-112">Child elements</span></span>

<span data-ttu-id="d486b-113">无。</span><span class="sxs-lookup"><span data-stu-id="d486b-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d486b-114">属性</span><span class="sxs-lookup"><span data-stu-id="d486b-114">Attributes</span></span>

|<span data-ttu-id="d486b-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="d486b-115">**Attribute**</span></span>|<span data-ttu-id="d486b-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="d486b-116">**Type**</span></span>|<span data-ttu-id="d486b-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="d486b-117">**Required**</span></span>|<span data-ttu-id="d486b-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="d486b-118">**Description**</span></span>|<span data-ttu-id="d486b-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d486b-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d486b-120">F</span><span class="sxs-lookup"><span data-stu-id="d486b-120">F</span></span>  <br/> |<span data-ttu-id="d486b-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d486b-121">xsd:string</span></span>  <br/> |<span data-ttu-id="d486b-122">可选</span><span class="sxs-lookup"><span data-stu-id="d486b-122">optional</span></span>  <br/> ||<span data-ttu-id="d486b-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d486b-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d486b-124">IX</span><span class="sxs-lookup"><span data-stu-id="d486b-124">IX</span></span>  <br/> |<span data-ttu-id="d486b-125">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="d486b-125">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="d486b-126">可选</span><span class="sxs-lookup"><span data-stu-id="d486b-126">optional</span></span>  <br/> ||<span data-ttu-id="d486b-127">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d486b-127">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="d486b-128">N</span><span class="sxs-lookup"><span data-stu-id="d486b-128">N</span></span>  <br/> |<span data-ttu-id="d486b-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d486b-129">xsd:string</span></span>  <br/> |<span data-ttu-id="d486b-130">必需</span><span class="sxs-lookup"><span data-stu-id="d486b-130">required</span></span>  <br/> ||<span data-ttu-id="d486b-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d486b-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d486b-132">S</span><span class="sxs-lookup"><span data-stu-id="d486b-132">S</span></span>  <br/> |<span data-ttu-id="d486b-133">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="d486b-133">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="d486b-134">可选</span><span class="sxs-lookup"><span data-stu-id="d486b-134">optional</span></span>  <br/> ||<span data-ttu-id="d486b-135">Xsd:unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d486b-135">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="d486b-136">T</span><span class="sxs-lookup"><span data-stu-id="d486b-136">T</span></span>  <br/> |<span data-ttu-id="d486b-137">xsd:token</span><span class="sxs-lookup"><span data-stu-id="d486b-137">xsd:token</span></span>  <br/> |<span data-ttu-id="d486b-138">必需</span><span class="sxs-lookup"><span data-stu-id="d486b-138">required</span></span>  <br/> ||<span data-ttu-id="d486b-139">Xsd:token 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d486b-139">Values of the xsd:token type.</span></span>  <br/> |
   

