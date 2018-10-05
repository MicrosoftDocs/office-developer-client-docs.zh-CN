---
title: RuleFilter 元素 （Rule_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b05497e6-722f-9203-e03c-0f14a712cddb
description: 指定确定是否应将有效性规则应用于目标对象的逻辑表达式。
ms.openlocfilehash: 8d4167fbb8dde54c55e49debb77fe307ecab6771
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396725"
---
# <a name="rulefilter-element-ruletype-complextype-visio-xml"></a><span data-ttu-id="08de9-103">RuleFilter 元素 （Rule_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="08de9-103">RuleFilter element (Rule_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="08de9-104">指定确定是否应将有效性规则应用于目标对象的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="08de9-104">Specifies the logical expression that determines whether the validation rule should be applied to a target object.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="08de9-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="08de9-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08de9-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="08de9-106">**Element type**</span></span> <br/> |[<span data-ttu-id="08de9-107">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="08de9-107">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="08de9-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="08de9-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="08de9-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="08de9-109">**Schema file**</span></span> <br/> |<span data-ttu-id="08de9-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="08de9-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="08de9-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="08de9-111">**Document parts**</span></span> <br/> |<span data-ttu-id="08de9-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="08de9-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="08de9-113">定义</span><span class="sxs-lookup"><span data-stu-id="08de9-113">Definition</span></span>

```XML
< xs:element name="RuleFilter" type="RuleFilter_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="08de9-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="08de9-114">Elements and attributes</span></span>

<span data-ttu-id="08de9-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="08de9-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="08de9-116">父元素</span><span class="sxs-lookup"><span data-stu-id="08de9-116">Parent elements</span></span>

|<span data-ttu-id="08de9-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="08de9-117">**Element**</span></span>|<span data-ttu-id="08de9-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="08de9-118">**Type**</span></span>|<span data-ttu-id="08de9-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="08de9-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="08de9-120">Rule</span><span class="sxs-lookup"><span data-stu-id="08de9-120">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="08de9-121">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="08de9-121">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="08de9-122">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="08de9-122">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="08de9-123">子元素</span><span class="sxs-lookup"><span data-stu-id="08de9-123">Child elements</span></span>

<span data-ttu-id="08de9-124">无。</span><span class="sxs-lookup"><span data-stu-id="08de9-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="08de9-125">属性</span><span class="sxs-lookup"><span data-stu-id="08de9-125">Attributes</span></span>

|<span data-ttu-id="08de9-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="08de9-126">**Attribute**</span></span>|<span data-ttu-id="08de9-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="08de9-127">**Type**</span></span>|<span data-ttu-id="08de9-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="08de9-128">**Required**</span></span>|<span data-ttu-id="08de9-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="08de9-129">**Description**</span></span>|<span data-ttu-id="08de9-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="08de9-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08de9-131">公式</span><span class="sxs-lookup"><span data-stu-id="08de9-131">Formula</span></span>  <br/> |<span data-ttu-id="08de9-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="08de9-132">xsd:string</span></span>  <br/> |<span data-ttu-id="08de9-133">可选</span><span class="sxs-lookup"><span data-stu-id="08de9-133">optional</span></span>  <br/> |<span data-ttu-id="08de9-134">代表元素的公式。</span><span class="sxs-lookup"><span data-stu-id="08de9-134">Represents the element's formula.</span></span>  <br/> |<span data-ttu-id="08de9-135">Xsd: string 的值。</span><span class="sxs-lookup"><span data-stu-id="08de9-135">Values of the xsd:string.</span></span>  <br/> |
   

