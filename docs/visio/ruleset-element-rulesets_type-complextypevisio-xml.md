---
title: RuleSet 元素 （RuleSets_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 代表一个图表验证规则集。
ms.openlocfilehash: ae8fc52dd665e51f38c7eeae2f12ff778937d565
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781200"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a><span data-ttu-id="4de25-103">RuleSet 元素 （RuleSets_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4de25-103">RuleSet element (RuleSets_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="4de25-104">代表一个图表验证规则集。</span><span class="sxs-lookup"><span data-stu-id="4de25-104">Represents one set of diagram-validation rules.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4de25-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4de25-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4de25-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4de25-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4de25-107">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="4de25-107">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4de25-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4de25-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4de25-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4de25-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4de25-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4de25-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4de25-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4de25-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4de25-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="4de25-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4de25-113">定义</span><span class="sxs-lookup"><span data-stu-id="4de25-113">Definition</span></span>

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4de25-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4de25-114">Elements and attributes</span></span>

<span data-ttu-id="4de25-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4de25-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4de25-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4de25-116">Parent elements</span></span>

|<span data-ttu-id="4de25-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de25-117">**Element**</span></span>|<span data-ttu-id="4de25-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de25-118">**Type**</span></span>|<span data-ttu-id="4de25-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de25-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de25-120">规则集</span><span class="sxs-lookup"><span data-stu-id="4de25-120">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de25-121">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="4de25-121">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de25-122">包括文档中设置每个有效性规则的**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="4de25-122">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4de25-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4de25-123">Child elements</span></span>

|<span data-ttu-id="4de25-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="4de25-124">**Element**</span></span>|<span data-ttu-id="4de25-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de25-125">**Type**</span></span>|<span data-ttu-id="4de25-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de25-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4de25-127">Rule</span><span class="sxs-lookup"><span data-stu-id="4de25-127">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de25-128">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="4de25-128">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de25-129">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="4de25-129">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
|[<span data-ttu-id="4de25-130">RuleSetFlags</span><span class="sxs-lookup"><span data-stu-id="4de25-130">RuleSetFlags</span></span>](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4de25-131">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="4de25-131">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4de25-132">指定规则设置属性。</span><span class="sxs-lookup"><span data-stu-id="4de25-132">Specifies rule-set properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4de25-133">属性</span><span class="sxs-lookup"><span data-stu-id="4de25-133">Attributes</span></span>

|<span data-ttu-id="4de25-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="4de25-134">**Attribute**</span></span>|<span data-ttu-id="4de25-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="4de25-135">**Type**</span></span>|<span data-ttu-id="4de25-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="4de25-136">**Required**</span></span>|<span data-ttu-id="4de25-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="4de25-137">**Description**</span></span>|<span data-ttu-id="4de25-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4de25-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4de25-139">说明</span><span class="sxs-lookup"><span data-stu-id="4de25-139">Description</span></span>  <br/> |<span data-ttu-id="4de25-140">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de25-140">xsd:string</span></span>  <br/> |<span data-ttu-id="4de25-141">可选</span><span class="sxs-lookup"><span data-stu-id="4de25-141">optional</span></span>  <br/> |<span data-ttu-id="4de25-142">指定在验证规则集的用户界面中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="4de25-142">Specifies the description that appears in the user interface for the validation rule set.</span></span> <span data-ttu-id="4de25-143">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="4de25-143">Default is an empty string.</span></span>  <br/> |<span data-ttu-id="4de25-144">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de25-144">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4de25-145">已启用</span><span class="sxs-lookup"><span data-stu-id="4de25-145">Enabled</span></span>  <br/> |<span data-ttu-id="4de25-146">化</span><span class="sxs-lookup"><span data-stu-id="4de25-146">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4de25-147">可选</span><span class="sxs-lookup"><span data-stu-id="4de25-147">optional</span></span>  <br/> |<span data-ttu-id="4de25-148">指定验证触发为当前文档时是否检查中指定的有效性规则集的规则。</span><span class="sxs-lookup"><span data-stu-id="4de25-148">Specifies whether the rules in the specified validation rule set are checked when validation is triggered for the current document.</span></span> <span data-ttu-id="4de25-149">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="4de25-149">Default is True.</span></span>  <br/> |<span data-ttu-id="4de25-150">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de25-150">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4de25-151">ID</span><span class="sxs-lookup"><span data-stu-id="4de25-151">ID</span></span>  <br/> |<span data-ttu-id="4de25-152">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4de25-152">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4de25-153">必需</span><span class="sxs-lookup"><span data-stu-id="4de25-153">required</span></span>  <br/> |<span data-ttu-id="4de25-154">指定有效性规则集的唯一的标识符。</span><span class="sxs-lookup"><span data-stu-id="4de25-154">Specifies the unique identifier of the validation rule set.</span></span>  <br/> |<span data-ttu-id="4de25-155">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de25-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4de25-156">名称</span><span class="sxs-lookup"><span data-stu-id="4de25-156">Name</span></span>  <br/> |<span data-ttu-id="4de25-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de25-157">xsd:string</span></span>  <br/> |<span data-ttu-id="4de25-158">可选</span><span class="sxs-lookup"><span data-stu-id="4de25-158">optional</span></span>  <br/> |<span data-ttu-id="4de25-159">指定有效性规则集的本地的名称。</span><span class="sxs-lookup"><span data-stu-id="4de25-159">Specifies the local name of the validation rule set.</span></span> <span data-ttu-id="4de25-160">默认值为 NameU 属性值。</span><span class="sxs-lookup"><span data-stu-id="4de25-160">Defaults to NameU attribute value.</span></span>  <br/> |<span data-ttu-id="4de25-161">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de25-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="4de25-162">NameU</span><span class="sxs-lookup"><span data-stu-id="4de25-162">NameU</span></span>  <br/> |<span data-ttu-id="4de25-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4de25-163">xsd:string</span></span>  <br/> |<span data-ttu-id="4de25-164">必需</span><span class="sxs-lookup"><span data-stu-id="4de25-164">required</span></span>  <br/> |<span data-ttu-id="4de25-165">指定有效性规则集的通用的名称。</span><span class="sxs-lookup"><span data-stu-id="4de25-165">Specifies the universal name of the validation rule set.</span></span>  <br/> |<span data-ttu-id="4de25-166">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4de25-166">Values of the xsd:string type.</span></span>  <br/> |
   
