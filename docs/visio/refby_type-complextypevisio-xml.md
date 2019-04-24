---
title: RefBy_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e2990281-6410-5a35-2b28-3a8b33246c73
ms.openlocfilehash: ebfc84b2e7eb88078b3b8010f0a7001e90a9cb31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348319"
---
# <a name="refbytype-complextype-visio-xml"></a><span data-ttu-id="b7144-102">RefBy_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b7144-102">RefBy_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b7144-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b7144-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b7144-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b7144-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b7144-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b7144-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b7144-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b7144-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b7144-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b7144-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b7144-108">无</span><span class="sxs-lookup"><span data-stu-id="b7144-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b7144-109">定义</span><span class="sxs-lookup"><span data-stu-id="b7144-109">Definition</span></span>

```XML
      <xs:complexType name="RefBy_Type">
    <xs:attribute name="T"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="ID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b7144-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b7144-110">Elements and attributes</span></span>

<span data-ttu-id="b7144-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b7144-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b7144-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b7144-112">Child elements</span></span>

<span data-ttu-id="b7144-113">无。</span><span class="sxs-lookup"><span data-stu-id="b7144-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b7144-114">属性</span><span class="sxs-lookup"><span data-stu-id="b7144-114">Attributes</span></span>

|<span data-ttu-id="b7144-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="b7144-115">**Attribute**</span></span>|<span data-ttu-id="b7144-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="b7144-116">**Type**</span></span>|<span data-ttu-id="b7144-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="b7144-117">**Required**</span></span>|<span data-ttu-id="b7144-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="b7144-118">**Description**</span></span>|<span data-ttu-id="b7144-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="b7144-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7144-120">ID</span><span class="sxs-lookup"><span data-stu-id="b7144-120">ID</span></span>  <br/> |<span data-ttu-id="b7144-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b7144-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="b7144-122">必需</span><span class="sxs-lookup"><span data-stu-id="b7144-122">required</span></span>  <br/> ||<span data-ttu-id="b7144-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b7144-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="b7144-124">T</span><span class="sxs-lookup"><span data-stu-id="b7144-124">T</span></span>  <br/> |<span data-ttu-id="b7144-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="b7144-125">xsd:string</span></span>  <br/> |<span data-ttu-id="b7144-126">必需</span><span class="sxs-lookup"><span data-stu-id="b7144-126">required</span></span>  <br/> ||<span data-ttu-id="b7144-127">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="b7144-127">Values of the xsd:string type.</span></span>  <br/> |
   

