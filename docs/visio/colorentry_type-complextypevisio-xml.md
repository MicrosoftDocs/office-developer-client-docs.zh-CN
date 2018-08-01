---
title: ColorEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d56b6110-634d-02d8-cf11-7902a2aaaf49
ms.openlocfilehash: 58a0abdd4f7f8c2014ec8c6763441840a07b93db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779886"
---
# <a name="colorentrytype-complextype-visio-xml"></a><span data-ttu-id="0eb13-102">ColorEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0eb13-102">ColorEntry_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="0eb13-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="0eb13-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0eb13-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0eb13-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="0eb13-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0eb13-105">**Schema file**</span></span> <br/> |<span data-ttu-id="0eb13-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="0eb13-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="0eb13-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0eb13-107">**Extension base**</span></span> <br/> |<span data-ttu-id="0eb13-108">无</span><span class="sxs-lookup"><span data-stu-id="0eb13-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0eb13-109">定义</span><span class="sxs-lookup"><span data-stu-id="0eb13-109">Definition</span></span>

```XML
      <xs:complexType name="ColorEntry_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="RGB"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0eb13-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0eb13-110">Elements and attributes</span></span>

<span data-ttu-id="0eb13-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0eb13-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0eb13-112">子元素</span><span class="sxs-lookup"><span data-stu-id="0eb13-112">Child elements</span></span>

<span data-ttu-id="0eb13-113">无。</span><span class="sxs-lookup"><span data-stu-id="0eb13-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0eb13-114">属性</span><span class="sxs-lookup"><span data-stu-id="0eb13-114">Attributes</span></span>

|<span data-ttu-id="0eb13-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="0eb13-115">**Attribute**</span></span>|<span data-ttu-id="0eb13-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="0eb13-116">**Type**</span></span>|<span data-ttu-id="0eb13-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="0eb13-117">**Required**</span></span>|<span data-ttu-id="0eb13-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="0eb13-118">**Description**</span></span>|<span data-ttu-id="0eb13-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0eb13-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0eb13-120">IX</span><span class="sxs-lookup"><span data-stu-id="0eb13-120">IX</span></span>  <br/> |<span data-ttu-id="0eb13-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0eb13-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="0eb13-122">必需</span><span class="sxs-lookup"><span data-stu-id="0eb13-122">required</span></span>  <br/> ||<span data-ttu-id="0eb13-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0eb13-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="0eb13-124">RGB</span><span class="sxs-lookup"><span data-stu-id="0eb13-124">RGB</span></span>  <br/> |<span data-ttu-id="0eb13-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0eb13-125">xsd:string</span></span>  <br/> |<span data-ttu-id="0eb13-126">必需</span><span class="sxs-lookup"><span data-stu-id="0eb13-126">required</span></span>  <br/> ||<span data-ttu-id="0eb13-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0eb13-127">Values of the xsd:string type.</span></span>  <br/> |
   

