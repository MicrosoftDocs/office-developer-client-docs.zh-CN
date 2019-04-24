---
title: Connect_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2230976b-f2a8-425b-b8b0-a7fd5efb4536
ms.openlocfilehash: 158fad1f3ec18bbc9565229338f4710c145c17e7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327081"
---
# <a name="connecttype-complextype-visio-xml"></a><span data-ttu-id="d1ad4-102">Connect_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="d1ad4-102">Connect_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="d1ad4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d1ad4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d1ad4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d1ad4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d1ad4-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="d1ad4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d1ad4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d1ad4-108">无</span><span class="sxs-lookup"><span data-stu-id="d1ad4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d1ad4-109">定义</span><span class="sxs-lookup"><span data-stu-id="d1ad4-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="d1ad4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d1ad4-110">Elements and attributes</span></span>

<span data-ttu-id="d1ad4-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d1ad4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d1ad4-112">Child elements</span></span>

<span data-ttu-id="d1ad4-113">无。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d1ad4-114">属性</span><span class="sxs-lookup"><span data-stu-id="d1ad4-114">Attributes</span></span>

|<span data-ttu-id="d1ad4-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-115">**Attribute**</span></span>|<span data-ttu-id="d1ad4-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-116">**Type**</span></span>|<span data-ttu-id="d1ad4-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-117">**Required**</span></span>|<span data-ttu-id="d1ad4-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-118">**Description**</span></span>|<span data-ttu-id="d1ad4-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d1ad4-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1ad4-120">FromCell</span><span class="sxs-lookup"><span data-stu-id="d1ad4-120">FromCell</span></span>  <br/> |<span data-ttu-id="d1ad4-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1ad4-121">xsd:string</span></span>  <br/> |<span data-ttu-id="d1ad4-122">可选</span><span class="sxs-lookup"><span data-stu-id="d1ad4-122">optional</span></span>  <br/> ||<span data-ttu-id="d1ad4-123">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d1ad4-124">FromPart</span><span class="sxs-lookup"><span data-stu-id="d1ad4-124">FromPart</span></span>  <br/> |<span data-ttu-id="d1ad4-125">xsd: int</span><span class="sxs-lookup"><span data-stu-id="d1ad4-125">xsd:int</span></span>  <br/> |<span data-ttu-id="d1ad4-126">可选</span><span class="sxs-lookup"><span data-stu-id="d1ad4-126">optional</span></span>  <br/> ||<span data-ttu-id="d1ad4-127">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-127">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="d1ad4-128">FromSheet</span><span class="sxs-lookup"><span data-stu-id="d1ad4-128">FromSheet</span></span>  <br/> |<span data-ttu-id="d1ad4-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d1ad4-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d1ad4-130">必需</span><span class="sxs-lookup"><span data-stu-id="d1ad4-130">required</span></span>  <br/> ||<span data-ttu-id="d1ad4-131">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d1ad4-132">ToCell</span><span class="sxs-lookup"><span data-stu-id="d1ad4-132">ToCell</span></span>  <br/> |<span data-ttu-id="d1ad4-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1ad4-133">xsd:string</span></span>  <br/> |<span data-ttu-id="d1ad4-134">可选</span><span class="sxs-lookup"><span data-stu-id="d1ad4-134">optional</span></span>  <br/> ||<span data-ttu-id="d1ad4-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="d1ad4-136">ToPart</span><span class="sxs-lookup"><span data-stu-id="d1ad4-136">ToPart</span></span>  <br/> |<span data-ttu-id="d1ad4-137">xsd: int</span><span class="sxs-lookup"><span data-stu-id="d1ad4-137">xsd:int</span></span>  <br/> |<span data-ttu-id="d1ad4-138">可选</span><span class="sxs-lookup"><span data-stu-id="d1ad4-138">optional</span></span>  <br/> ||<span data-ttu-id="d1ad4-139">xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="d1ad4-140">ToSheet</span><span class="sxs-lookup"><span data-stu-id="d1ad4-140">ToSheet</span></span>  <br/> |<span data-ttu-id="d1ad4-141">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d1ad4-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d1ad4-142">必需</span><span class="sxs-lookup"><span data-stu-id="d1ad4-142">required</span></span>  <br/> ||<span data-ttu-id="d1ad4-143">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d1ad4-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

