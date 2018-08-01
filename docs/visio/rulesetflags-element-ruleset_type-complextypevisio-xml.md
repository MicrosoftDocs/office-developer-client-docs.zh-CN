---
title: RuleSetFlags 元素 （RuleSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c18d3a84-2088-13f7-7b14-1f4c129537b4
description: 指定规则设置属性。
ms.openlocfilehash: f656e8ace045d45460ab353444c39c760448aa7b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781196"
---
# <a name="rulesetflags-element-rulesettype-complextype-visio-xml"></a><span data-ttu-id="3f7b3-103">RuleSetFlags 元素 （RuleSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3f7b3-103">RuleSetFlags element (RuleSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="3f7b3-104">指定规则设置属性。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-104">Specifies rule-set properties.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="3f7b3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="3f7b3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3f7b3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="3f7b3-107">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="3f7b3-107">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="3f7b3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="3f7b3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="3f7b3-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="3f7b3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="3f7b3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="3f7b3-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="3f7b3-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3f7b3-113">定义</span><span class="sxs-lookup"><span data-stu-id="3f7b3-113">Definition</span></span>

```XML
< xs:element name="RuleSetFlags" type="RuleSetFlags_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3f7b3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3f7b3-114">Elements and attributes</span></span>

<span data-ttu-id="3f7b3-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="3f7b3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="3f7b3-116">Parent elements</span></span>

|<span data-ttu-id="3f7b3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-117">**Element**</span></span>|<span data-ttu-id="3f7b3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-118">**Type**</span></span>|<span data-ttu-id="3f7b3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3f7b3-120">规则集</span><span class="sxs-lookup"><span data-stu-id="3f7b3-120">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3f7b3-121">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="3f7b3-121">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="3f7b3-122">代表一个图表验证规则集。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-122">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="3f7b3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="3f7b3-123">Child elements</span></span>

<span data-ttu-id="3f7b3-124">无。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3f7b3-125">属性</span><span class="sxs-lookup"><span data-stu-id="3f7b3-125">Attributes</span></span>

|<span data-ttu-id="3f7b3-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-126">**Attribute**</span></span>|<span data-ttu-id="3f7b3-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-127">**Type**</span></span>|<span data-ttu-id="3f7b3-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-128">**Required**</span></span>|<span data-ttu-id="3f7b3-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-129">**Description**</span></span>|<span data-ttu-id="3f7b3-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3f7b3-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f7b3-131">隐藏</span><span class="sxs-lookup"><span data-stu-id="3f7b3-131">Hidden</span></span>  <br/> |<span data-ttu-id="3f7b3-132">化</span><span class="sxs-lookup"><span data-stu-id="3f7b3-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="3f7b3-133">可选</span><span class="sxs-lookup"><span data-stu-id="3f7b3-133">optional</span></span>  <br/> |<span data-ttu-id="3f7b3-134">指定是否在规则检查列表中显示的规则集。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-134">Specifies whether the rule set appears in the Rules to Check list.</span></span>  <br/> |<span data-ttu-id="3f7b3-135">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="3f7b3-135">Values of the xsd:boolean type.</span></span>  <br/> |
   

