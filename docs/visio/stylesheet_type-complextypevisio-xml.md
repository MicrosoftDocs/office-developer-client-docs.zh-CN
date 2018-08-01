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
# <a name="stylesheettype-complextype-visio-xml"></a><span data-ttu-id="40ed8-102">StyleSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="40ed8-102">StyleSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="40ed8-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="40ed8-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="40ed8-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="40ed8-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="40ed8-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="40ed8-105">**Schema file**</span></span> <br/> |<span data-ttu-id="40ed8-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="40ed8-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="40ed8-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="40ed8-107">**Extension base**</span></span> <br/> |<span data-ttu-id="40ed8-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="40ed8-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="40ed8-109">定义</span><span class="sxs-lookup"><span data-stu-id="40ed8-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="40ed8-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="40ed8-110">Elements and attributes</span></span>

<span data-ttu-id="40ed8-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="40ed8-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="40ed8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="40ed8-112">Child elements</span></span>

<span data-ttu-id="40ed8-113">无。</span><span class="sxs-lookup"><span data-stu-id="40ed8-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="40ed8-114">属性</span><span class="sxs-lookup"><span data-stu-id="40ed8-114">Attributes</span></span>

|<span data-ttu-id="40ed8-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="40ed8-115">**Attribute**</span></span>|<span data-ttu-id="40ed8-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="40ed8-116">**Type**</span></span>|<span data-ttu-id="40ed8-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="40ed8-117">**Required**</span></span>|<span data-ttu-id="40ed8-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="40ed8-118">**Description**</span></span>|<span data-ttu-id="40ed8-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="40ed8-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40ed8-120">ID</span><span class="sxs-lookup"><span data-stu-id="40ed8-120">ID</span></span>  <br/> |<span data-ttu-id="40ed8-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="40ed8-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="40ed8-122">必需</span><span class="sxs-lookup"><span data-stu-id="40ed8-122">required</span></span>  <br/> ||<span data-ttu-id="40ed8-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ed8-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="40ed8-124">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="40ed8-124">IsCustomName</span></span>  <br/> |<span data-ttu-id="40ed8-125">化</span><span class="sxs-lookup"><span data-stu-id="40ed8-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="40ed8-126">可选</span><span class="sxs-lookup"><span data-stu-id="40ed8-126">optional</span></span>  <br/> ||<span data-ttu-id="40ed8-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ed8-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="40ed8-128">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="40ed8-128">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="40ed8-129">化</span><span class="sxs-lookup"><span data-stu-id="40ed8-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="40ed8-130">可选</span><span class="sxs-lookup"><span data-stu-id="40ed8-130">optional</span></span>  <br/> ||<span data-ttu-id="40ed8-131">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ed8-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="40ed8-132">名称</span><span class="sxs-lookup"><span data-stu-id="40ed8-132">Name</span></span>  <br/> |<span data-ttu-id="40ed8-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ed8-133">xsd:string</span></span>  <br/> |<span data-ttu-id="40ed8-134">可选</span><span class="sxs-lookup"><span data-stu-id="40ed8-134">optional</span></span>  <br/> ||<span data-ttu-id="40ed8-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ed8-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="40ed8-136">NameU</span><span class="sxs-lookup"><span data-stu-id="40ed8-136">NameU</span></span>  <br/> |<span data-ttu-id="40ed8-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ed8-137">xsd:string</span></span>  <br/> |<span data-ttu-id="40ed8-138">可选</span><span class="sxs-lookup"><span data-stu-id="40ed8-138">optional</span></span>  <br/> ||<span data-ttu-id="40ed8-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ed8-139">Values of the xsd:string type.</span></span>  <br/> |
   

