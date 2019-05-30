---
title: Rule 元素 (RuleSet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fcd22f3a-c8e8-1133-160c-fe26e612a15d
description: 代表图表有效性规则集中的一个有效性规则。
ms.openlocfilehash: 0d848ce3309d7dfc5a89b201be30ce060ec6f88f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541706"
---
# <a name="rule-element-rulesettype-complextype-visio-xml"></a><span data-ttu-id="48fda-103">Rule 元素 (RuleSet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="48fda-103">Rule element (RuleSet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="48fda-104">代表图表有效性规则集中的一个有效性规则。</span><span class="sxs-lookup"><span data-stu-id="48fda-104">Represents a single validation rule in a diagram validation rule set.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="48fda-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="48fda-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="48fda-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="48fda-106">**Element type**</span></span> <br/> |[<span data-ttu-id="48fda-107">Rule_Type</span><span class="sxs-lookup"><span data-stu-id="48fda-107">Rule_Type</span></span>](rule_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="48fda-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="48fda-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="48fda-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="48fda-109">**Schema file**</span></span> <br/> |<span data-ttu-id="48fda-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="48fda-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="48fda-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="48fda-111">**Document parts**</span></span> <br/> |<span data-ttu-id="48fda-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="48fda-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="48fda-113">定义</span><span class="sxs-lookup"><span data-stu-id="48fda-113">Definition</span></span>

```XML
< xs:element name="Rule" type="Rule_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="48fda-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="48fda-114">Elements and attributes</span></span>

<span data-ttu-id="48fda-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="48fda-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="48fda-116">父元素</span><span class="sxs-lookup"><span data-stu-id="48fda-116">Parent elements</span></span>

|<span data-ttu-id="48fda-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="48fda-117">**Element**</span></span>|<span data-ttu-id="48fda-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="48fda-118">**Type**</span></span>|<span data-ttu-id="48fda-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="48fda-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48fda-120">RuleSet</span><span class="sxs-lookup"><span data-stu-id="48fda-120">RuleSet</span></span>](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="48fda-121">RuleSet_Type</span><span class="sxs-lookup"><span data-stu-id="48fda-121">RuleSet_Type</span></span>](ruleset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48fda-122">表示一组图表有效性规则。</span><span class="sxs-lookup"><span data-stu-id="48fda-122">Represents one set of diagram-validation rules.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="48fda-123">子元素</span><span class="sxs-lookup"><span data-stu-id="48fda-123">Child elements</span></span>

|<span data-ttu-id="48fda-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="48fda-124">**Element**</span></span>|<span data-ttu-id="48fda-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="48fda-125">**Type**</span></span>|<span data-ttu-id="48fda-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="48fda-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="48fda-127">RuleFilter</span><span class="sxs-lookup"><span data-stu-id="48fda-127">RuleFilter</span></span>](rulefilter-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="48fda-128">RuleFilter_Type</span><span class="sxs-lookup"><span data-stu-id="48fda-128">RuleFilter_Type</span></span>](rulefilter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48fda-129">指定用于确定是否应将验证规则应用于目标对象的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="48fda-129">Specifies the logical expression that determines whether the validation rule should be applied to a target object.</span></span>  <br/> |
|[<span data-ttu-id="48fda-130">RuleTest</span><span class="sxs-lookup"><span data-stu-id="48fda-130">RuleTest</span></span>](ruletest-element-rule_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="48fda-131">RuleTest_Type</span><span class="sxs-lookup"><span data-stu-id="48fda-131">RuleTest_Type</span></span>](ruletest_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="48fda-132">指定确定目标对象是否满足有效性规则的逻辑表达式。</span><span class="sxs-lookup"><span data-stu-id="48fda-132">Specifies the logical expression that determines whether the target object satisfies the validation rule.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="48fda-133">属性</span><span class="sxs-lookup"><span data-stu-id="48fda-133">Attributes</span></span>

|<span data-ttu-id="48fda-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="48fda-134">**Attribute**</span></span>|<span data-ttu-id="48fda-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="48fda-135">**Type**</span></span>|<span data-ttu-id="48fda-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="48fda-136">**Required**</span></span>|<span data-ttu-id="48fda-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="48fda-137">**Description**</span></span>|<span data-ttu-id="48fda-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="48fda-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48fda-139">类别</span><span class="sxs-lookup"><span data-stu-id="48fda-139">Category</span></span>  <br/> |<span data-ttu-id="48fda-140">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48fda-140">xsd:string</span></span>  <br/> |<span data-ttu-id="48fda-141">可选</span><span class="sxs-lookup"><span data-stu-id="48fda-141">optional</span></span>  <br/> |<span data-ttu-id="48fda-142">指定在 "问题" 窗口的 "**类别**" 列中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="48fda-142">Specifies the text displayed in the **Category** column of the Issues window.</span></span> <span data-ttu-id="48fda-143">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="48fda-143">Default is an empty string.</span></span>  <br/> |<span data-ttu-id="48fda-144">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-144">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="48fda-145">说明</span><span class="sxs-lookup"><span data-stu-id="48fda-145">Description</span></span>  <br/> |<span data-ttu-id="48fda-146">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48fda-146">xsd:string</span></span>  <br/> |<span data-ttu-id="48fda-147">可选</span><span class="sxs-lookup"><span data-stu-id="48fda-147">optional</span></span>  <br/> |<span data-ttu-id="48fda-148">指定显示在用户界面中的验证规则的说明。</span><span class="sxs-lookup"><span data-stu-id="48fda-148">Specifies the description of the validation rule that appears in the user interface.</span></span> <span data-ttu-id="48fda-149">默认值为 "未知"。</span><span class="sxs-lookup"><span data-stu-id="48fda-149">Default is "Unknown".</span></span>  <br/> |<span data-ttu-id="48fda-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="48fda-151">ID</span><span class="sxs-lookup"><span data-stu-id="48fda-151">ID</span></span>  <br/> |<span data-ttu-id="48fda-152">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="48fda-152">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="48fda-153">必需</span><span class="sxs-lookup"><span data-stu-id="48fda-153">required</span></span>  <br/> |<span data-ttu-id="48fda-154">指定验证规则的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="48fda-154">Specifies the unique identifier for the validation rule.</span></span>  <br/> |<span data-ttu-id="48fda-155">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-155">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="48fda-156">Ignored</span><span class="sxs-lookup"><span data-stu-id="48fda-156">Ignored</span></span>  <br/> |<span data-ttu-id="48fda-157">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="48fda-157">xsd:boolean</span></span>  <br/> |<span data-ttu-id="48fda-158">可选</span><span class="sxs-lookup"><span data-stu-id="48fda-158">optional</span></span>  <br/> |<span data-ttu-id="48fda-159">指定当前是否忽略有效性规则。</span><span class="sxs-lookup"><span data-stu-id="48fda-159">Specifies whether the validation rule is currently ignored.</span></span> <span data-ttu-id="48fda-160">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="48fda-160">Default is False.</span></span>  <br/> |<span data-ttu-id="48fda-161">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-161">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="48fda-162">NameU</span><span class="sxs-lookup"><span data-stu-id="48fda-162">NameU</span></span>  <br/> |<span data-ttu-id="48fda-163">xsd: string</span><span class="sxs-lookup"><span data-stu-id="48fda-163">xsd:string</span></span>  <br/> |<span data-ttu-id="48fda-164">必需</span><span class="sxs-lookup"><span data-stu-id="48fda-164">required</span></span>  <br/> |<span data-ttu-id="48fda-165">指定验证规则的通用名称。</span><span class="sxs-lookup"><span data-stu-id="48fda-165">Specifies the universal name of the validation rule.</span></span>  <br/> |<span data-ttu-id="48fda-166">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-166">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="48fda-167">RuleTarget</span><span class="sxs-lookup"><span data-stu-id="48fda-167">RuleTarget</span></span>  <br/> |<span data-ttu-id="48fda-168">xsd: int</span><span class="sxs-lookup"><span data-stu-id="48fda-168">xsd:int</span></span>  <br/> |<span data-ttu-id="48fda-169">可选</span><span class="sxs-lookup"><span data-stu-id="48fda-169">optional</span></span>  <br/> |<span data-ttu-id="48fda-170">指定要应用验证规则的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="48fda-170">Specifies the type of object to which the validation rule applies.</span></span>  <br/> |<span data-ttu-id="48fda-171">Xsd: int 类型的值。</span><span class="sxs-lookup"><span data-stu-id="48fda-171">Values of the xsd:int type.</span></span>  <br/> |
   

