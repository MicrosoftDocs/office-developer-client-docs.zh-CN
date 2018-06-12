---
title: RuleInfo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9ec3a334-dd0e-acc1-2b4e-026568b6f265
ms.openlocfilehash: 0a0ac32729b83a5d648b2826bffe5a9df4d9fc0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781185"
---
# <a name="ruleinfotype-complextype-visio-xml"></a><span data-ttu-id="ecb5d-102">RuleInfo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ecb5d-102">RuleInfo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ecb5d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ecb5d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ecb5d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ecb5d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ecb5d-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="ecb5d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ecb5d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ecb5d-108">无</span><span class="sxs-lookup"><span data-stu-id="ecb5d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ecb5d-109">定义</span><span class="sxs-lookup"><span data-stu-id="ecb5d-109">Definition</span></span>

```XML
      <xs:complexType name="RuleInfo_Type">
    <xs:attribute name="RuleSetID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="RuleID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ecb5d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ecb5d-110">Elements and attributes</span></span>

<span data-ttu-id="ecb5d-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ecb5d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ecb5d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ecb5d-112">Child elements</span></span>

<span data-ttu-id="ecb5d-113">无。</span><span class="sxs-lookup"><span data-stu-id="ecb5d-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ecb5d-114">属性</span><span class="sxs-lookup"><span data-stu-id="ecb5d-114">Attributes</span></span>

|<span data-ttu-id="ecb5d-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-115">**Attribute**</span></span>|<span data-ttu-id="ecb5d-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-116">**Type**</span></span>|<span data-ttu-id="ecb5d-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-117">**Required**</span></span>|<span data-ttu-id="ecb5d-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-118">**Description**</span></span>|<span data-ttu-id="ecb5d-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ecb5d-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ecb5d-120">规则 Id</span><span class="sxs-lookup"><span data-stu-id="ecb5d-120">RuleID</span></span>  <br/> |<span data-ttu-id="ecb5d-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ecb5d-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ecb5d-122">必需</span><span class="sxs-lookup"><span data-stu-id="ecb5d-122">required</span></span>  <br/> ||<span data-ttu-id="ecb5d-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ecb5d-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ecb5d-124">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="ecb5d-124">RuleSetID</span></span>  <br/> |<span data-ttu-id="ecb5d-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ecb5d-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ecb5d-126">必需</span><span class="sxs-lookup"><span data-stu-id="ecb5d-126">required</span></span>  <br/> ||<span data-ttu-id="ecb5d-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ecb5d-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

