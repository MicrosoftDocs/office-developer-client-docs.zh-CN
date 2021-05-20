---
title: 'AuthorEntry_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6ea7b946-ecd3-1524-5e36-a2c35cb11d7a
ms.openlocfilehash: 41279e9f4ffa0bba17d4f74eb2f40d724589c17d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537876"
---
# <a name="authorentry_type-complextype-visio-xml"></a><span data-ttu-id="11813-102">AuthorEntry_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="11813-102">AuthorEntry_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="11813-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="11813-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11813-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="11813-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="11813-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="11813-105">**Schema file**</span></span> <br/> |<span data-ttu-id="11813-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="11813-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="11813-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="11813-107">**Extension base**</span></span> <br/> |<span data-ttu-id="11813-108">无</span><span class="sxs-lookup"><span data-stu-id="11813-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="11813-109">定义</span><span class="sxs-lookup"><span data-stu-id="11813-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="11813-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="11813-110">Elements and attributes</span></span>

<span data-ttu-id="11813-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="11813-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="11813-112">子元素</span><span class="sxs-lookup"><span data-stu-id="11813-112">Child elements</span></span>

<span data-ttu-id="11813-113">无。</span><span class="sxs-lookup"><span data-stu-id="11813-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="11813-114">属性</span><span class="sxs-lookup"><span data-stu-id="11813-114">Attributes</span></span>

|<span data-ttu-id="11813-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="11813-115">**Attribute**</span></span>|<span data-ttu-id="11813-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="11813-116">**Type**</span></span>|<span data-ttu-id="11813-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="11813-117">**Required**</span></span>|<span data-ttu-id="11813-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="11813-118">**Description**</span></span>|<span data-ttu-id="11813-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="11813-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11813-120">ID</span><span class="sxs-lookup"><span data-stu-id="11813-120">ID</span></span>  <br/> |<span data-ttu-id="11813-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="11813-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="11813-122">必需</span><span class="sxs-lookup"><span data-stu-id="11813-122">required</span></span>  <br/> ||<span data-ttu-id="11813-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11813-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="11813-124">Initials</span><span class="sxs-lookup"><span data-stu-id="11813-124">Initials</span></span>  <br/> |<span data-ttu-id="11813-125">xsd：string</span><span class="sxs-lookup"><span data-stu-id="11813-125">xsd:string</span></span>  <br/> |<span data-ttu-id="11813-126">可选</span><span class="sxs-lookup"><span data-stu-id="11813-126">optional</span></span>  <br/> ||<span data-ttu-id="11813-127">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11813-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="11813-128">名称</span><span class="sxs-lookup"><span data-stu-id="11813-128">Name</span></span>  <br/> |<span data-ttu-id="11813-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="11813-129">xsd:string</span></span>  <br/> |<span data-ttu-id="11813-130">可选</span><span class="sxs-lookup"><span data-stu-id="11813-130">optional</span></span>  <br/> ||<span data-ttu-id="11813-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11813-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="11813-132">ResolutionID</span><span class="sxs-lookup"><span data-stu-id="11813-132">ResolutionID</span></span>  <br/> |<span data-ttu-id="11813-133">xsd：string</span><span class="sxs-lookup"><span data-stu-id="11813-133">xsd:string</span></span>  <br/> |<span data-ttu-id="11813-134">可选</span><span class="sxs-lookup"><span data-stu-id="11813-134">optional</span></span>  <br/> ||<span data-ttu-id="11813-135">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11813-135">Values of the xsd:string type.</span></span>  <br/> |
   

