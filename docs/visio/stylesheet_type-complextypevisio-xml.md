---
title: StyleSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 06a02d07-920e-7d47-d63a-da3596cf20f6
ms.openlocfilehash: 19440ab1365ff82bd37d705115fd123dcb630aba
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395999"
---
# <a name="stylesheettype-complextype-visio-xml"></a><span data-ttu-id="71702-102">StyleSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="71702-102">StyleSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="71702-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="71702-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="71702-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="71702-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="71702-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="71702-105">**Schema file**</span></span> <br/> |<span data-ttu-id="71702-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="71702-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="71702-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="71702-107">**Extension base**</span></span> <br/> |<span data-ttu-id="71702-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="71702-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="71702-109">定义</span><span class="sxs-lookup"><span data-stu-id="71702-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="71702-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="71702-110">Elements and attributes</span></span>

<span data-ttu-id="71702-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="71702-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="71702-112">子元素</span><span class="sxs-lookup"><span data-stu-id="71702-112">Child elements</span></span>

<span data-ttu-id="71702-113">无。</span><span class="sxs-lookup"><span data-stu-id="71702-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="71702-114">属性</span><span class="sxs-lookup"><span data-stu-id="71702-114">Attributes</span></span>

|<span data-ttu-id="71702-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="71702-115">**Attribute**</span></span>|<span data-ttu-id="71702-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="71702-116">**Type**</span></span>|<span data-ttu-id="71702-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="71702-117">**Required**</span></span>|<span data-ttu-id="71702-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="71702-118">**Description**</span></span>|<span data-ttu-id="71702-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="71702-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71702-120">ID</span><span class="sxs-lookup"><span data-stu-id="71702-120">ID</span></span>  <br/> |<span data-ttu-id="71702-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="71702-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="71702-122">必需</span><span class="sxs-lookup"><span data-stu-id="71702-122">required</span></span>  <br/> ||<span data-ttu-id="71702-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="71702-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="71702-124">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="71702-124">IsCustomName</span></span>  <br/> |<span data-ttu-id="71702-125">化</span><span class="sxs-lookup"><span data-stu-id="71702-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="71702-126">可选</span><span class="sxs-lookup"><span data-stu-id="71702-126">optional</span></span>  <br/> ||<span data-ttu-id="71702-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="71702-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="71702-128">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="71702-128">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="71702-129">化</span><span class="sxs-lookup"><span data-stu-id="71702-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="71702-130">可选</span><span class="sxs-lookup"><span data-stu-id="71702-130">optional</span></span>  <br/> ||<span data-ttu-id="71702-131">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="71702-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="71702-132">名称</span><span class="sxs-lookup"><span data-stu-id="71702-132">Name</span></span>  <br/> |<span data-ttu-id="71702-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="71702-133">xsd:string</span></span>  <br/> |<span data-ttu-id="71702-134">可选</span><span class="sxs-lookup"><span data-stu-id="71702-134">optional</span></span>  <br/> ||<span data-ttu-id="71702-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="71702-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="71702-136">NameU</span><span class="sxs-lookup"><span data-stu-id="71702-136">NameU</span></span>  <br/> |<span data-ttu-id="71702-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="71702-137">xsd:string</span></span>  <br/> |<span data-ttu-id="71702-138">可选</span><span class="sxs-lookup"><span data-stu-id="71702-138">optional</span></span>  <br/> ||<span data-ttu-id="71702-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="71702-139">Values of the xsd:string type.</span></span>  <br/> |
   

