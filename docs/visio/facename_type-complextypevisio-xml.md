---
title: FaceName_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d24f350c-35bf-ab16-2469-39fd5344e5fe
ms.openlocfilehash: 554a8144fd38c34d59aa2fd0ae25d171c20cd8ba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780212"
---
# <a name="facenametype-complextype-visio-xml"></a><span data-ttu-id="e5cf9-102">FaceName_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e5cf9-102">FaceName_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="e5cf9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e5cf9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e5cf9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e5cf9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e5cf9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="e5cf9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e5cf9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e5cf9-108">无</span><span class="sxs-lookup"><span data-stu-id="e5cf9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e5cf9-109">定义</span><span class="sxs-lookup"><span data-stu-id="e5cf9-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="e5cf9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e5cf9-110">Elements and attributes</span></span>

<span data-ttu-id="e5cf9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e5cf9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e5cf9-112">Child elements</span></span>

<span data-ttu-id="e5cf9-113">无。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e5cf9-114">属性</span><span class="sxs-lookup"><span data-stu-id="e5cf9-114">Attributes</span></span>

|<span data-ttu-id="e5cf9-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-115">**Attribute**</span></span>|<span data-ttu-id="e5cf9-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-116">**Type**</span></span>|<span data-ttu-id="e5cf9-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-117">**Required**</span></span>|<span data-ttu-id="e5cf9-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-118">**Description**</span></span>|<span data-ttu-id="e5cf9-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e5cf9-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5cf9-120">CharSets</span><span class="sxs-lookup"><span data-stu-id="e5cf9-120">CharSets</span></span>  <br/> |<span data-ttu-id="e5cf9-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e5cf9-121">xsd:string</span></span>  <br/> |<span data-ttu-id="e5cf9-122">可选</span><span class="sxs-lookup"><span data-stu-id="e5cf9-122">optional</span></span>  <br/> ||<span data-ttu-id="e5cf9-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e5cf9-124">标志</span><span class="sxs-lookup"><span data-stu-id="e5cf9-124">Flags</span></span>  <br/> |<span data-ttu-id="e5cf9-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e5cf9-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e5cf9-126">可选</span><span class="sxs-lookup"><span data-stu-id="e5cf9-126">optional</span></span>  <br/> ||<span data-ttu-id="e5cf9-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e5cf9-128">NameU</span><span class="sxs-lookup"><span data-stu-id="e5cf9-128">NameU</span></span>  <br/> |<span data-ttu-id="e5cf9-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e5cf9-129">xsd:string</span></span>  <br/> |<span data-ttu-id="e5cf9-130">必需</span><span class="sxs-lookup"><span data-stu-id="e5cf9-130">required</span></span>  <br/> ||<span data-ttu-id="e5cf9-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e5cf9-132">Panos</span><span class="sxs-lookup"><span data-stu-id="e5cf9-132">Panos</span></span>  <br/> |<span data-ttu-id="e5cf9-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e5cf9-133">xsd:string</span></span>  <br/> |<span data-ttu-id="e5cf9-134">可选</span><span class="sxs-lookup"><span data-stu-id="e5cf9-134">optional</span></span>  <br/> ||<span data-ttu-id="e5cf9-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e5cf9-136">Panose</span><span class="sxs-lookup"><span data-stu-id="e5cf9-136">Panose</span></span>  <br/> |<span data-ttu-id="e5cf9-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e5cf9-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e5cf9-138">可选</span><span class="sxs-lookup"><span data-stu-id="e5cf9-138">optional</span></span>  <br/> ||<span data-ttu-id="e5cf9-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e5cf9-140">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="e5cf9-140">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="e5cf9-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e5cf9-141">xsd:string</span></span>  <br/> |<span data-ttu-id="e5cf9-142">可选</span><span class="sxs-lookup"><span data-stu-id="e5cf9-142">optional</span></span>  <br/> ||<span data-ttu-id="e5cf9-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e5cf9-143">Values of the xsd:string type.</span></span>  <br/> |
   

