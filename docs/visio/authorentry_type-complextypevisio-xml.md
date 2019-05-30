---
title: AuthorEntry_Type 复杂类型 (Visio XML)
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
# <a name="authorentrytype-complextype-visio-xml"></a><span data-ttu-id="b4d3a-102">AuthorEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b4d3a-102">AuthorEntry_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="b4d3a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b4d3a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b4d3a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b4d3a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b4d3a-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b4d3a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b4d3a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b4d3a-108">无</span><span class="sxs-lookup"><span data-stu-id="b4d3a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b4d3a-109">定义</span><span class="sxs-lookup"><span data-stu-id="b4d3a-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="b4d3a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b4d3a-110">Elements and attributes</span></span>

<span data-ttu-id="b4d3a-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b4d3a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b4d3a-112">Child elements</span></span>

<span data-ttu-id="b4d3a-113">无。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b4d3a-114">属性</span><span class="sxs-lookup"><span data-stu-id="b4d3a-114">Attributes</span></span>

|<span data-ttu-id="b4d3a-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-115">**Attribute**</span></span>|<span data-ttu-id="b4d3a-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-116">**Type**</span></span>|<span data-ttu-id="b4d3a-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-117">**Required**</span></span>|<span data-ttu-id="b4d3a-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-118">**Description**</span></span>|<span data-ttu-id="b4d3a-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b4d3a-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4d3a-120">ID</span><span class="sxs-lookup"><span data-stu-id="b4d3a-120">ID</span></span>  <br/> |<span data-ttu-id="b4d3a-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b4d3a-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b4d3a-122">必需</span><span class="sxs-lookup"><span data-stu-id="b4d3a-122">required</span></span>  <br/> ||<span data-ttu-id="b4d3a-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b4d3a-124">缩写</span><span class="sxs-lookup"><span data-stu-id="b4d3a-124">Initials</span></span>  <br/> |<span data-ttu-id="b4d3a-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b4d3a-125">xsd:string</span></span>  <br/> |<span data-ttu-id="b4d3a-126">可选</span><span class="sxs-lookup"><span data-stu-id="b4d3a-126">optional</span></span>  <br/> ||<span data-ttu-id="b4d3a-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-127">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b4d3a-128">名称</span><span class="sxs-lookup"><span data-stu-id="b4d3a-128">Name</span></span>  <br/> |<span data-ttu-id="b4d3a-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b4d3a-129">xsd:string</span></span>  <br/> |<span data-ttu-id="b4d3a-130">可选</span><span class="sxs-lookup"><span data-stu-id="b4d3a-130">optional</span></span>  <br/> ||<span data-ttu-id="b4d3a-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="b4d3a-132">ResolutionID</span><span class="sxs-lookup"><span data-stu-id="b4d3a-132">ResolutionID</span></span>  <br/> |<span data-ttu-id="b4d3a-133">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b4d3a-133">xsd:string</span></span>  <br/> |<span data-ttu-id="b4d3a-134">可选</span><span class="sxs-lookup"><span data-stu-id="b4d3a-134">optional</span></span>  <br/> ||<span data-ttu-id="b4d3a-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b4d3a-135">Values of the xsd:string type.</span></span>  <br/> |
   

