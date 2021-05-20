---
title: 'ComplexType (Rule_Type XML)  (Visio RuleFilter) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b05497e6-722f-9203-e03c-0f14a712cddb
description: 指定逻辑表达式，该表达式确定是否应当将验证规则应用于目标对象。
ms.openlocfilehash: 3abcd7e2dd093fa8e2321052e73835db22c150db
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541678"
---
# <a name="rulefilter-element-rule_type-complextype-visio-xml"></a><span data-ttu-id="6821a-103">ComplexType (Rule_Type XML)  (Visio RuleFilter) </span><span class="sxs-lookup"><span data-stu-id="6821a-103">RuleFilter element (Rule_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="6821a-104">指定逻辑表达式，该表达式确定是否应当将验证规则应用于目标对象。</span><span class="sxs-lookup"><span data-stu-id="6821a-104">Specifies the logical expression that determines whether the validation rule should be applied to a target object.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6821a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6821a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6821a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6821a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6821a-107">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="6821a-107">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6821a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6821a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6821a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6821a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6821a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6821a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6821a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6821a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6821a-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="6821a-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6821a-113">定义</span><span class="sxs-lookup"><span data-stu-id="6821a-113">Definition</span></span>

```XML
< xs:element name="RuleFilter" type="RuleFilter_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6821a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6821a-114">Elements and attributes</span></span>

<span data-ttu-id="6821a-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6821a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6821a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6821a-116">Parent elements</span></span>

|<span data-ttu-id="6821a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6821a-117">**Element**</span></span>|<span data-ttu-id="6821a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6821a-118">**Type**</span></span>|<span data-ttu-id="6821a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6821a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6821a-120">Rule</span><span class="sxs-lookup"><span data-stu-id="6821a-120">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6821a-121">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="6821a-121">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6821a-122">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="6821a-122">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6821a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6821a-123">Child elements</span></span>

<span data-ttu-id="6821a-124">无。</span><span class="sxs-lookup"><span data-stu-id="6821a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6821a-125">属性</span><span class="sxs-lookup"><span data-stu-id="6821a-125">Attributes</span></span>

|<span data-ttu-id="6821a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="6821a-126">**Attribute**</span></span>|<span data-ttu-id="6821a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="6821a-127">**Type**</span></span>|<span data-ttu-id="6821a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="6821a-128">**Required**</span></span>|<span data-ttu-id="6821a-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="6821a-129">**Description**</span></span>|<span data-ttu-id="6821a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6821a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6821a-131">公式</span><span class="sxs-lookup"><span data-stu-id="6821a-131">Formula</span></span>  <br/> |<span data-ttu-id="6821a-132">xsd：string</span><span class="sxs-lookup"><span data-stu-id="6821a-132">xsd:string</span></span>  <br/> |<span data-ttu-id="6821a-133">可选</span><span class="sxs-lookup"><span data-stu-id="6821a-133">optional</span></span>  <br/> |<span data-ttu-id="6821a-134">表示元素的公式。</span><span class="sxs-lookup"><span data-stu-id="6821a-134">Represents the element's formula.</span></span>  <br/> |<span data-ttu-id="6821a-135">xsd：string 的值。</span><span class="sxs-lookup"><span data-stu-id="6821a-135">Values of the xsd:string.</span></span>  <br/> |
   

