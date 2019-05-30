---
title: Connect_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2230976b-f2a8-425b-b8b0-a7fd5efb4536
ms.openlocfilehash: 9dee421915cb3e69ef5223280a425e785d29e4ec
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538737"
---
# <a name="connecttype-complextype-visio-xml"></a><span data-ttu-id="6660a-102">Connect_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6660a-102">Connect_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="6660a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="6660a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6660a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6660a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="6660a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6660a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="6660a-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="6660a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="6660a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="6660a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="6660a-108">无</span><span class="sxs-lookup"><span data-stu-id="6660a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6660a-109">定义</span><span class="sxs-lookup"><span data-stu-id="6660a-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="6660a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6660a-110">Elements and attributes</span></span>

<span data-ttu-id="6660a-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="6660a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="6660a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="6660a-112">Child elements</span></span>

<span data-ttu-id="6660a-113">无。</span><span class="sxs-lookup"><span data-stu-id="6660a-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6660a-114">属性</span><span class="sxs-lookup"><span data-stu-id="6660a-114">Attributes</span></span>

|<span data-ttu-id="6660a-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="6660a-115">**Attribute**</span></span>|<span data-ttu-id="6660a-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="6660a-116">**Type**</span></span>|<span data-ttu-id="6660a-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="6660a-117">**Required**</span></span>|<span data-ttu-id="6660a-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="6660a-118">**Description**</span></span>|<span data-ttu-id="6660a-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6660a-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6660a-120">FromCell</span><span class="sxs-lookup"><span data-stu-id="6660a-120">FromCell</span></span>  <br/> |<span data-ttu-id="6660a-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6660a-121">xsd:string</span></span>  <br/> |<span data-ttu-id="6660a-122">可选</span><span class="sxs-lookup"><span data-stu-id="6660a-122">optional</span></span>  <br/> ||<span data-ttu-id="6660a-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-123">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6660a-124">FromPart</span><span class="sxs-lookup"><span data-stu-id="6660a-124">FromPart</span></span>  <br/> |<span data-ttu-id="6660a-125">xsd: int</span><span class="sxs-lookup"><span data-stu-id="6660a-125">xsd:int</span></span>  <br/> |<span data-ttu-id="6660a-126">可选</span><span class="sxs-lookup"><span data-stu-id="6660a-126">optional</span></span>  <br/> ||<span data-ttu-id="6660a-127">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-127">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="6660a-128">FromSheet</span><span class="sxs-lookup"><span data-stu-id="6660a-128">FromSheet</span></span>  <br/> |<span data-ttu-id="6660a-129">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6660a-129">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="6660a-130">必需</span><span class="sxs-lookup"><span data-stu-id="6660a-130">required</span></span>  <br/> ||<span data-ttu-id="6660a-131">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-131">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="6660a-132">ToCell</span><span class="sxs-lookup"><span data-stu-id="6660a-132">ToCell</span></span>  <br/> |<span data-ttu-id="6660a-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="6660a-133">xsd:string</span></span>  <br/> |<span data-ttu-id="6660a-134">可选</span><span class="sxs-lookup"><span data-stu-id="6660a-134">optional</span></span>  <br/> ||<span data-ttu-id="6660a-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="6660a-136">ToPart</span><span class="sxs-lookup"><span data-stu-id="6660a-136">ToPart</span></span>  <br/> |<span data-ttu-id="6660a-137">xsd: int</span><span class="sxs-lookup"><span data-stu-id="6660a-137">xsd:int</span></span>  <br/> |<span data-ttu-id="6660a-138">可选</span><span class="sxs-lookup"><span data-stu-id="6660a-138">optional</span></span>  <br/> ||<span data-ttu-id="6660a-139">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-139">Values of the xsd:int type.</span></span>  <br/> |
|<span data-ttu-id="6660a-140">ToSheet</span><span class="sxs-lookup"><span data-stu-id="6660a-140">ToSheet</span></span>  <br/> |<span data-ttu-id="6660a-141">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6660a-141">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="6660a-142">必需</span><span class="sxs-lookup"><span data-stu-id="6660a-142">required</span></span>  <br/> ||<span data-ttu-id="6660a-143">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="6660a-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

