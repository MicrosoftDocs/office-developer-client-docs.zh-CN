---
title: RuleTest 元素 (Rule_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cb95b34-3ce0-07a5-5d57-8ac9b0570b9a
description: 指定确定目标对象是否满足有效性规则的逻辑表达式。
ms.openlocfilehash: bb1f0cf9b3f712903f6e45d6d09f96607089f920
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541517"
---
# <a name="ruletest-element-ruletype-complextype-visio-xml"></a><span data-ttu-id="59338-103">RuleTest 元素 (Rule_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="59338-103">RuleTest element (Rule_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="59338-104">指定确定目标对象是否满足有效性规则的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="59338-104">Specifies the logical expression that determines whether the target object satisfies the validation rule.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="59338-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="59338-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="59338-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="59338-106">**Element type**</span></span> <br/> |[<span data-ttu-id="59338-107">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="59338-107">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="59338-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="59338-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="59338-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="59338-109">**Schema file**</span></span> <br/> |<span data-ttu-id="59338-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="59338-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="59338-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="59338-111">**Document parts**</span></span> <br/> |<span data-ttu-id="59338-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="59338-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="59338-113">定义</span><span class="sxs-lookup"><span data-stu-id="59338-113">Definition</span></span>

```XML
< xs:element name="RuleTest" type="RuleTest_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="59338-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="59338-114">Elements and attributes</span></span>

<span data-ttu-id="59338-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="59338-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="59338-116">父元素</span><span class="sxs-lookup"><span data-stu-id="59338-116">Parent elements</span></span>

|<span data-ttu-id="59338-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="59338-117">**Element**</span></span>|<span data-ttu-id="59338-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="59338-118">**Type**</span></span>|<span data-ttu-id="59338-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="59338-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="59338-120">Rule</span><span class="sxs-lookup"><span data-stu-id="59338-120">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="59338-121">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="59338-121">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="59338-122">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="59338-122">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="59338-123">子元素</span><span class="sxs-lookup"><span data-stu-id="59338-123">Child elements</span></span>

<span data-ttu-id="59338-124">无。</span><span class="sxs-lookup"><span data-stu-id="59338-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="59338-125">属性</span><span class="sxs-lookup"><span data-stu-id="59338-125">Attributes</span></span>

|<span data-ttu-id="59338-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="59338-126">**Attribute**</span></span>|<span data-ttu-id="59338-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="59338-127">**Type**</span></span>|<span data-ttu-id="59338-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="59338-128">**Required**</span></span>|<span data-ttu-id="59338-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="59338-129">**Description**</span></span>|<span data-ttu-id="59338-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="59338-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59338-131">公式</span><span class="sxs-lookup"><span data-stu-id="59338-131">Formula</span></span>  <br/> |<span data-ttu-id="59338-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="59338-132">xsd:string</span></span>  <br/> |<span data-ttu-id="59338-133">可选</span><span class="sxs-lookup"><span data-stu-id="59338-133">optional</span></span>  <br/> |<span data-ttu-id="59338-134">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="59338-134">Represents the element's formula.</span></span>  <br/> |<span data-ttu-id="59338-135">Xsd: 字符串的值。</span><span class="sxs-lookup"><span data-stu-id="59338-135">Values of the xsd:string.</span></span>  <br/> |
   

