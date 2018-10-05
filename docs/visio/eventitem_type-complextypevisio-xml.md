---
title: EventItem_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f157db03-e7d0-d39f-cbde-2a22f45b40ed
ms.openlocfilehash: 77c51ab76a1d7c5c4450c429b1d3ccb8e3442f34
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395726"
---
# <a name="eventitemtype-complextype-visio-xml"></a><span data-ttu-id="c915d-102">EventItem_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c915d-102">EventItem_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="c915d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c915d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c915d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c915d-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c915d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c915d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c915d-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="c915d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c915d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c915d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c915d-108">无</span><span class="sxs-lookup"><span data-stu-id="c915d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c915d-109">定义</span><span class="sxs-lookup"><span data-stu-id="c915d-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="c915d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c915d-110">Elements and attributes</span></span>

<span data-ttu-id="c915d-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c915d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c915d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c915d-112">Child elements</span></span>

<span data-ttu-id="c915d-113">无。</span><span class="sxs-lookup"><span data-stu-id="c915d-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c915d-114">属性</span><span class="sxs-lookup"><span data-stu-id="c915d-114">Attributes</span></span>

|<span data-ttu-id="c915d-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="c915d-115">**Attribute**</span></span>|<span data-ttu-id="c915d-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="c915d-116">**Type**</span></span>|<span data-ttu-id="c915d-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="c915d-117">**Required**</span></span>|<span data-ttu-id="c915d-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="c915d-118">**Description**</span></span>|<span data-ttu-id="c915d-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c915d-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c915d-120">操作</span><span class="sxs-lookup"><span data-stu-id="c915d-120">Action</span></span>  <br/> |<span data-ttu-id="c915d-121">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c915d-121">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c915d-122">必需</span><span class="sxs-lookup"><span data-stu-id="c915d-122">required</span></span>  <br/> ||<span data-ttu-id="c915d-123">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-123">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c915d-124">已启用</span><span class="sxs-lookup"><span data-stu-id="c915d-124">Enabled</span></span>  <br/> |<span data-ttu-id="c915d-125">化</span><span class="sxs-lookup"><span data-stu-id="c915d-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c915d-126">可选</span><span class="sxs-lookup"><span data-stu-id="c915d-126">optional</span></span>  <br/> ||<span data-ttu-id="c915d-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c915d-128">EventCode</span><span class="sxs-lookup"><span data-stu-id="c915d-128">EventCode</span></span>  <br/> |<span data-ttu-id="c915d-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="c915d-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="c915d-130">必需</span><span class="sxs-lookup"><span data-stu-id="c915d-130">required</span></span>  <br/> ||<span data-ttu-id="c915d-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="c915d-132">ID</span><span class="sxs-lookup"><span data-stu-id="c915d-132">ID</span></span>  <br/> |<span data-ttu-id="c915d-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c915d-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c915d-134">必需</span><span class="sxs-lookup"><span data-stu-id="c915d-134">required</span></span>  <br/> ||<span data-ttu-id="c915d-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c915d-136">目标</span><span class="sxs-lookup"><span data-stu-id="c915d-136">Target</span></span>  <br/> |<span data-ttu-id="c915d-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c915d-137">xsd:string</span></span>  <br/> |<span data-ttu-id="c915d-138">必需</span><span class="sxs-lookup"><span data-stu-id="c915d-138">required</span></span>  <br/> ||<span data-ttu-id="c915d-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-139">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c915d-140">TargetArgs</span><span class="sxs-lookup"><span data-stu-id="c915d-140">TargetArgs</span></span>  <br/> |<span data-ttu-id="c915d-141">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c915d-141">xsd:string</span></span>  <br/> |<span data-ttu-id="c915d-142">必需</span><span class="sxs-lookup"><span data-stu-id="c915d-142">required</span></span>  <br/> ||<span data-ttu-id="c915d-143">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c915d-143">Values of the xsd:string type.</span></span>  <br/> |
   

