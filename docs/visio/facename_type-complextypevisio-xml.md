---
title: FaceName_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d24f350c-35bf-ab16-2469-39fd5344e5fe
ms.openlocfilehash: 8035f541e619360403336bd2fbd931cf05dbfe59
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382440"
---
# <a name="facenametype-complextype-visio-xml"></a><span data-ttu-id="79a67-102">FaceName_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="79a67-102">FaceName_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="79a67-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="79a67-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="79a67-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="79a67-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="79a67-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="79a67-105">**Schema file**</span></span> <br/> |<span data-ttu-id="79a67-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="79a67-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="79a67-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="79a67-107">**Extension base**</span></span> <br/> |<span data-ttu-id="79a67-108">无</span><span class="sxs-lookup"><span data-stu-id="79a67-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="79a67-109">定义</span><span class="sxs-lookup"><span data-stu-id="79a67-109">Definition</span></span>

```XML
      <xs:complexType name="FaceName_Type">
    <xs:attribute name="NameU"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="UnicodeRanges"
  type="xsd:string"
    />
    <xs:attribute name="CharSets"
  type="xsd:string"
    />
    <xs:attribute name="Panos"
  type="xsd:string"
    />
    <xs:attribute name="Panose"
  type="xsd:string"
    />
    <xs:attribute name="Flags"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="79a67-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="79a67-110">Elements and attributes</span></span>

<span data-ttu-id="79a67-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="79a67-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="79a67-112">子元素</span><span class="sxs-lookup"><span data-stu-id="79a67-112">Child elements</span></span>

<span data-ttu-id="79a67-113">无。</span><span class="sxs-lookup"><span data-stu-id="79a67-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="79a67-114">属性</span><span class="sxs-lookup"><span data-stu-id="79a67-114">Attributes</span></span>

|<span data-ttu-id="79a67-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="79a67-115">**Attribute**</span></span>|<span data-ttu-id="79a67-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="79a67-116">**Type**</span></span>|<span data-ttu-id="79a67-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="79a67-117">**Required**</span></span>|<span data-ttu-id="79a67-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="79a67-118">**Description**</span></span>|<span data-ttu-id="79a67-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="79a67-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="79a67-120">CharSets</span><span class="sxs-lookup"><span data-stu-id="79a67-120">CharSets</span></span>  <br/> |<span data-ttu-id="79a67-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79a67-121">xsd:string</span></span>  <br/> |<span data-ttu-id="79a67-122">可选</span><span class="sxs-lookup"><span data-stu-id="79a67-122">optional</span></span>  <br/> ||<span data-ttu-id="79a67-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79a67-124">Flags</span><span class="sxs-lookup"><span data-stu-id="79a67-124">Flags</span></span>  <br/> |<span data-ttu-id="79a67-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="79a67-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="79a67-126">可选</span><span class="sxs-lookup"><span data-stu-id="79a67-126">optional</span></span>  <br/> ||<span data-ttu-id="79a67-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="79a67-128">NameU</span><span class="sxs-lookup"><span data-stu-id="79a67-128">NameU</span></span>  <br/> |<span data-ttu-id="79a67-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79a67-129">xsd:string</span></span>  <br/> |<span data-ttu-id="79a67-130">必需</span><span class="sxs-lookup"><span data-stu-id="79a67-130">required</span></span>  <br/> ||<span data-ttu-id="79a67-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79a67-132">Panos</span><span class="sxs-lookup"><span data-stu-id="79a67-132">Panos</span></span>  <br/> |<span data-ttu-id="79a67-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79a67-133">xsd:string</span></span>  <br/> |<span data-ttu-id="79a67-134">可选</span><span class="sxs-lookup"><span data-stu-id="79a67-134">optional</span></span>  <br/> ||<span data-ttu-id="79a67-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79a67-136">Panose</span><span class="sxs-lookup"><span data-stu-id="79a67-136">Panose</span></span>  <br/> |<span data-ttu-id="79a67-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79a67-137">xsd:string</span></span>  <br/> |<span data-ttu-id="79a67-138">可选</span><span class="sxs-lookup"><span data-stu-id="79a67-138">optional</span></span>  <br/> ||<span data-ttu-id="79a67-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="79a67-140">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="79a67-140">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="79a67-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="79a67-141">xsd:string</span></span>  <br/> |<span data-ttu-id="79a67-142">可选</span><span class="sxs-lookup"><span data-stu-id="79a67-142">optional</span></span>  <br/> ||<span data-ttu-id="79a67-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="79a67-143">Values of the xsd:string type.</span></span>  <br/> |
   

