---
title: RefBy_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e2990281-6410-5a35-2b28-3a8b33246c73
ms.openlocfilehash: ebfc84b2e7eb88078b3b8010f0a7001e90a9cb31
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383481"
---
# <a name="refbytype-complextype-visio-xml"></a><span data-ttu-id="49e74-102">RefBy_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="49e74-102">RefBy_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="49e74-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="49e74-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="49e74-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="49e74-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="49e74-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="49e74-105">**Schema file**</span></span> <br/> |<span data-ttu-id="49e74-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="49e74-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="49e74-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="49e74-107">**Extension base**</span></span> <br/> |<span data-ttu-id="49e74-108">无</span><span class="sxs-lookup"><span data-stu-id="49e74-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="49e74-109">定义</span><span class="sxs-lookup"><span data-stu-id="49e74-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="49e74-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="49e74-110">Elements and attributes</span></span>

<span data-ttu-id="49e74-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="49e74-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="49e74-112">子元素</span><span class="sxs-lookup"><span data-stu-id="49e74-112">Child elements</span></span>

<span data-ttu-id="49e74-113">无。</span><span class="sxs-lookup"><span data-stu-id="49e74-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="49e74-114">属性</span><span class="sxs-lookup"><span data-stu-id="49e74-114">Attributes</span></span>

|<span data-ttu-id="49e74-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="49e74-115">**Attribute**</span></span>|<span data-ttu-id="49e74-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="49e74-116">**Type**</span></span>|<span data-ttu-id="49e74-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="49e74-117">**Required**</span></span>|<span data-ttu-id="49e74-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="49e74-118">**Description**</span></span>|<span data-ttu-id="49e74-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="49e74-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49e74-120">ID</span><span class="sxs-lookup"><span data-stu-id="49e74-120">ID</span></span>  <br/> |<span data-ttu-id="49e74-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="49e74-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="49e74-122">必需</span><span class="sxs-lookup"><span data-stu-id="49e74-122">required</span></span>  <br/> ||<span data-ttu-id="49e74-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="49e74-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="49e74-124">T</span><span class="sxs-lookup"><span data-stu-id="49e74-124">T</span></span>  <br/> |<span data-ttu-id="49e74-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="49e74-125">xsd:string</span></span>  <br/> |<span data-ttu-id="49e74-126">必需</span><span class="sxs-lookup"><span data-stu-id="49e74-126">required</span></span>  <br/> ||<span data-ttu-id="49e74-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="49e74-127">Values of the xsd:string type.</span></span>  <br/> |
   

