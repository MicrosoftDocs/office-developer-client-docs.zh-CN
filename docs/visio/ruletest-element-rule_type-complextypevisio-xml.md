---
title: RuleTest 元素 （Rule_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cb95b34-3ce0-07a5-5d57-8ac9b0570b9a
description: 指定确定目标对象是否满足有效性规则的逻辑表达式。
ms.openlocfilehash: 25569530af5bc6f4b00e8600d1e25d968a01f246
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781203"
---
# <a name="ruletest-element-ruletype-complextype-visio-xml"></a><span data-ttu-id="d1c34-103">RuleTest 元素 （Rule_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d1c34-103">RuleTest element (Rule_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d1c34-104">指定确定目标对象是否满足有效性规则的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="d1c34-104">Specifies the logical expression that determines whether the target object satisfies the validation rule.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d1c34-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d1c34-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d1c34-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d1c34-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d1c34-107">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="d1c34-107">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d1c34-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d1c34-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d1c34-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d1c34-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d1c34-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d1c34-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d1c34-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d1c34-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d1c34-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="d1c34-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d1c34-113">定义</span><span class="sxs-lookup"><span data-stu-id="d1c34-113">Definition</span></span>

```XML
< xs:element name="RuleTest" type="RuleTest_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d1c34-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d1c34-114">Elements and attributes</span></span>

<span data-ttu-id="d1c34-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d1c34-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d1c34-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d1c34-116">Parent elements</span></span>

|<span data-ttu-id="d1c34-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1c34-117">**Element**</span></span>|<span data-ttu-id="d1c34-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1c34-118">**Type**</span></span>|<span data-ttu-id="d1c34-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1c34-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d1c34-120">Rule</span><span class="sxs-lookup"><span data-stu-id="d1c34-120">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1c34-121">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="d1c34-121">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1c34-122">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="d1c34-122">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d1c34-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d1c34-123">Child elements</span></span>

<span data-ttu-id="d1c34-124">无。</span><span class="sxs-lookup"><span data-stu-id="d1c34-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d1c34-125">属性</span><span class="sxs-lookup"><span data-stu-id="d1c34-125">Attributes</span></span>

|<span data-ttu-id="d1c34-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d1c34-126">**Attribute**</span></span>|<span data-ttu-id="d1c34-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1c34-127">**Type**</span></span>|<span data-ttu-id="d1c34-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d1c34-128">**Required**</span></span>|<span data-ttu-id="d1c34-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1c34-129">**Description**</span></span>|<span data-ttu-id="d1c34-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d1c34-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1c34-131">公式</span><span class="sxs-lookup"><span data-stu-id="d1c34-131">Formula</span></span>  <br/> |<span data-ttu-id="d1c34-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="d1c34-132">xsd:string</span></span>  <br/> |<span data-ttu-id="d1c34-133">可选</span><span class="sxs-lookup"><span data-stu-id="d1c34-133">optional</span></span>  <br/> |<span data-ttu-id="d1c34-134">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="d1c34-134">Represents the element's formula.</span></span>  <br/> |<span data-ttu-id="d1c34-135">Xsd: string 的值。</span><span class="sxs-lookup"><span data-stu-id="d1c34-135">Values of the xsd:string.</span></span>  <br/> |
   

