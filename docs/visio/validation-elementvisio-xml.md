---
title: 'VALIDATION 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db6292c7-9f4c-c287-803b-64fa41c0a269
description: 存储有关文档图表验证的信息。
ms.openlocfilehash: b1b1bcbd70d57d7a7316e91d137cf8c3c3750722
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538548"
---
# <a name="validation-element-visio-xml"></a><span data-ttu-id="d9120-103">VALIDATION 元素 (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="d9120-103">Validation element (Visio XML)</span></span>

<span data-ttu-id="d9120-104">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="d9120-104">Stores information about diagram validation for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d9120-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d9120-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d9120-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d9120-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d9120-107">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="d9120-107">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d9120-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d9120-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d9120-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d9120-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d9120-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d9120-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d9120-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d9120-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d9120-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="d9120-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d9120-113">定义</span><span class="sxs-lookup"><span data-stu-id="d9120-113">Definition</span></span>

```XML
< xs:element name="Validation" type="Validation_Type" > </xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d9120-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d9120-114">Elements and attributes</span></span>

<span data-ttu-id="d9120-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d9120-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d9120-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d9120-116">Parent elements</span></span>

<span data-ttu-id="d9120-117">无。</span><span class="sxs-lookup"><span data-stu-id="d9120-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="d9120-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d9120-118">Child elements</span></span>

|<span data-ttu-id="d9120-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="d9120-119">**Element**</span></span>|<span data-ttu-id="d9120-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="d9120-120">**Type**</span></span>|<span data-ttu-id="d9120-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="d9120-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d9120-122">Issues</span><span class="sxs-lookup"><span data-stu-id="d9120-122">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d9120-123">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="d9120-123">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d9120-124">包含文档 **的所有 Issue** 元素。</span><span class="sxs-lookup"><span data-stu-id="d9120-124">Contains all the **Issue** elements for the document.</span></span>  <br/> |
|[<span data-ttu-id="d9120-125">RuleSets</span><span class="sxs-lookup"><span data-stu-id="d9120-125">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d9120-126">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="d9120-126">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d9120-127">包括文档中每个验证规则集 **RuleSet** 元素。</span><span class="sxs-lookup"><span data-stu-id="d9120-127">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
|[<span data-ttu-id="d9120-128">ValidationProperties</span><span class="sxs-lookup"><span data-stu-id="d9120-128">ValidationProperties</span></span>](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d9120-129">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="d9120-129">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d9120-130">封装与文档验证相关的属性。</span><span class="sxs-lookup"><span data-stu-id="d9120-130">Encapsulates the properties that are related to the document's validation.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d9120-131">Attributes</span><span class="sxs-lookup"><span data-stu-id="d9120-131">Attributes</span></span>

<span data-ttu-id="d9120-132">无。</span><span class="sxs-lookup"><span data-stu-id="d9120-132">None.</span></span>
  

