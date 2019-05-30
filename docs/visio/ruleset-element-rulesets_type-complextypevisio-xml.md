---
title: 规则集元素 (RuleSets_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 表示一组图表有效性规则。
ms.openlocfilehash: c6fc8df6d9c84f44496d69207dfb9cfb878659e3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541636"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a><span data-ttu-id="07ef7-103">规则集元素 (RuleSets_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="07ef7-103">RuleSet element (RuleSets_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="07ef7-104">表示一组图表有效性规则。</span><span class="sxs-lookup"><span data-stu-id="07ef7-104">Represents one set of diagram-validation rules.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="07ef7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="07ef7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="07ef7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="07ef7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="07ef7-107">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="07ef7-107">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="07ef7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="07ef7-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="07ef7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="07ef7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="07ef7-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="07ef7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="07ef7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="07ef7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="07ef7-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="07ef7-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="07ef7-113">定义</span><span class="sxs-lookup"><span data-stu-id="07ef7-113">Definition</span></span>

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="07ef7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="07ef7-114">Elements and attributes</span></span>

<span data-ttu-id="07ef7-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="07ef7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="07ef7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="07ef7-116">Parent elements</span></span>

|<span data-ttu-id="07ef7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="07ef7-117">**Element**</span></span>|<span data-ttu-id="07ef7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="07ef7-118">**Type**</span></span>|<span data-ttu-id="07ef7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="07ef7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07ef7-120">RuleSets</span><span class="sxs-lookup"><span data-stu-id="07ef7-120">RuleSets</span></span>](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="07ef7-121">RuleSets_Type</span><span class="sxs-lookup"><span data-stu-id="07ef7-121">RuleSets_Type</span></span>](rulesets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07ef7-122">为文档中的每个有效性规则集包含一个**规则集**元素。</span><span class="sxs-lookup"><span data-stu-id="07ef7-122">Includes a **RuleSet** element for each validation rule set in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="07ef7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="07ef7-123">Child elements</span></span>

|<span data-ttu-id="07ef7-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="07ef7-124">**Element**</span></span>|<span data-ttu-id="07ef7-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="07ef7-125">**Type**</span></span>|<span data-ttu-id="07ef7-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="07ef7-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="07ef7-127">Rule</span><span class="sxs-lookup"><span data-stu-id="07ef7-127">Rule</span></span>](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="07ef7-128">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="07ef7-128">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07ef7-129">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="07ef7-129">Represents a single validation rule in a diagram validation rule set.</span></span>  <br/> |
|[<span data-ttu-id="07ef7-130">RuleSetFlags</span><span class="sxs-lookup"><span data-stu-id="07ef7-130">RuleSetFlags</span></span>](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="07ef7-131">RuleSetFlags_Type</span><span class="sxs-lookup"><span data-stu-id="07ef7-131">RuleSetFlags_Type</span></span>](rulesetflags_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="07ef7-132">指定规则集属性。</span><span class="sxs-lookup"><span data-stu-id="07ef7-132">Specifies rule-set properties.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="07ef7-133">属性</span><span class="sxs-lookup"><span data-stu-id="07ef7-133">Attributes</span></span>

|<span data-ttu-id="07ef7-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="07ef7-134">**Attribute**</span></span>|<span data-ttu-id="07ef7-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="07ef7-135">**Type**</span></span>|<span data-ttu-id="07ef7-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="07ef7-136">**Required**</span></span>|<span data-ttu-id="07ef7-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="07ef7-137">**Description**</span></span>|<span data-ttu-id="07ef7-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="07ef7-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07ef7-139">说明</span><span class="sxs-lookup"><span data-stu-id="07ef7-139">Description</span></span>  <br/> |<span data-ttu-id="07ef7-140">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07ef7-140">xsd:string</span></span>  <br/> |<span data-ttu-id="07ef7-141">可选</span><span class="sxs-lookup"><span data-stu-id="07ef7-141">optional</span></span>  <br/> |<span data-ttu-id="07ef7-142">指定在验证规则集的用户界面中显示的说明。</span><span class="sxs-lookup"><span data-stu-id="07ef7-142">Specifies the description that appears in the user interface for the validation rule set.</span></span> <span data-ttu-id="07ef7-143">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="07ef7-143">Default is an empty string.</span></span>  <br/> |<span data-ttu-id="07ef7-144">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-144">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="07ef7-145">已启用</span><span class="sxs-lookup"><span data-stu-id="07ef7-145">Enabled</span></span>  <br/> |<span data-ttu-id="07ef7-146">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="07ef7-146">xsd:boolean</span></span>  <br/> |<span data-ttu-id="07ef7-147">可选</span><span class="sxs-lookup"><span data-stu-id="07ef7-147">optional</span></span>  <br/> |<span data-ttu-id="07ef7-148">指定在为当前文档触发验证时是否检查指定的验证规则集中的规则。</span><span class="sxs-lookup"><span data-stu-id="07ef7-148">Specifies whether the rules in the specified validation rule set are checked when validation is triggered for the current document.</span></span> <span data-ttu-id="07ef7-149">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="07ef7-149">Default is True.</span></span>  <br/> |<span data-ttu-id="07ef7-150">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-150">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="07ef7-151">ID</span><span class="sxs-lookup"><span data-stu-id="07ef7-151">ID</span></span>  <br/> |<span data-ttu-id="07ef7-152">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="07ef7-152">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="07ef7-153">必需</span><span class="sxs-lookup"><span data-stu-id="07ef7-153">required</span></span>  <br/> |<span data-ttu-id="07ef7-154">指定验证规则集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="07ef7-154">Specifies the unique identifier of the validation rule set.</span></span>  <br/> |<span data-ttu-id="07ef7-155">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="07ef7-156">名称</span><span class="sxs-lookup"><span data-stu-id="07ef7-156">Name</span></span>  <br/> |<span data-ttu-id="07ef7-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07ef7-157">xsd:string</span></span>  <br/> |<span data-ttu-id="07ef7-158">可选</span><span class="sxs-lookup"><span data-stu-id="07ef7-158">optional</span></span>  <br/> |<span data-ttu-id="07ef7-159">指定验证规则集的本地名称。</span><span class="sxs-lookup"><span data-stu-id="07ef7-159">Specifies the local name of the validation rule set.</span></span> <span data-ttu-id="07ef7-160">默认值为 NameU 属性值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-160">Defaults to NameU attribute value.</span></span>  <br/> |<span data-ttu-id="07ef7-161">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-161">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="07ef7-162">NameU</span><span class="sxs-lookup"><span data-stu-id="07ef7-162">NameU</span></span>  <br/> |<span data-ttu-id="07ef7-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07ef7-163">xsd:string</span></span>  <br/> |<span data-ttu-id="07ef7-164">必需</span><span class="sxs-lookup"><span data-stu-id="07ef7-164">required</span></span>  <br/> |<span data-ttu-id="07ef7-165">指定验证规则集的通用名称。</span><span class="sxs-lookup"><span data-stu-id="07ef7-165">Specifies the universal name of the validation rule set.</span></span>  <br/> |<span data-ttu-id="07ef7-166">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07ef7-166">Values of the xsd:string type.</span></span>  <br/> |
   

