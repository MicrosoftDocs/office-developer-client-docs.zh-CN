---
title: ColorEntry_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d56b6110-634d-02d8-cf11-7902a2aaaf49
ms.openlocfilehash: c5f2cafba60cd8157f80dc548cea328d179e74db
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394907"
---
# <a name="colorentrytype-complextype-visio-xml"></a><span data-ttu-id="155c9-102">ColorEntry_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="155c9-102">ColorEntry_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="155c9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="155c9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="155c9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="155c9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="155c9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="155c9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="155c9-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="155c9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="155c9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="155c9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="155c9-108">无</span><span class="sxs-lookup"><span data-stu-id="155c9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="155c9-109">定义</span><span class="sxs-lookup"><span data-stu-id="155c9-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="155c9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="155c9-110">Elements and attributes</span></span>

<span data-ttu-id="155c9-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="155c9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="155c9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="155c9-112">Child elements</span></span>

<span data-ttu-id="155c9-113">无。</span><span class="sxs-lookup"><span data-stu-id="155c9-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="155c9-114">属性</span><span class="sxs-lookup"><span data-stu-id="155c9-114">Attributes</span></span>

|<span data-ttu-id="155c9-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="155c9-115">**Attribute**</span></span>|<span data-ttu-id="155c9-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="155c9-116">**Type**</span></span>|<span data-ttu-id="155c9-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="155c9-117">**Required**</span></span>|<span data-ttu-id="155c9-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="155c9-118">**Description**</span></span>|<span data-ttu-id="155c9-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="155c9-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="155c9-120">IX</span><span class="sxs-lookup"><span data-stu-id="155c9-120">IX</span></span>  <br/> |<span data-ttu-id="155c9-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="155c9-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="155c9-122">必需</span><span class="sxs-lookup"><span data-stu-id="155c9-122">required</span></span>  <br/> ||<span data-ttu-id="155c9-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="155c9-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="155c9-124">RGB</span><span class="sxs-lookup"><span data-stu-id="155c9-124">RGB</span></span>  <br/> |<span data-ttu-id="155c9-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="155c9-125">xsd:string</span></span>  <br/> |<span data-ttu-id="155c9-126">必需</span><span class="sxs-lookup"><span data-stu-id="155c9-126">required</span></span>  <br/> ||<span data-ttu-id="155c9-127">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="155c9-127">Values of the xsd:string type.</span></span>  <br/> |
   

