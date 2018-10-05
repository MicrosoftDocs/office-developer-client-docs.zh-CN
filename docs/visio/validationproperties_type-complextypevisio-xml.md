---
title: ValidationProperties_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3b0d1209-4636-ea9c-acf7-895c3300492a
ms.openlocfilehash: 2fa6724ce6262886379f3ac22625927608184bab
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389979"
---
# <a name="validationpropertiestype-complextype-visio-xml"></a><span data-ttu-id="09a3c-102">ValidationProperties_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="09a3c-102">ValidationProperties_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="09a3c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="09a3c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="09a3c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="09a3c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="09a3c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="09a3c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="09a3c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="09a3c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="09a3c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="09a3c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="09a3c-108">无</span><span class="sxs-lookup"><span data-stu-id="09a3c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="09a3c-109">定义</span><span class="sxs-lookup"><span data-stu-id="09a3c-109">Definition</span></span>

```XML
      <xs:complexType name="ValidationProperties_Type">
    <xs:attribute name="LastValidated"
  type="xsd:dateTime"
     use="required"
    />
    <xs:attribute name="ShowIgnored"
  type="xsd:boolean"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="09a3c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="09a3c-110">Elements and attributes</span></span>

<span data-ttu-id="09a3c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="09a3c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="09a3c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="09a3c-112">Child elements</span></span>

<span data-ttu-id="09a3c-113">无。</span><span class="sxs-lookup"><span data-stu-id="09a3c-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="09a3c-114">属性</span><span class="sxs-lookup"><span data-stu-id="09a3c-114">Attributes</span></span>

|<span data-ttu-id="09a3c-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="09a3c-115">**Attribute**</span></span>|<span data-ttu-id="09a3c-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="09a3c-116">**Type**</span></span>|<span data-ttu-id="09a3c-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="09a3c-117">**Required**</span></span>|<span data-ttu-id="09a3c-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="09a3c-118">**Description**</span></span>|<span data-ttu-id="09a3c-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="09a3c-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09a3c-120">LastValidated</span><span class="sxs-lookup"><span data-stu-id="09a3c-120">LastValidated</span></span>  <br/> |<span data-ttu-id="09a3c-121">化</span><span class="sxs-lookup"><span data-stu-id="09a3c-121">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="09a3c-122">必需</span><span class="sxs-lookup"><span data-stu-id="09a3c-122">required</span></span>  <br/> ||<span data-ttu-id="09a3c-123">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="09a3c-123">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="09a3c-124">ShowIgnored</span><span class="sxs-lookup"><span data-stu-id="09a3c-124">ShowIgnored</span></span>  <br/> |<span data-ttu-id="09a3c-125">化</span><span class="sxs-lookup"><span data-stu-id="09a3c-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="09a3c-126">必需</span><span class="sxs-lookup"><span data-stu-id="09a3c-126">required</span></span>  <br/> ||<span data-ttu-id="09a3c-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="09a3c-127">Values of the xsd:boolean type.</span></span>  <br/> |
   

