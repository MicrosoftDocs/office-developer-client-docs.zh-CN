---
title: 'DocumentSheet_Type COMPLEXType (Visio XML) '
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
# <a name="documentsheet_type-complextype-visio-xml"></a><span data-ttu-id="fd023-102">DocumentSheet_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="fd023-102">DocumentSheet_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="fd023-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="fd023-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fd023-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fd023-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="fd023-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fd023-105">**Schema file**</span></span> <br/> |<span data-ttu-id="fd023-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="fd023-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="fd023-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="fd023-107">**Extension base**</span></span> <br/> |<span data-ttu-id="fd023-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="fd023-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fd023-109">定义</span><span class="sxs-lookup"><span data-stu-id="fd023-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="fd023-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fd023-110">Elements and attributes</span></span>

<span data-ttu-id="fd023-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fd023-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="fd023-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fd023-112">Child elements</span></span>

<span data-ttu-id="fd023-113">无。</span><span class="sxs-lookup"><span data-stu-id="fd023-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="fd023-114">属性</span><span class="sxs-lookup"><span data-stu-id="fd023-114">Attributes</span></span>

|<span data-ttu-id="fd023-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="fd023-115">**Attribute**</span></span>|<span data-ttu-id="fd023-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="fd023-116">**Type**</span></span>|<span data-ttu-id="fd023-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="fd023-117">**Required**</span></span>|<span data-ttu-id="fd023-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="fd023-118">**Description**</span></span>|<span data-ttu-id="fd023-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="fd023-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd023-120">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="fd023-120">IsCustomName</span></span>  <br/> |<span data-ttu-id="fd023-121">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="fd023-121">xsd:boolean</span></span>  <br/> |<span data-ttu-id="fd023-122">可选</span><span class="sxs-lookup"><span data-stu-id="fd023-122">optional</span></span>  <br/> ||<span data-ttu-id="fd023-123">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd023-123">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="fd023-124">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="fd023-124">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="fd023-125">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="fd023-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="fd023-126">可选</span><span class="sxs-lookup"><span data-stu-id="fd023-126">optional</span></span>  <br/> ||<span data-ttu-id="fd023-127">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd023-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="fd023-128">名称</span><span class="sxs-lookup"><span data-stu-id="fd023-128">Name</span></span>  <br/> |<span data-ttu-id="fd023-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd023-129">xsd:string</span></span>  <br/> |<span data-ttu-id="fd023-130">可选</span><span class="sxs-lookup"><span data-stu-id="fd023-130">optional</span></span>  <br/> ||<span data-ttu-id="fd023-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd023-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fd023-132">NameU</span><span class="sxs-lookup"><span data-stu-id="fd023-132">NameU</span></span>  <br/> |<span data-ttu-id="fd023-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd023-133">xsd:string</span></span>  <br/> |<span data-ttu-id="fd023-134">可选</span><span class="sxs-lookup"><span data-stu-id="fd023-134">optional</span></span>  <br/> ||<span data-ttu-id="fd023-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd023-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="fd023-136">UniqueID</span><span class="sxs-lookup"><span data-stu-id="fd023-136">UniqueID</span></span>  <br/> |<span data-ttu-id="fd023-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="fd023-137">xsd:string</span></span>  <br/> |<span data-ttu-id="fd023-138">可选</span><span class="sxs-lookup"><span data-stu-id="fd023-138">optional</span></span>  <br/> ||<span data-ttu-id="fd023-139">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="fd023-139">Values of the xsd:string type.</span></span>  <br/> |
   

