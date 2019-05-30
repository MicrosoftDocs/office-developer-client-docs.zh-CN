---
title: RuleSetFlags 元素 (RuleSet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c18d3a84-2088-13f7-7b14-1f4c129537b4
description: 指定规则集属性。
ms.openlocfilehash: 03b94abb2d9bbe1f611671a4ac37053747a486fb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541594"
---
# <a name="rulesetflags-element-rulesettype-complextype-visio-xml"></a><span data-ttu-id="025b7-103">RuleSetFlags 元素 (RuleSet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="025b7-103">RuleSetFlags element (RuleSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="025b7-104">指定规则集属性。</span><span class="sxs-lookup"><span data-stu-id="025b7-104">Specifies rule-set properties.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="025b7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="025b7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="025b7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="025b7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="025b7-107">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="025b7-107">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="025b7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="025b7-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="025b7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="025b7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="025b7-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="025b7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="025b7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="025b7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="025b7-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="025b7-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="025b7-113">定义</span><span class="sxs-lookup"><span data-stu-id="025b7-113">Definition</span></span>

```XML
< xs:element name="RuleSetFlags" type="RuleSetFlags_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="025b7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="025b7-114">Elements and attributes</span></span>

<span data-ttu-id="025b7-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="025b7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="025b7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="025b7-116">Parent elements</span></span>

|<span data-ttu-id="025b7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="025b7-117">**Element**</span></span>|<span data-ttu-id="025b7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="025b7-118">**Type**</span></span>|<span data-ttu-id="025b7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="025b7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="025b7-120">RuleSet</span><span class="sxs-lookup"><span data-stu-id="025b7-120">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="025b7-121">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="025b7-121">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="025b7-122">表示一组图表有效性规则。</span><span class="sxs-lookup"><span data-stu-id="025b7-122">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="025b7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="025b7-123">Child elements</span></span>

<span data-ttu-id="025b7-124">无。</span><span class="sxs-lookup"><span data-stu-id="025b7-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="025b7-125">属性</span><span class="sxs-lookup"><span data-stu-id="025b7-125">Attributes</span></span>

|<span data-ttu-id="025b7-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="025b7-126">**Attribute**</span></span>|<span data-ttu-id="025b7-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="025b7-127">**Type**</span></span>|<span data-ttu-id="025b7-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="025b7-128">**Required**</span></span>|<span data-ttu-id="025b7-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="025b7-129">**Description**</span></span>|<span data-ttu-id="025b7-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="025b7-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="025b7-131">Hidden</span><span class="sxs-lookup"><span data-stu-id="025b7-131">Hidden</span></span>  <br/> |<span data-ttu-id="025b7-132">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="025b7-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="025b7-133">可选</span><span class="sxs-lookup"><span data-stu-id="025b7-133">optional</span></span>  <br/> |<span data-ttu-id="025b7-134">指定规则集是否出现在 "要检查的规则" 列表中。</span><span class="sxs-lookup"><span data-stu-id="025b7-134">Specifies whether the rule set appears in the Rules to Check list.</span></span>  <br/> |<span data-ttu-id="025b7-135">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="025b7-135">Values of the xsd:boolean type.</span></span>  <br/> |
   

