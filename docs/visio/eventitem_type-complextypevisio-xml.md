---
title: EventItem_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f157db03-e7d0-d39f-cbde-2a22f45b40ed
ms.openlocfilehash: 7fc23d9e2a9e4567693a4979b796804b16f148e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780205"
---
# <a name="eventitemtype-complextype-visio-xml"></a><span data-ttu-id="eeb0a-102">EventItem_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="eeb0a-102">EventItem_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="eeb0a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="eeb0a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="eeb0a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="eeb0a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="eeb0a-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="eeb0a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="eeb0a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="eeb0a-108">无</span><span class="sxs-lookup"><span data-stu-id="eeb0a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="eeb0a-109">定义</span><span class="sxs-lookup"><span data-stu-id="eeb0a-109">Definition</span></span>

```XML
      <xs:complexType name="EventItem_Type">
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Action"
  type="xsd:unsignedShort"
     use="required"
    />
    <xs:attribute name="EventCode"
  type="xsd:unsignedShort"
     use="required"
    />
    <xs:attribute name="Enabled"
  type="xsd:boolean"
    />
    <xs:attribute name="Target"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="TargetArgs"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="eeb0a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="eeb0a-110">Elements and attributes</span></span>

<span data-ttu-id="eeb0a-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="eeb0a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="eeb0a-112">Child elements</span></span>

<span data-ttu-id="eeb0a-113">无。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="eeb0a-114">属性</span><span class="sxs-lookup"><span data-stu-id="eeb0a-114">Attributes</span></span>

|<span data-ttu-id="eeb0a-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-115">**Attribute**</span></span>|<span data-ttu-id="eeb0a-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-116">**Type**</span></span>|<span data-ttu-id="eeb0a-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-117">**Required**</span></span>|<span data-ttu-id="eeb0a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-118">**Description**</span></span>|<span data-ttu-id="eeb0a-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="eeb0a-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eeb0a-120">操作</span><span class="sxs-lookup"><span data-stu-id="eeb0a-120">Action</span></span>  <br/> |<span data-ttu-id="eeb0a-121">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="eeb0a-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="eeb0a-122">必需</span><span class="sxs-lookup"><span data-stu-id="eeb0a-122">required</span></span>  <br/> ||<span data-ttu-id="eeb0a-123">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="eeb0a-124">已启用</span><span class="sxs-lookup"><span data-stu-id="eeb0a-124">Enabled</span></span>  <br/> |<span data-ttu-id="eeb0a-125">化</span><span class="sxs-lookup"><span data-stu-id="eeb0a-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="eeb0a-126">可选</span><span class="sxs-lookup"><span data-stu-id="eeb0a-126">optional</span></span>  <br/> ||<span data-ttu-id="eeb0a-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="eeb0a-128">EventCode</span><span class="sxs-lookup"><span data-stu-id="eeb0a-128">EventCode</span></span>  <br/> |<span data-ttu-id="eeb0a-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="eeb0a-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="eeb0a-130">必需</span><span class="sxs-lookup"><span data-stu-id="eeb0a-130">required</span></span>  <br/> ||<span data-ttu-id="eeb0a-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="eeb0a-132">ID</span><span class="sxs-lookup"><span data-stu-id="eeb0a-132">ID</span></span>  <br/> |<span data-ttu-id="eeb0a-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="eeb0a-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="eeb0a-134">必需</span><span class="sxs-lookup"><span data-stu-id="eeb0a-134">required</span></span>  <br/> ||<span data-ttu-id="eeb0a-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="eeb0a-136">目标</span><span class="sxs-lookup"><span data-stu-id="eeb0a-136">Target</span></span>  <br/> |<span data-ttu-id="eeb0a-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="eeb0a-137">xsd:string</span></span>  <br/> |<span data-ttu-id="eeb0a-138">必需</span><span class="sxs-lookup"><span data-stu-id="eeb0a-138">required</span></span>  <br/> ||<span data-ttu-id="eeb0a-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="eeb0a-140">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="eeb0a-140">TargetArgs</span></span>  <br/> |<span data-ttu-id="eeb0a-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="eeb0a-141">xsd:string</span></span>  <br/> |<span data-ttu-id="eeb0a-142">必需</span><span class="sxs-lookup"><span data-stu-id="eeb0a-142">required</span></span>  <br/> ||<span data-ttu-id="eeb0a-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="eeb0a-143">Values of the xsd:string type.</span></span>  <br/> |
   

