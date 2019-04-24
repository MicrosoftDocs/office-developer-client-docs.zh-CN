---
title: 规则集元素 (Validation_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0201e6-9a93-83ae-8a0a-47630ed291ce
description: 为文档中的每个有效性规则集包含一个规则集元素。
ms.openlocfilehash: 8c770de80a841a452908ae1a9f77a6dee25aad4d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319045"
---
# <a name="rulesets-element-validationtype-complextype-visio-xml"></a><span data-ttu-id="48805-103">规则集元素 (Validation_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="48805-103">RuleSets element (Validation_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="48805-104">为文档中的每个有效性规则集包含一个**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="48805-104">Includes a **RuleSet** element for each validation rule set in the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="48805-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="48805-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="48805-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="48805-106">**Element type**</span></span> <br/> |[<span data-ttu-id="48805-107">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="48805-107">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="48805-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="48805-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="48805-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="48805-109">**Schema file**</span></span> <br/> |<span data-ttu-id="48805-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="48805-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="48805-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="48805-111">**Document parts**</span></span> <br/> |<span data-ttu-id="48805-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="48805-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="48805-113">定义</span><span class="sxs-lookup"><span data-stu-id="48805-113">Definition</span></span>

```XML
< xs:element name="RuleSets" type="RuleSets_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="48805-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="48805-114">Elements and attributes</span></span>

<span data-ttu-id="48805-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="48805-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="48805-116">父元素</span><span class="sxs-lookup"><span data-stu-id="48805-116">Parent elements</span></span>

|<span data-ttu-id="48805-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="48805-117">**Element**</span></span>|<span data-ttu-id="48805-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="48805-118">**Type**</span></span>|<span data-ttu-id="48805-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="48805-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48805-120">Validation</span><span class="sxs-lookup"><span data-stu-id="48805-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="48805-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="48805-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48805-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="48805-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="48805-123">子元素</span><span class="sxs-lookup"><span data-stu-id="48805-123">Child elements</span></span>

|<span data-ttu-id="48805-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="48805-124">**Element**</span></span>|<span data-ttu-id="48805-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="48805-125">**Type**</span></span>|<span data-ttu-id="48805-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="48805-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48805-127">RuleSet</span><span class="sxs-lookup"><span data-stu-id="48805-127">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="48805-128">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="48805-128">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48805-129">表示一组图表有效性规则。</span><span class="sxs-lookup"><span data-stu-id="48805-129">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="48805-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="48805-130">Attributes</span></span>

<span data-ttu-id="48805-131">无。</span><span class="sxs-lookup"><span data-stu-id="48805-131">None.</span></span>
  

