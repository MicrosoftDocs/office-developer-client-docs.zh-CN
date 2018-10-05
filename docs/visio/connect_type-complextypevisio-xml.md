---
title: Connect_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2230976b-f2a8-425b-b8b0-a7fd5efb4536
ms.openlocfilehash: 158fad1f3ec18bbc9565229338f4710c145c17e7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383909"
---
# <a name="connecttype-complextype-visio-xml"></a><span data-ttu-id="1cc93-102">Connect_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1cc93-102">Connect_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="1cc93-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1cc93-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1cc93-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1cc93-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1cc93-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1cc93-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1cc93-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="1cc93-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1cc93-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1cc93-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1cc93-108">无</span><span class="sxs-lookup"><span data-stu-id="1cc93-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1cc93-109">定义</span><span class="sxs-lookup"><span data-stu-id="1cc93-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="1cc93-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1cc93-110">Elements and attributes</span></span>

<span data-ttu-id="1cc93-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1cc93-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1cc93-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1cc93-112">Child elements</span></span>

<span data-ttu-id="1cc93-113">无。</span><span class="sxs-lookup"><span data-stu-id="1cc93-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1cc93-114">属性</span><span class="sxs-lookup"><span data-stu-id="1cc93-114">Attributes</span></span>

|<span data-ttu-id="1cc93-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="1cc93-115">**Attribute**</span></span>|<span data-ttu-id="1cc93-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1cc93-116">**Type**</span></span>|<span data-ttu-id="1cc93-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="1cc93-117">**Required**</span></span>|<span data-ttu-id="1cc93-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="1cc93-118">**Description**</span></span>|<span data-ttu-id="1cc93-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1cc93-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1cc93-120">FromCell</span><span class="sxs-lookup"><span data-stu-id="1cc93-120">FromCell</span></span>  <br/> |<span data-ttu-id="1cc93-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1cc93-121">xsd:string</span></span>  <br/> |<span data-ttu-id="1cc93-122">可选</span><span class="sxs-lookup"><span data-stu-id="1cc93-122">optional</span></span>  <br/> ||<span data-ttu-id="1cc93-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="1cc93-124">FromPart</span><span class="sxs-lookup"><span data-stu-id="1cc93-124">FromPart</span></span>  <br/> |<span data-ttu-id="1cc93-125">xsd:int</span><span class="sxs-lookup"><span data-stu-id="1cc93-125">xsd:int</span></span>  <br/> |<span data-ttu-id="1cc93-126">可选</span><span class="sxs-lookup"><span data-stu-id="1cc93-126">optional</span></span>  <br/> ||<span data-ttu-id="1cc93-127">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-127">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="1cc93-128">FromSheet</span><span class="sxs-lookup"><span data-stu-id="1cc93-128">FromSheet</span></span>  <br/> |<span data-ttu-id="1cc93-129">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1cc93-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1cc93-130">必需</span><span class="sxs-lookup"><span data-stu-id="1cc93-130">required</span></span>  <br/> ||<span data-ttu-id="1cc93-131">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="1cc93-132">ToCell</span><span class="sxs-lookup"><span data-stu-id="1cc93-132">ToCell</span></span>  <br/> |<span data-ttu-id="1cc93-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="1cc93-133">xsd:string</span></span>  <br/> |<span data-ttu-id="1cc93-134">可选</span><span class="sxs-lookup"><span data-stu-id="1cc93-134">optional</span></span>  <br/> ||<span data-ttu-id="1cc93-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="1cc93-136">ToPart</span><span class="sxs-lookup"><span data-stu-id="1cc93-136">ToPart</span></span>  <br/> |<span data-ttu-id="1cc93-137">xsd:int</span><span class="sxs-lookup"><span data-stu-id="1cc93-137">xsd:int</span></span>  <br/> |<span data-ttu-id="1cc93-138">可选</span><span class="sxs-lookup"><span data-stu-id="1cc93-138">optional</span></span>  <br/> ||<span data-ttu-id="1cc93-139">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="1cc93-140">ToSheet</span><span class="sxs-lookup"><span data-stu-id="1cc93-140">ToSheet</span></span>  <br/> |<span data-ttu-id="1cc93-141">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1cc93-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1cc93-142">必需</span><span class="sxs-lookup"><span data-stu-id="1cc93-142">required</span></span>  <br/> ||<span data-ttu-id="1cc93-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1cc93-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

