---
title: Connect_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2230976b-f2a8-425b-b8b0-a7fd5efb4536
ms.openlocfilehash: 9a321a3ff910afb183e1a697eaad9dfb51125524
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779949"
---
# <a name="connecttype-complextype-visio-xml"></a><span data-ttu-id="9e785-102">Connect_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9e785-102">Connect_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9e785-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9e785-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9e785-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9e785-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9e785-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9e785-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9e785-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="9e785-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9e785-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9e785-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9e785-108">无</span><span class="sxs-lookup"><span data-stu-id="9e785-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9e785-109">定义</span><span class="sxs-lookup"><span data-stu-id="9e785-109">Definition</span></span>

```XML
      <xs:complexType name="Connect_Type">
    <xs:attribute name="FromSheet"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="FromCell"
  type="xsd:string"
    />
    <xs:attribute name="FromPart"
  type="xsd:int"
    />
    <xs:attribute name="ToSheet"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ToCell"
  type="xsd:string"
    />
    <xs:attribute name="ToPart"
  type="xsd:int"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9e785-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9e785-110">Elements and attributes</span></span>

<span data-ttu-id="9e785-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9e785-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9e785-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9e785-112">Child elements</span></span>

<span data-ttu-id="9e785-113">无。</span><span class="sxs-lookup"><span data-stu-id="9e785-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9e785-114">属性</span><span class="sxs-lookup"><span data-stu-id="9e785-114">Attributes</span></span>

|<span data-ttu-id="9e785-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="9e785-115">**Attribute**</span></span>|<span data-ttu-id="9e785-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e785-116">**Type**</span></span>|<span data-ttu-id="9e785-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="9e785-117">**Required**</span></span>|<span data-ttu-id="9e785-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e785-118">**Description**</span></span>|<span data-ttu-id="9e785-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9e785-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e785-120">FromCell</span><span class="sxs-lookup"><span data-stu-id="9e785-120">FromCell</span></span>  <br/> |<span data-ttu-id="9e785-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9e785-121">xsd:string</span></span>  <br/> |<span data-ttu-id="9e785-122">可选</span><span class="sxs-lookup"><span data-stu-id="9e785-122">optional</span></span>  <br/> ||<span data-ttu-id="9e785-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9e785-124">FromPart</span><span class="sxs-lookup"><span data-stu-id="9e785-124">FromPart</span></span>  <br/> |<span data-ttu-id="9e785-125">xsd:int</span><span class="sxs-lookup"><span data-stu-id="9e785-125">xsd:int</span></span>  <br/> |<span data-ttu-id="9e785-126">可选</span><span class="sxs-lookup"><span data-stu-id="9e785-126">optional</span></span>  <br/> ||<span data-ttu-id="9e785-127">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-127">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="9e785-128">FromSheet</span><span class="sxs-lookup"><span data-stu-id="9e785-128">FromSheet</span></span>  <br/> |<span data-ttu-id="9e785-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e785-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e785-130">必需</span><span class="sxs-lookup"><span data-stu-id="9e785-130">required</span></span>  <br/> ||<span data-ttu-id="9e785-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9e785-132">ToCell</span><span class="sxs-lookup"><span data-stu-id="9e785-132">ToCell</span></span>  <br/> |<span data-ttu-id="9e785-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9e785-133">xsd:string</span></span>  <br/> |<span data-ttu-id="9e785-134">可选</span><span class="sxs-lookup"><span data-stu-id="9e785-134">optional</span></span>  <br/> ||<span data-ttu-id="9e785-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9e785-136">ToPart</span><span class="sxs-lookup"><span data-stu-id="9e785-136">ToPart</span></span>  <br/> |<span data-ttu-id="9e785-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="9e785-137">xsd:int</span></span>  <br/> |<span data-ttu-id="9e785-138">可选</span><span class="sxs-lookup"><span data-stu-id="9e785-138">optional</span></span>  <br/> ||<span data-ttu-id="9e785-139">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="9e785-140">ToSheet</span><span class="sxs-lookup"><span data-stu-id="9e785-140">ToSheet</span></span>  <br/> |<span data-ttu-id="9e785-141">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9e785-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9e785-142">必需</span><span class="sxs-lookup"><span data-stu-id="9e785-142">required</span></span>  <br/> ||<span data-ttu-id="9e785-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9e785-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

