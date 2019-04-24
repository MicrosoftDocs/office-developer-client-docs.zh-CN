---
title: 规则集元素 (RuleSets_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 表示一组图表有效性规则。
ms.openlocfilehash: 1231e8cdb3c8781dc47f470c0477b4585b1331c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318912"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a><span data-ttu-id="18246-103">规则集元素 (RuleSets_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="18246-103">RuleSet element (RuleSets_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="18246-104">表示一组图表有效性规则。</span><span class="sxs-lookup"><span data-stu-id="18246-104">Represents one set of diagram-validation rules.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="18246-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="18246-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="18246-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="18246-106">**Element type**</span></span> <br/> |[<span data-ttu-id="18246-107">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="18246-107">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="18246-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="18246-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="18246-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="18246-109">**Schema file**</span></span> <br/> |<span data-ttu-id="18246-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="18246-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="18246-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="18246-111">**Document parts**</span></span> <br/> |<span data-ttu-id="18246-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="18246-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="18246-113">定义</span><span class="sxs-lookup"><span data-stu-id="18246-113">Definition</span></span>

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="18246-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="18246-114">Elements and attributes</span></span>

<span data-ttu-id="18246-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="18246-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="18246-116">父元素</span><span class="sxs-lookup"><span data-stu-id="18246-116">Parent elements</span></span>

|<span data-ttu-id="18246-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="18246-117">**Element**</span></span>|<span data-ttu-id="18246-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="18246-118">**Type**</span></span>|<span data-ttu-id="18246-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="18246-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="18246-120">RuleSets</span><span class="sxs-lookup"><span data-stu-id="18246-120">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18246-121">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="18246-121">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="18246-122">为文档中的每个有效性规则集包含一个**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="18246-122">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="18246-123">子元素</span><span class="sxs-lookup"><span data-stu-id="18246-123">Child elements</span></span>

|<span data-ttu-id="18246-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="18246-124">**Element**</span></span>|<span data-ttu-id="18246-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="18246-125">**Type**</span></span>|<span data-ttu-id="18246-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="18246-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="18246-127">Rule</span><span class="sxs-lookup"><span data-stu-id="18246-127">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18246-128">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="18246-128">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="18246-129">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="18246-129">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
|[<span data-ttu-id="18246-130">RuleSetFlags</span><span class="sxs-lookup"><span data-stu-id="18246-130">RuleSetFlags</span></span>](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18246-131">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="18246-131">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="18246-132">指定规则集属性。</span><span class="sxs-lookup"><span data-stu-id="18246-132">Specifies rule-set properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="18246-133">属性</span><span class="sxs-lookup"><span data-stu-id="18246-133">Attributes</span></span>

|<span data-ttu-id="18246-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="18246-134">**Attribute**</span></span>|<span data-ttu-id="18246-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="18246-135">**Type**</span></span>|<span data-ttu-id="18246-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="18246-136">**Required**</span></span>|<span data-ttu-id="18246-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="18246-137">**Description**</span></span>|<span data-ttu-id="18246-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="18246-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18246-139">说明</span><span class="sxs-lookup"><span data-stu-id="18246-139">Description</span></span>  <br/> |<span data-ttu-id="18246-140">xsd: string</span><span class="sxs-lookup"><span data-stu-id="18246-140">xsd:string</span></span>  <br/> |<span data-ttu-id="18246-141">可选</span><span class="sxs-lookup"><span data-stu-id="18246-141">optional</span></span>  <br/> |<span data-ttu-id="18246-142">指定在验证规则集的用户界面中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="18246-142">Specifies the description that appears in the user interface for the validation rule set.</span></span> <span data-ttu-id="18246-143">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="18246-143">Default is an empty string.</span></span>  <br/> |<span data-ttu-id="18246-144">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18246-144">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="18246-145">已启用</span><span class="sxs-lookup"><span data-stu-id="18246-145">Enabled</span></span>  <br/> |<span data-ttu-id="18246-146">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="18246-146">xsd:boolean</span></span>  <br/> |<span data-ttu-id="18246-147">可选</span><span class="sxs-lookup"><span data-stu-id="18246-147">optional</span></span>  <br/> |<span data-ttu-id="18246-148">指定在为当前文档触发验证时是否检查指定的验证规则集中的规则。</span><span class="sxs-lookup"><span data-stu-id="18246-148">Specifies whether the rules in the specified validation rule set are checked when validation is triggered for the current document.</span></span> <span data-ttu-id="18246-149">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="18246-149">Default is True.</span></span>  <br/> |<span data-ttu-id="18246-150">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18246-150">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="18246-151">ID</span><span class="sxs-lookup"><span data-stu-id="18246-151">ID</span></span>  <br/> |<span data-ttu-id="18246-152">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="18246-152">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="18246-153">必需</span><span class="sxs-lookup"><span data-stu-id="18246-153">required</span></span>  <br/> |<span data-ttu-id="18246-154">指定验证规则集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="18246-154">Specifies the unique identifier of the validation rule set.</span></span>  <br/> |<span data-ttu-id="18246-155">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18246-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="18246-156">名称</span><span class="sxs-lookup"><span data-stu-id="18246-156">Name</span></span>  <br/> |<span data-ttu-id="18246-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="18246-157">xsd:string</span></span>  <br/> |<span data-ttu-id="18246-158">可选</span><span class="sxs-lookup"><span data-stu-id="18246-158">optional</span></span>  <br/> |<span data-ttu-id="18246-159">指定验证规则集的本地名称。</span><span class="sxs-lookup"><span data-stu-id="18246-159">Specifies the local name of the validation rule set.</span></span> <span data-ttu-id="18246-160">默认值为 NameU 属性值。</span><span class="sxs-lookup"><span data-stu-id="18246-160">Defaults to NameU attribute value.</span></span>  <br/> |<span data-ttu-id="18246-161">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18246-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="18246-162">NameU</span><span class="sxs-lookup"><span data-stu-id="18246-162">NameU</span></span>  <br/> |<span data-ttu-id="18246-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="18246-163">xsd:string</span></span>  <br/> |<span data-ttu-id="18246-164">必需</span><span class="sxs-lookup"><span data-stu-id="18246-164">required</span></span>  <br/> |<span data-ttu-id="18246-165">指定验证规则集的通用名称。</span><span class="sxs-lookup"><span data-stu-id="18246-165">Specifies the universal name of the validation rule set.</span></span>  <br/> |<span data-ttu-id="18246-166">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18246-166">Values of the xsd:string type.</span></span>  <br/> |
   

