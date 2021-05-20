---
title: 'RuleSets 元素 (Validation_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a0201e6-9a93-83ae-8a0a-47630ed291ce
description: 包括文档中每个验证字段规则集 RuleSet 元素。
ms.openlocfilehash: 0aca3f52bd8b201d1afc2ab7d647757452ff8899
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541573"
---
# <a name="rulesets-element-validation_type-complextype-visio-xml"></a><span data-ttu-id="a11b6-103">RuleSets 元素 (Validation_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="a11b6-103">RuleSets element (Validation_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="a11b6-104">包括文档中每个验证规则集 **RuleSet** 元素。</span><span class="sxs-lookup"><span data-stu-id="a11b6-104">Includes a **RuleSet** element for each validation rule set in the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="a11b6-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="a11b6-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a11b6-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="a11b6-106">**Element type**</span></span> <br/> |[<span data-ttu-id="a11b6-107">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="a11b6-107">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="a11b6-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a11b6-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="a11b6-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a11b6-109">**Schema file**</span></span> <br/> |<span data-ttu-id="a11b6-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="a11b6-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="a11b6-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="a11b6-111">**Document parts**</span></span> <br/> |<span data-ttu-id="a11b6-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="a11b6-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a11b6-113">定义</span><span class="sxs-lookup"><span data-stu-id="a11b6-113">Definition</span></span>

```XML
< xs:element name="RuleSets" type="RuleSets_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a11b6-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a11b6-114">Elements and attributes</span></span>

<span data-ttu-id="a11b6-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a11b6-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="a11b6-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a11b6-116">Parent elements</span></span>

|<span data-ttu-id="a11b6-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="a11b6-117">**Element**</span></span>|<span data-ttu-id="a11b6-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a11b6-118">**Type**</span></span>|<span data-ttu-id="a11b6-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a11b6-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a11b6-120">Validation</span><span class="sxs-lookup"><span data-stu-id="a11b6-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="a11b6-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="a11b6-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a11b6-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="a11b6-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="a11b6-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a11b6-123">Child elements</span></span>

|<span data-ttu-id="a11b6-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="a11b6-124">**Element**</span></span>|<span data-ttu-id="a11b6-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="a11b6-125">**Type**</span></span>|<span data-ttu-id="a11b6-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="a11b6-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a11b6-127">RuleSet</span><span class="sxs-lookup"><span data-stu-id="a11b6-127">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a11b6-128">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="a11b6-128">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a11b6-129">表示一组图表验证规则。</span><span class="sxs-lookup"><span data-stu-id="a11b6-129">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="a11b6-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="a11b6-130">Attributes</span></span>

<span data-ttu-id="a11b6-131">无。</span><span class="sxs-lookup"><span data-stu-id="a11b6-131">None.</span></span>
  

