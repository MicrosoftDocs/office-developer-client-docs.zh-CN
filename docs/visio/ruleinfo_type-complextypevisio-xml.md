---
title: RuleInfo_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9ec3a334-dd0e-acc1-2b4e-026568b6f265
ms.openlocfilehash: 0548f2b493677ab63ef75548149e709645c0cf75
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382566"
---
# <a name="ruleinfotype-complextype-visio-xml"></a><span data-ttu-id="9d5cc-102">RuleInfo_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9d5cc-102">RuleInfo_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9d5cc-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9d5cc-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9d5cc-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9d5cc-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9d5cc-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="9d5cc-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9d5cc-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9d5cc-108">无</span><span class="sxs-lookup"><span data-stu-id="9d5cc-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9d5cc-109">定义</span><span class="sxs-lookup"><span data-stu-id="9d5cc-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="9d5cc-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9d5cc-110">Elements and attributes</span></span>

<span data-ttu-id="9d5cc-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9d5cc-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9d5cc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9d5cc-112">Child elements</span></span>

<span data-ttu-id="9d5cc-113">无。</span><span class="sxs-lookup"><span data-stu-id="9d5cc-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9d5cc-114">属性</span><span class="sxs-lookup"><span data-stu-id="9d5cc-114">Attributes</span></span>

|<span data-ttu-id="9d5cc-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-115">**Attribute**</span></span>|<span data-ttu-id="9d5cc-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-116">**Type**</span></span>|<span data-ttu-id="9d5cc-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-117">**Required**</span></span>|<span data-ttu-id="9d5cc-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-118">**Description**</span></span>|<span data-ttu-id="9d5cc-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9d5cc-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d5cc-120">规则 Id</span><span class="sxs-lookup"><span data-stu-id="9d5cc-120">RuleID</span></span>  <br/> |<span data-ttu-id="9d5cc-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9d5cc-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9d5cc-122">必需</span><span class="sxs-lookup"><span data-stu-id="9d5cc-122">required</span></span>  <br/> ||<span data-ttu-id="9d5cc-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9d5cc-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9d5cc-124">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="9d5cc-124">RuleSetID</span></span>  <br/> |<span data-ttu-id="9d5cc-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9d5cc-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9d5cc-126">必需</span><span class="sxs-lookup"><span data-stu-id="9d5cc-126">required</span></span>  <br/> ||<span data-ttu-id="9d5cc-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9d5cc-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

