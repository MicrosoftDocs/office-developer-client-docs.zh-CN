---
title: 'RuleTest 元素 (Rule_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cb95b34-3ce0-07a5-5d57-8ac9b0570b9a
description: 指定逻辑表达式，该表达式确定目标对象是否满足验证规则。
ms.openlocfilehash: bb1f0cf9b3f712903f6e45d6d09f96607089f920
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541517"
---
# <a name="ruletest-element-rule_type-complextype-visio-xml"></a><span data-ttu-id="4b8db-103">RuleTest 元素 (Rule_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4b8db-103">RuleTest element (Rule_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="4b8db-104">指定逻辑表达式，该表达式确定目标对象是否满足验证规则。</span><span class="sxs-lookup"><span data-stu-id="4b8db-104">Specifies the logical expression that determines whether the target object satisfies the validation rule.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4b8db-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4b8db-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4b8db-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4b8db-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4b8db-107">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="4b8db-107">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4b8db-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4b8db-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4b8db-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4b8db-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4b8db-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4b8db-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4b8db-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4b8db-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4b8db-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="4b8db-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4b8db-113">定义</span><span class="sxs-lookup"><span data-stu-id="4b8db-113">Definition</span></span>

```XML
< xs:element name="RuleTest" type="RuleTest_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4b8db-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4b8db-114">Elements and attributes</span></span>

<span data-ttu-id="4b8db-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4b8db-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4b8db-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4b8db-116">Parent elements</span></span>

|<span data-ttu-id="4b8db-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4b8db-117">**Element**</span></span>|<span data-ttu-id="4b8db-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b8db-118">**Type**</span></span>|<span data-ttu-id="4b8db-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4b8db-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4b8db-120">Rule</span><span class="sxs-lookup"><span data-stu-id="4b8db-120">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4b8db-121">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="4b8db-121">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4b8db-122">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="4b8db-122">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4b8db-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4b8db-123">Child elements</span></span>

<span data-ttu-id="4b8db-124">无。</span><span class="sxs-lookup"><span data-stu-id="4b8db-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4b8db-125">属性</span><span class="sxs-lookup"><span data-stu-id="4b8db-125">Attributes</span></span>

|<span data-ttu-id="4b8db-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="4b8db-126">**Attribute**</span></span>|<span data-ttu-id="4b8db-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b8db-127">**Type**</span></span>|<span data-ttu-id="4b8db-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="4b8db-128">**Required**</span></span>|<span data-ttu-id="4b8db-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="4b8db-129">**Description**</span></span>|<span data-ttu-id="4b8db-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4b8db-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b8db-131">公式</span><span class="sxs-lookup"><span data-stu-id="4b8db-131">Formula</span></span>  <br/> |<span data-ttu-id="4b8db-132">xsd：string</span><span class="sxs-lookup"><span data-stu-id="4b8db-132">xsd:string</span></span>  <br/> |<span data-ttu-id="4b8db-133">可选</span><span class="sxs-lookup"><span data-stu-id="4b8db-133">optional</span></span>  <br/> |<span data-ttu-id="4b8db-134">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="4b8db-134">Represents the element's formula.</span></span>  <br/> |<span data-ttu-id="4b8db-135">xsd：string 的值。</span><span class="sxs-lookup"><span data-stu-id="4b8db-135">Values of the xsd:string.</span></span>  <br/> |
   

