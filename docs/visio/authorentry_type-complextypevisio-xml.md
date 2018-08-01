---
title: AuthorEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6ea7b946-ecd3-1524-5e36-a2c35cb11d7a
ms.openlocfilehash: 39cf47915230b18d22db78f5470fd9c26b9c77ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779642"
---
# <a name="authorentrytype-complextype-visio-xml"></a><span data-ttu-id="549a6-102">AuthorEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="549a6-102">AuthorEntry_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="549a6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="549a6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="549a6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="549a6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="549a6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="549a6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="549a6-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="549a6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="549a6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="549a6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="549a6-108">无</span><span class="sxs-lookup"><span data-stu-id="549a6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="549a6-109">定义</span><span class="sxs-lookup"><span data-stu-id="549a6-109">Definition</span></span>

```XML
      <xs:complexType name="AuthorEntry_Type">
    <xs:attribute name="Name"
  type="xsd:string"
    />
    <xs:attribute name="Initials"
  type="xsd:string"
    />
    <xs:attribute name="ResolutionID"
  type="xsd:string"
    />
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="549a6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="549a6-110">Elements and attributes</span></span>

<span data-ttu-id="549a6-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="549a6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="549a6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="549a6-112">Child elements</span></span>

<span data-ttu-id="549a6-113">无。</span><span class="sxs-lookup"><span data-stu-id="549a6-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="549a6-114">属性</span><span class="sxs-lookup"><span data-stu-id="549a6-114">Attributes</span></span>

|<span data-ttu-id="549a6-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="549a6-115">**Attribute**</span></span>|<span data-ttu-id="549a6-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="549a6-116">**Type**</span></span>|<span data-ttu-id="549a6-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="549a6-117">**Required**</span></span>|<span data-ttu-id="549a6-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="549a6-118">**Description**</span></span>|<span data-ttu-id="549a6-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="549a6-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="549a6-120">ID</span><span class="sxs-lookup"><span data-stu-id="549a6-120">ID</span></span>  <br/> |<span data-ttu-id="549a6-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="549a6-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="549a6-122">必需</span><span class="sxs-lookup"><span data-stu-id="549a6-122">required</span></span>  <br/> ||<span data-ttu-id="549a6-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="549a6-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="549a6-124">Initials</span><span class="sxs-lookup"><span data-stu-id="549a6-124">Initials</span></span>  <br/> |<span data-ttu-id="549a6-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="549a6-125">xsd:string</span></span>  <br/> |<span data-ttu-id="549a6-126">可选</span><span class="sxs-lookup"><span data-stu-id="549a6-126">optional</span></span>  <br/> ||<span data-ttu-id="549a6-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="549a6-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="549a6-128">名称</span><span class="sxs-lookup"><span data-stu-id="549a6-128">Name</span></span>  <br/> |<span data-ttu-id="549a6-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="549a6-129">xsd:string</span></span>  <br/> |<span data-ttu-id="549a6-130">可选</span><span class="sxs-lookup"><span data-stu-id="549a6-130">optional</span></span>  <br/> ||<span data-ttu-id="549a6-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="549a6-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="549a6-132">ResolutionID</span><span class="sxs-lookup"><span data-stu-id="549a6-132">ResolutionID</span></span>  <br/> |<span data-ttu-id="549a6-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="549a6-133">xsd:string</span></span>  <br/> |<span data-ttu-id="549a6-134">可选</span><span class="sxs-lookup"><span data-stu-id="549a6-134">optional</span></span>  <br/> ||<span data-ttu-id="549a6-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="549a6-135">Values of the xsd:string type.</span></span>  <br/> |
   

