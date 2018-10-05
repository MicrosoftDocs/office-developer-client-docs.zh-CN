---
title: Rule 元素 （RuleSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fcd22f3a-c8e8-1133-160c-fe26e612a15d
description: 代表图表有效性规则集中的一个有效性规则。
ms.openlocfilehash: 92d52456164b89ff2aad31fa8d8f02f818c8bd1c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395908"
---
# <a name="rule-element-rulesettype-complextype-visio-xml"></a><span data-ttu-id="beca1-103">Rule 元素 （RuleSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="beca1-103">Rule element (RuleSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="beca1-104">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="beca1-104">Represents a single validation rule in a diagram validation rule set.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="beca1-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="beca1-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="beca1-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="beca1-106">**Element type**</span></span> <br/> |[<span data-ttu-id="beca1-107">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="beca1-107">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="beca1-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="beca1-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="beca1-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="beca1-109">**Schema file**</span></span> <br/> |<span data-ttu-id="beca1-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="beca1-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="beca1-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="beca1-111">**Document parts**</span></span> <br/> |<span data-ttu-id="beca1-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="beca1-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="beca1-113">定义</span><span class="sxs-lookup"><span data-stu-id="beca1-113">Definition</span></span>

```XML
< xs:element name="Rule" type="Rule_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="beca1-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="beca1-114">Elements and attributes</span></span>

<span data-ttu-id="beca1-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="beca1-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="beca1-116">父元素</span><span class="sxs-lookup"><span data-stu-id="beca1-116">Parent elements</span></span>

|<span data-ttu-id="beca1-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="beca1-117">**Element**</span></span>|<span data-ttu-id="beca1-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="beca1-118">**Type**</span></span>|<span data-ttu-id="beca1-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="beca1-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="beca1-120">规则集</span><span class="sxs-lookup"><span data-stu-id="beca1-120">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="beca1-121">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="beca1-121">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="beca1-122">代表一个图表验证规则集。</span><span class="sxs-lookup"><span data-stu-id="beca1-122">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="beca1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="beca1-123">Child elements</span></span>

|<span data-ttu-id="beca1-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="beca1-124">**Element**</span></span>|<span data-ttu-id="beca1-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="beca1-125">**Type**</span></span>|<span data-ttu-id="beca1-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="beca1-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="beca1-127">RuleFilter</span><span class="sxs-lookup"><span data-stu-id="beca1-127">RuleFilter</span></span>](rulefilter-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="beca1-128">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="beca1-128">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="beca1-129">指定确定是否应将有效性规则应用于目标对象的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="beca1-129">Specifies the logical expression that determines whether the validation rule should be applied to a target object.</span></span>  <br/> |
|[<span data-ttu-id="beca1-130">RuleTest</span><span class="sxs-lookup"><span data-stu-id="beca1-130">RuleTest</span></span>](ruletest-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="beca1-131">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="beca1-131">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="beca1-132">指定确定目标对象是否满足有效性规则的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="beca1-132">Specifies the logical expression that determines whether the target object satisfies the validation rule.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="beca1-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="beca1-133">Attributes</span></span>

|<span data-ttu-id="beca1-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="beca1-134">**Attribute**</span></span>|<span data-ttu-id="beca1-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="beca1-135">**Type**</span></span>|<span data-ttu-id="beca1-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="beca1-136">**Required**</span></span>|<span data-ttu-id="beca1-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="beca1-137">**Description**</span></span>|<span data-ttu-id="beca1-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="beca1-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="beca1-139">Category</span><span class="sxs-lookup"><span data-stu-id="beca1-139">Category</span></span>  <br/> |<span data-ttu-id="beca1-140">xsd: string</span><span class="sxs-lookup"><span data-stu-id="beca1-140">xsd:string</span></span>  <br/> |<span data-ttu-id="beca1-141">可选</span><span class="sxs-lookup"><span data-stu-id="beca1-141">optional</span></span>  <br/> |<span data-ttu-id="beca1-142">指定**类别**列中的问题窗口中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="beca1-142">Specifies the text displayed in the **Category** column of the Issues window.</span></span> <span data-ttu-id="beca1-143">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="beca1-143">Default is an empty string.</span></span>  <br/> |<span data-ttu-id="beca1-144">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-144">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="beca1-145">说明</span><span class="sxs-lookup"><span data-stu-id="beca1-145">Description</span></span>  <br/> |<span data-ttu-id="beca1-146">xsd: string</span><span class="sxs-lookup"><span data-stu-id="beca1-146">xsd:string</span></span>  <br/> |<span data-ttu-id="beca1-147">可选</span><span class="sxs-lookup"><span data-stu-id="beca1-147">optional</span></span>  <br/> |<span data-ttu-id="beca1-148">指定在用户界面中显示的有效性规则的说明。</span><span class="sxs-lookup"><span data-stu-id="beca1-148">Specifies the description of the validation rule that appears in the user interface.</span></span> <span data-ttu-id="beca1-149">默认值为"Unknown"。</span><span class="sxs-lookup"><span data-stu-id="beca1-149">Default is "Unknown".</span></span>  <br/> |<span data-ttu-id="beca1-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="beca1-151">ID</span><span class="sxs-lookup"><span data-stu-id="beca1-151">ID</span></span>  <br/> |<span data-ttu-id="beca1-152">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="beca1-152">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="beca1-153">必需</span><span class="sxs-lookup"><span data-stu-id="beca1-153">required</span></span>  <br/> |<span data-ttu-id="beca1-154">指定的有效性规则的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="beca1-154">Specifies the unique identifier for the validation rule.</span></span>  <br/> |<span data-ttu-id="beca1-155">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="beca1-156">忽略</span><span class="sxs-lookup"><span data-stu-id="beca1-156">Ignored</span></span>  <br/> |<span data-ttu-id="beca1-157">化</span><span class="sxs-lookup"><span data-stu-id="beca1-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="beca1-158">可选</span><span class="sxs-lookup"><span data-stu-id="beca1-158">optional</span></span>  <br/> |<span data-ttu-id="beca1-159">指定是否当前忽略有效性规则。</span><span class="sxs-lookup"><span data-stu-id="beca1-159">Specifies whether the validation rule is currently ignored.</span></span> <span data-ttu-id="beca1-160">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="beca1-160">Default is False.</span></span>  <br/> |<span data-ttu-id="beca1-161">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-161">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="beca1-162">NameU</span><span class="sxs-lookup"><span data-stu-id="beca1-162">NameU</span></span>  <br/> |<span data-ttu-id="beca1-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="beca1-163">xsd:string</span></span>  <br/> |<span data-ttu-id="beca1-164">必需</span><span class="sxs-lookup"><span data-stu-id="beca1-164">required</span></span>  <br/> |<span data-ttu-id="beca1-165">指定的有效性规则的通用名称。</span><span class="sxs-lookup"><span data-stu-id="beca1-165">Specifies the universal name of the validation rule.</span></span>  <br/> |<span data-ttu-id="beca1-166">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-166">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="beca1-167">RuleTarget</span><span class="sxs-lookup"><span data-stu-id="beca1-167">RuleTarget</span></span>  <br/> |<span data-ttu-id="beca1-168">xsd:int</span><span class="sxs-lookup"><span data-stu-id="beca1-168">xsd:int</span></span>  <br/> |<span data-ttu-id="beca1-169">可选</span><span class="sxs-lookup"><span data-stu-id="beca1-169">optional</span></span>  <br/> |<span data-ttu-id="beca1-170">指定的有效性规则应用于的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="beca1-170">Specifies the type of object to which the validation rule applies.</span></span>  <br/> |<span data-ttu-id="beca1-171">Xsd:int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="beca1-171">Values of the xsd:int type.</span></span>  <br/> |
   

