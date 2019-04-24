---
title: DocumentSheet_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 57af2ed5-7d89-9538-e51b-0bc70f067b40
ms.openlocfilehash: a1f51ef6f0340b4430860eabde3ad778e923fed0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326136"
---
# <a name="documentsheettype-complextype-visio-xml"></a><span data-ttu-id="9b8d6-102">DocumentSheet_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9b8d6-102">DocumentSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9b8d6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9b8d6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9b8d6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9b8d6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9b8d6-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="9b8d6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9b8d6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9b8d6-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="9b8d6-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9b8d6-109">定义</span><span class="sxs-lookup"><span data-stu-id="9b8d6-109">Definition</span></span>

```XML
      <xs:complexType name="DocumentSheet_Type">
        <xs:complexContent>
        <xs:extension base="Sheet_Type">
      
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
    <xs:attribute name="UniqueID"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9b8d6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9b8d6-110">Elements and attributes</span></span>

<span data-ttu-id="9b8d6-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9b8d6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9b8d6-112">Child elements</span></span>

<span data-ttu-id="9b8d6-113">无。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9b8d6-114">属性</span><span class="sxs-lookup"><span data-stu-id="9b8d6-114">Attributes</span></span>

|<span data-ttu-id="9b8d6-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-115">**Attribute**</span></span>|<span data-ttu-id="9b8d6-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-116">**Type**</span></span>|<span data-ttu-id="9b8d6-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-117">**Required**</span></span>|<span data-ttu-id="9b8d6-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-118">**Description**</span></span>|<span data-ttu-id="9b8d6-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9b8d6-120">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="9b8d6-120">IsCustomName</span></span>  <br/> |<span data-ttu-id="9b8d6-121">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="9b8d6-121">xsd:boolean</span></span>  <br/> |<span data-ttu-id="9b8d6-122">可选</span><span class="sxs-lookup"><span data-stu-id="9b8d6-122">optional</span></span>  <br/> ||<span data-ttu-id="9b8d6-123">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-123">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="9b8d6-124">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="9b8d6-124">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="9b8d6-125">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="9b8d6-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="9b8d6-126">可选</span><span class="sxs-lookup"><span data-stu-id="9b8d6-126">optional</span></span>  <br/> ||<span data-ttu-id="9b8d6-127">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="9b8d6-128">名称</span><span class="sxs-lookup"><span data-stu-id="9b8d6-128">Name</span></span>  <br/> |<span data-ttu-id="9b8d6-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9b8d6-129">xsd:string</span></span>  <br/> |<span data-ttu-id="9b8d6-130">可选</span><span class="sxs-lookup"><span data-stu-id="9b8d6-130">optional</span></span>  <br/> ||<span data-ttu-id="9b8d6-131">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9b8d6-132">NameU</span><span class="sxs-lookup"><span data-stu-id="9b8d6-132">NameU</span></span>  <br/> |<span data-ttu-id="9b8d6-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9b8d6-133">xsd:string</span></span>  <br/> |<span data-ttu-id="9b8d6-134">可选</span><span class="sxs-lookup"><span data-stu-id="9b8d6-134">optional</span></span>  <br/> ||<span data-ttu-id="9b8d6-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9b8d6-136">UniqueID</span><span class="sxs-lookup"><span data-stu-id="9b8d6-136">UniqueID</span></span>  <br/> |<span data-ttu-id="9b8d6-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9b8d6-137">xsd:string</span></span>  <br/> |<span data-ttu-id="9b8d6-138">可选</span><span class="sxs-lookup"><span data-stu-id="9b8d6-138">optional</span></span>  <br/> ||<span data-ttu-id="9b8d6-139">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9b8d6-139">Values of the xsd:string type.</span></span>  <br/> |
   

