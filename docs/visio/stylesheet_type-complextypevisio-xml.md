---
title: StyleSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 06a02d07-920e-7d47-d63a-da3596cf20f6
ms.openlocfilehash: 394712b65ee44a939a20fd3b65df504785f106ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781467"
---
# <a name="stylesheettype-complextype-visio-xml"></a><span data-ttu-id="2a4c1-102">StyleSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2a4c1-102">StyleSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2a4c1-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2a4c1-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2a4c1-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2a4c1-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2a4c1-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="2a4c1-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2a4c1-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2a4c1-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="2a4c1-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2a4c1-109">定义</span><span class="sxs-lookup"><span data-stu-id="2a4c1-109">Definition</span></span>

```XML
      <xs:complexType name="StyleSheet_Type">
        <xs:complexContent>
        <xs:extension base="Sheet_Type">
      
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="NameU"
  type="xsd:string"
    />
    <xs:attribute name="IsCustomName"
  type="xsd:boolean"
    />
    <xs:attribute name="IsCustomNameU"
  type="xsd:boolean"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2a4c1-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2a4c1-110">Elements and attributes</span></span>

<span data-ttu-id="2a4c1-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2a4c1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2a4c1-112">Child elements</span></span>

<span data-ttu-id="2a4c1-113">无。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2a4c1-114">属性</span><span class="sxs-lookup"><span data-stu-id="2a4c1-114">Attributes</span></span>

|<span data-ttu-id="2a4c1-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-115">**Attribute**</span></span>|<span data-ttu-id="2a4c1-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-116">**Type**</span></span>|<span data-ttu-id="2a4c1-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-117">**Required**</span></span>|<span data-ttu-id="2a4c1-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-118">**Description**</span></span>|<span data-ttu-id="2a4c1-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2a4c1-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a4c1-120">ID</span><span class="sxs-lookup"><span data-stu-id="2a4c1-120">ID</span></span>  <br/> |<span data-ttu-id="2a4c1-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2a4c1-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2a4c1-122">必需</span><span class="sxs-lookup"><span data-stu-id="2a4c1-122">required</span></span>  <br/> ||<span data-ttu-id="2a4c1-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="2a4c1-124">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="2a4c1-124">IsCustomName</span></span>  <br/> |<span data-ttu-id="2a4c1-125">化</span><span class="sxs-lookup"><span data-stu-id="2a4c1-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2a4c1-126">可选</span><span class="sxs-lookup"><span data-stu-id="2a4c1-126">optional</span></span>  <br/> ||<span data-ttu-id="2a4c1-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2a4c1-128">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="2a4c1-128">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="2a4c1-129">化</span><span class="sxs-lookup"><span data-stu-id="2a4c1-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="2a4c1-130">可选</span><span class="sxs-lookup"><span data-stu-id="2a4c1-130">optional</span></span>  <br/> ||<span data-ttu-id="2a4c1-131">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="2a4c1-132">名称</span><span class="sxs-lookup"><span data-stu-id="2a4c1-132">Name</span></span>  <br/> |<span data-ttu-id="2a4c1-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2a4c1-133">xsd:string</span></span>  <br/> |<span data-ttu-id="2a4c1-134">可选</span><span class="sxs-lookup"><span data-stu-id="2a4c1-134">optional</span></span>  <br/> ||<span data-ttu-id="2a4c1-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2a4c1-136">NameU</span><span class="sxs-lookup"><span data-stu-id="2a4c1-136">NameU</span></span>  <br/> |<span data-ttu-id="2a4c1-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2a4c1-137">xsd:string</span></span>  <br/> |<span data-ttu-id="2a4c1-138">可选</span><span class="sxs-lookup"><span data-stu-id="2a4c1-138">optional</span></span>  <br/> ||<span data-ttu-id="2a4c1-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2a4c1-139">Values of the xsd:string type.</span></span>  <br/> |
   

