---
title: RuleSets 元素 （Validation_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0201e6-9a93-83ae-8a0a-47630ed291ce
description: 包括文档中设置每个有效性规则的规则集元素。
ms.openlocfilehash: 84d64a8539f1b83c16a96a61ea68e9b2660c9036
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781206"
---
# <a name="rulesets-element-validationtype-complextype-visio-xml"></a><span data-ttu-id="0bfa9-103">RuleSets 元素 （Validation_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0bfa9-103">RuleSets element (Validation_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="0bfa9-104">包括文档中设置每个有效性规则的**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="0bfa9-104">Includes a **RuleSet** element for each validation rule set in the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="0bfa9-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="0bfa9-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0bfa9-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-106">**Element type**</span></span> <br/> |[<span data-ttu-id="0bfa9-107">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="0bfa9-107">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="0bfa9-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="0bfa9-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-109">**Schema file**</span></span> <br/> |<span data-ttu-id="0bfa9-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="0bfa9-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="0bfa9-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-111">**Document parts**</span></span> <br/> |<span data-ttu-id="0bfa9-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="0bfa9-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0bfa9-113">定义</span><span class="sxs-lookup"><span data-stu-id="0bfa9-113">Definition</span></span>

```XML
< xs:element name="RuleSets" type="RuleSets_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0bfa9-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0bfa9-114">Elements and attributes</span></span>

<span data-ttu-id="0bfa9-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0bfa9-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="0bfa9-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0bfa9-116">Parent elements</span></span>

|<span data-ttu-id="0bfa9-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-117">**Element**</span></span>|<span data-ttu-id="0bfa9-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-118">**Type**</span></span>|<span data-ttu-id="0bfa9-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0bfa9-120">验证</span><span class="sxs-lookup"><span data-stu-id="0bfa9-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="0bfa9-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="0bfa9-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0bfa9-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="0bfa9-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="0bfa9-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0bfa9-123">Child elements</span></span>

|<span data-ttu-id="0bfa9-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-124">**Element**</span></span>|<span data-ttu-id="0bfa9-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-125">**Type**</span></span>|<span data-ttu-id="0bfa9-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="0bfa9-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0bfa9-127">规则集</span><span class="sxs-lookup"><span data-stu-id="0bfa9-127">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0bfa9-128">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="0bfa9-128">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0bfa9-129">代表一个图表验证规则集。</span><span class="sxs-lookup"><span data-stu-id="0bfa9-129">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="0bfa9-130">属性</span><span class="sxs-lookup"><span data-stu-id="0bfa9-130">Attributes</span></span>

<span data-ttu-id="0bfa9-131">无。</span><span class="sxs-lookup"><span data-stu-id="0bfa9-131">None.</span></span>
  

