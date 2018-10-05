---
title: Validation 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db6292c7-9f4c-c287-803b-64fa41c0a269
description: 存储有关文档图表验证的信息。
ms.openlocfilehash: 7e40cd3a79922b56800cbb566a0d88de23829cc0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382356"
---
# <a name="validation-element-visio-xml"></a><span data-ttu-id="b9908-103">Validation 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b9908-103">Validation element ('Visio XML')</span></span>

<span data-ttu-id="b9908-104">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="b9908-104">Stores information about diagram validation for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b9908-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b9908-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b9908-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b9908-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b9908-107">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="b9908-107">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b9908-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b9908-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b9908-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b9908-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b9908-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b9908-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b9908-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b9908-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b9908-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="b9908-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b9908-113">定义</span><span class="sxs-lookup"><span data-stu-id="b9908-113">Definition</span></span>

```XML
< xs:element name="Validation" type="Validation_Type" > </xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b9908-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b9908-114">Elements and attributes</span></span>

<span data-ttu-id="b9908-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b9908-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b9908-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b9908-116">Parent elements</span></span>

<span data-ttu-id="b9908-117">无。</span><span class="sxs-lookup"><span data-stu-id="b9908-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b9908-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b9908-118">Child elements</span></span>

|<span data-ttu-id="b9908-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="b9908-119">**Element**</span></span>|<span data-ttu-id="b9908-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="b9908-120">**Type**</span></span>|<span data-ttu-id="b9908-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9908-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b9908-122">问题</span><span class="sxs-lookup"><span data-stu-id="b9908-122">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b9908-123">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="b9908-123">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b9908-124">包含文档的所有**问题**元素。</span><span class="sxs-lookup"><span data-stu-id="b9908-124">Contains all the **Issue** elements for the document.</span></span>  <br/> |
|[<span data-ttu-id="b9908-125">规则集</span><span class="sxs-lookup"><span data-stu-id="b9908-125">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b9908-126">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="b9908-126">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b9908-127">包括文档中设置每个有效性规则的**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="b9908-127">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
|[<span data-ttu-id="b9908-128">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="b9908-128">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b9908-129">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="b9908-129">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b9908-130">封装与文档的验证相关的属性。</span><span class="sxs-lookup"><span data-stu-id="b9908-130">Encapsulates the properties that are related to the document's validation.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="b9908-131">Attributes</span><span class="sxs-lookup"><span data-stu-id="b9908-131">Attributes</span></span>

<span data-ttu-id="b9908-132">无。</span><span class="sxs-lookup"><span data-stu-id="b9908-132">None.</span></span>
  

