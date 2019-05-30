---
title: DocumentSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 57af2ed5-7d89-9538-e51b-0bc70f067b40
ms.openlocfilehash: 18e7f064b1b6c9ac8e084c96011c1b18a646aecb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540005"
---
# <a name="documentsheettype-complextype-visio-xml"></a><span data-ttu-id="be2b0-102">DocumentSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="be2b0-102">DocumentSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="be2b0-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="be2b0-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="be2b0-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="be2b0-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="be2b0-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="be2b0-105">**Schema file**</span></span> <br/> |<span data-ttu-id="be2b0-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="be2b0-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="be2b0-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="be2b0-107">**Extension base**</span></span> <br/> |<span data-ttu-id="be2b0-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="be2b0-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="be2b0-109">定义</span><span class="sxs-lookup"><span data-stu-id="be2b0-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="be2b0-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="be2b0-110">Elements and attributes</span></span>

<span data-ttu-id="be2b0-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="be2b0-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="be2b0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="be2b0-112">Child elements</span></span>

<span data-ttu-id="be2b0-113">无。</span><span class="sxs-lookup"><span data-stu-id="be2b0-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="be2b0-114">属性</span><span class="sxs-lookup"><span data-stu-id="be2b0-114">Attributes</span></span>

|<span data-ttu-id="be2b0-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="be2b0-115">**Attribute**</span></span>|<span data-ttu-id="be2b0-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="be2b0-116">**Type**</span></span>|<span data-ttu-id="be2b0-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="be2b0-117">**Required**</span></span>|<span data-ttu-id="be2b0-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="be2b0-118">**Description**</span></span>|<span data-ttu-id="be2b0-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="be2b0-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be2b0-120">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="be2b0-120">IsCustomName</span></span>  <br/> |<span data-ttu-id="be2b0-121">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="be2b0-121">xsd:boolean</span></span>  <br/> |<span data-ttu-id="be2b0-122">可选</span><span class="sxs-lookup"><span data-stu-id="be2b0-122">optional</span></span>  <br/> ||<span data-ttu-id="be2b0-123">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="be2b0-123">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="be2b0-124">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="be2b0-124">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="be2b0-125">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="be2b0-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="be2b0-126">可选</span><span class="sxs-lookup"><span data-stu-id="be2b0-126">optional</span></span>  <br/> ||<span data-ttu-id="be2b0-127">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="be2b0-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="be2b0-128">名称</span><span class="sxs-lookup"><span data-stu-id="be2b0-128">Name</span></span>  <br/> |<span data-ttu-id="be2b0-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="be2b0-129">xsd:string</span></span>  <br/> |<span data-ttu-id="be2b0-130">可选</span><span class="sxs-lookup"><span data-stu-id="be2b0-130">optional</span></span>  <br/> ||<span data-ttu-id="be2b0-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="be2b0-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="be2b0-132">NameU</span><span class="sxs-lookup"><span data-stu-id="be2b0-132">NameU</span></span>  <br/> |<span data-ttu-id="be2b0-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="be2b0-133">xsd:string</span></span>  <br/> |<span data-ttu-id="be2b0-134">可选</span><span class="sxs-lookup"><span data-stu-id="be2b0-134">optional</span></span>  <br/> ||<span data-ttu-id="be2b0-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="be2b0-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="be2b0-136">UniqueID</span><span class="sxs-lookup"><span data-stu-id="be2b0-136">UniqueID</span></span>  <br/> |<span data-ttu-id="be2b0-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="be2b0-137">xsd:string</span></span>  <br/> |<span data-ttu-id="be2b0-138">可选</span><span class="sxs-lookup"><span data-stu-id="be2b0-138">optional</span></span>  <br/> ||<span data-ttu-id="be2b0-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="be2b0-139">Values of the xsd:string type.</span></span>  <br/> |
   

