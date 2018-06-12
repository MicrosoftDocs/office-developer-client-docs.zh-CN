---
title: Validation 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db6292c7-9f4c-c287-803b-64fa41c0a269
description: 存储有关文档图表验证的信息。
ms.openlocfilehash: f4a7c0893baebb09dccd743c3006a5512dec533d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781613"
---
# <a name="validation-element-visio-xml"></a><span data-ttu-id="7f007-103">Validation 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="7f007-103">Validation element ('Visio XML')</span></span>

<span data-ttu-id="7f007-104">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="7f007-104">Stores information about diagram validation for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="7f007-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="7f007-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7f007-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="7f007-106">**Element type**</span></span> <br/> |[<span data-ttu-id="7f007-107">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="7f007-107">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="7f007-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="7f007-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="7f007-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="7f007-109">**Schema file**</span></span> <br/> |<span data-ttu-id="7f007-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="7f007-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="7f007-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="7f007-111">**Document parts**</span></span> <br/> |<span data-ttu-id="7f007-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="7f007-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="7f007-113">定义</span><span class="sxs-lookup"><span data-stu-id="7f007-113">Definition</span></span>

```XML
< xs:element name="Validation" type="Validation_Type" > </xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="7f007-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="7f007-114">Elements and attributes</span></span>

<span data-ttu-id="7f007-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="7f007-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="7f007-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7f007-116">Parent elements</span></span>

<span data-ttu-id="7f007-117">无。</span><span class="sxs-lookup"><span data-stu-id="7f007-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="7f007-118">子元素</span><span class="sxs-lookup"><span data-stu-id="7f007-118">Child elements</span></span>

|<span data-ttu-id="7f007-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="7f007-119">**Element**</span></span>|<span data-ttu-id="7f007-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="7f007-120">**Type**</span></span>|<span data-ttu-id="7f007-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="7f007-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="7f007-122">问题</span><span class="sxs-lookup"><span data-stu-id="7f007-122">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7f007-123">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="7f007-123">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7f007-124">包含文档的所有**问题**元素。</span><span class="sxs-lookup"><span data-stu-id="7f007-124">Contains all the **Issue** elements for the document.</span></span>  <br/> |
|[<span data-ttu-id="7f007-125">规则集</span><span class="sxs-lookup"><span data-stu-id="7f007-125">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7f007-126">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="7f007-126">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7f007-127">包括文档中设置每个有效性规则的**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="7f007-127">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
|[<span data-ttu-id="7f007-128">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="7f007-128">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="7f007-129">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="7f007-129">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="7f007-130">封装与文档的验证相关的属性。</span><span class="sxs-lookup"><span data-stu-id="7f007-130">Encapsulates the properties that are related to the document's validation.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="7f007-131">属性</span><span class="sxs-lookup"><span data-stu-id="7f007-131">Attributes</span></span>

<span data-ttu-id="7f007-132">无。</span><span class="sxs-lookup"><span data-stu-id="7f007-132">None.</span></span>
  

