---
title: StyleSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 06a02d07-920e-7d47-d63a-da3596cf20f6
ms.openlocfilehash: 6dcb6bbfd01c37b499dfca4d54d6cb0832e59b5a
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541979"
---
# <a name="stylesheettype-complextype-visio-xml"></a><span data-ttu-id="670fa-102">StyleSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="670fa-102">StyleSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="670fa-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="670fa-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="670fa-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="670fa-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="670fa-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="670fa-105">**Schema file**</span></span> <br/> |<span data-ttu-id="670fa-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="670fa-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="670fa-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="670fa-107">**Extension base**</span></span> <br/> |<span data-ttu-id="670fa-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="670fa-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="670fa-109">定义</span><span class="sxs-lookup"><span data-stu-id="670fa-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="670fa-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="670fa-110">Elements and attributes</span></span>

<span data-ttu-id="670fa-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="670fa-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="670fa-112">子元素</span><span class="sxs-lookup"><span data-stu-id="670fa-112">Child elements</span></span>

<span data-ttu-id="670fa-113">无。</span><span class="sxs-lookup"><span data-stu-id="670fa-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="670fa-114">属性</span><span class="sxs-lookup"><span data-stu-id="670fa-114">Attributes</span></span>

|<span data-ttu-id="670fa-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="670fa-115">**Attribute**</span></span>|<span data-ttu-id="670fa-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="670fa-116">**Type**</span></span>|<span data-ttu-id="670fa-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="670fa-117">**Required**</span></span>|<span data-ttu-id="670fa-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="670fa-118">**Description**</span></span>|<span data-ttu-id="670fa-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="670fa-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="670fa-120">ID</span><span class="sxs-lookup"><span data-stu-id="670fa-120">ID</span></span>  <br/> |<span data-ttu-id="670fa-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="670fa-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="670fa-122">必需</span><span class="sxs-lookup"><span data-stu-id="670fa-122">required</span></span>  <br/> ||<span data-ttu-id="670fa-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="670fa-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="670fa-124">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="670fa-124">IsCustomName</span></span>  <br/> |<span data-ttu-id="670fa-125">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="670fa-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="670fa-126">可选</span><span class="sxs-lookup"><span data-stu-id="670fa-126">optional</span></span>  <br/> ||<span data-ttu-id="670fa-127">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="670fa-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="670fa-128">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="670fa-128">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="670fa-129">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="670fa-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="670fa-130">可选</span><span class="sxs-lookup"><span data-stu-id="670fa-130">optional</span></span>  <br/> ||<span data-ttu-id="670fa-131">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="670fa-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="670fa-132">名称</span><span class="sxs-lookup"><span data-stu-id="670fa-132">Name</span></span>  <br/> |<span data-ttu-id="670fa-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="670fa-133">xsd:string</span></span>  <br/> |<span data-ttu-id="670fa-134">可选</span><span class="sxs-lookup"><span data-stu-id="670fa-134">optional</span></span>  <br/> ||<span data-ttu-id="670fa-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="670fa-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="670fa-136">NameU</span><span class="sxs-lookup"><span data-stu-id="670fa-136">NameU</span></span>  <br/> |<span data-ttu-id="670fa-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="670fa-137">xsd:string</span></span>  <br/> |<span data-ttu-id="670fa-138">可选</span><span class="sxs-lookup"><span data-stu-id="670fa-138">optional</span></span>  <br/> ||<span data-ttu-id="670fa-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="670fa-139">Values of the xsd:string type.</span></span>  <br/> |
   

