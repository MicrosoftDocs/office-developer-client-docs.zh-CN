---
title: 'Issue 元素 (Issues_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5c4d07bf-4edc-e241-7827-017f96c11957
description: 表示文档中的单个验证问题。
ms.openlocfilehash: 73c83fe47ebf9921686ea7b35c5f94a06b803623
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541125"
---
# <a name="issue-element-issues_type-complextype-visio-xml"></a><span data-ttu-id="40329-103">Issue 元素 (Issues_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="40329-103">Issue element (Issues_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="40329-104">表示文档中的单个验证问题。</span><span class="sxs-lookup"><span data-stu-id="40329-104">Represents a single validation issue in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="40329-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="40329-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="40329-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="40329-106">**Element type**</span></span> <br/> |[<span data-ttu-id="40329-107">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="40329-107">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="40329-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="40329-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="40329-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="40329-109">**Schema file**</span></span> <br/> |<span data-ttu-id="40329-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="40329-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="40329-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="40329-111">**Document parts**</span></span> <br/> |<span data-ttu-id="40329-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="40329-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="40329-113">定义</span><span class="sxs-lookup"><span data-stu-id="40329-113">Definition</span></span>

```XML
< xs:element name="Issue" type="Issue_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="40329-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="40329-114">Elements and attributes</span></span>

<span data-ttu-id="40329-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="40329-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="40329-116">父元素</span><span class="sxs-lookup"><span data-stu-id="40329-116">Parent elements</span></span>

|<span data-ttu-id="40329-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="40329-117">**Element**</span></span>|<span data-ttu-id="40329-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="40329-118">**Type**</span></span>|<span data-ttu-id="40329-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="40329-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="40329-120">Issues</span><span class="sxs-lookup"><span data-stu-id="40329-120">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="40329-121">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="40329-121">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="40329-122">包含文档 **的所有 Issue** 元素。</span><span class="sxs-lookup"><span data-stu-id="40329-122">Contains all the **Issue** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="40329-123">子元素</span><span class="sxs-lookup"><span data-stu-id="40329-123">Child elements</span></span>

|<span data-ttu-id="40329-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="40329-124">**Element**</span></span>|<span data-ttu-id="40329-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="40329-125">**Type**</span></span>|<span data-ttu-id="40329-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="40329-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="40329-127">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="40329-127">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="40329-128">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="40329-128">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="40329-129">根据父验证问题的目标，指定与父验证问题关联的页面或页面和形状。</span><span class="sxs-lookup"><span data-stu-id="40329-129">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span>  <br/> |
|[<span data-ttu-id="40329-130">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="40329-130">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="40329-131">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="40329-131">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="40329-132">指定有关父验证问题所相关的验证规则的信息。</span><span class="sxs-lookup"><span data-stu-id="40329-132">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="40329-133">属性</span><span class="sxs-lookup"><span data-stu-id="40329-133">Attributes</span></span>

|<span data-ttu-id="40329-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="40329-134">**Attribute**</span></span>|<span data-ttu-id="40329-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="40329-135">**Type**</span></span>|<span data-ttu-id="40329-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="40329-136">**Required**</span></span>|<span data-ttu-id="40329-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="40329-137">**Description**</span></span>|<span data-ttu-id="40329-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="40329-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40329-139">ID</span><span class="sxs-lookup"><span data-stu-id="40329-139">ID</span></span>  <br/> |<span data-ttu-id="40329-140">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="40329-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="40329-141">必需</span><span class="sxs-lookup"><span data-stu-id="40329-141">required</span></span>  <br/> |<span data-ttu-id="40329-142">指定验证问题的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="40329-142">Specifies the unique identifier of the validation issue.</span></span>  <br/> |<span data-ttu-id="40329-143">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40329-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="40329-144">忽略</span><span class="sxs-lookup"><span data-stu-id="40329-144">Ignored</span></span>  <br/> |<span data-ttu-id="40329-145">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="40329-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="40329-146">可选</span><span class="sxs-lookup"><span data-stu-id="40329-146">optional</span></span>  <br/> |<span data-ttu-id="40329-147">指定有关父验证问题所相关的验证规则的信息。</span><span class="sxs-lookup"><span data-stu-id="40329-147">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |<span data-ttu-id="40329-148">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40329-148">Values of the xsd:boolean type.</span></span>  <br/> |
   

