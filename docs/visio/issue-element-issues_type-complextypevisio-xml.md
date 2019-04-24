---
title: Issue 元素 (Issues_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5c4d07bf-4edc-e241-7827-017f96c11957
description: 代表文档中的一个验证问题。
ms.openlocfilehash: 4ebe7d2d8b2b4627fb9c9e12113ef23ce19db52e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317904"
---
# <a name="issue-element-issuestype-complextype-visio-xml"></a><span data-ttu-id="291f6-103">Issue 元素 (Issues_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="291f6-103">Issue element (Issues_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="291f6-104">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="291f6-104">Represents a single validation issue in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="291f6-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="291f6-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="291f6-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="291f6-106">**Element type**</span></span> <br/> |[<span data-ttu-id="291f6-107">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="291f6-107">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="291f6-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="291f6-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="291f6-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="291f6-109">**Schema file**</span></span> <br/> |<span data-ttu-id="291f6-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="291f6-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="291f6-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="291f6-111">**Document parts**</span></span> <br/> |<span data-ttu-id="291f6-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="291f6-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="291f6-113">定义</span><span class="sxs-lookup"><span data-stu-id="291f6-113">Definition</span></span>

```XML
< xs:element name="Issue" type="Issue_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="291f6-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="291f6-114">Elements and attributes</span></span>

<span data-ttu-id="291f6-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="291f6-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="291f6-116">父元素</span><span class="sxs-lookup"><span data-stu-id="291f6-116">Parent elements</span></span>

|<span data-ttu-id="291f6-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="291f6-117">**Element**</span></span>|<span data-ttu-id="291f6-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="291f6-118">**Type**</span></span>|<span data-ttu-id="291f6-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="291f6-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="291f6-120">Issues</span><span class="sxs-lookup"><span data-stu-id="291f6-120">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="291f6-121">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="291f6-121">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="291f6-122">包含文档的所有**问题**元素。</span><span class="sxs-lookup"><span data-stu-id="291f6-122">Contains all the **Issue** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="291f6-123">子元素</span><span class="sxs-lookup"><span data-stu-id="291f6-123">Child elements</span></span>

|<span data-ttu-id="291f6-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="291f6-124">**Element**</span></span>|<span data-ttu-id="291f6-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="291f6-125">**Type**</span></span>|<span data-ttu-id="291f6-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="291f6-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="291f6-127">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="291f6-127">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="291f6-128">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="291f6-128">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="291f6-129">根据父验证问题的目标, 指定页面或页面和形状, 与父验证问题相关联。</span><span class="sxs-lookup"><span data-stu-id="291f6-129">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span>  <br/> |
|[<span data-ttu-id="291f6-130">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="291f6-130">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="291f6-131">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="291f6-131">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="291f6-132">指定与父验证问题相关的验证规则的相关信息。</span><span class="sxs-lookup"><span data-stu-id="291f6-132">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="291f6-133">属性</span><span class="sxs-lookup"><span data-stu-id="291f6-133">Attributes</span></span>

|<span data-ttu-id="291f6-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="291f6-134">**Attribute**</span></span>|<span data-ttu-id="291f6-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="291f6-135">**Type**</span></span>|<span data-ttu-id="291f6-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="291f6-136">**Required**</span></span>|<span data-ttu-id="291f6-137">**描述**</span><span class="sxs-lookup"><span data-stu-id="291f6-137">**Description**</span></span>|<span data-ttu-id="291f6-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="291f6-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="291f6-139">ID</span><span class="sxs-lookup"><span data-stu-id="291f6-139">ID</span></span>  <br/> |<span data-ttu-id="291f6-140">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="291f6-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="291f6-141">必需</span><span class="sxs-lookup"><span data-stu-id="291f6-141">required</span></span>  <br/> |<span data-ttu-id="291f6-142">指定验证问题的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="291f6-142">Specifies the unique identifier of the validation issue.</span></span>  <br/> |<span data-ttu-id="291f6-143">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="291f6-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="291f6-144">Ignored</span><span class="sxs-lookup"><span data-stu-id="291f6-144">Ignored</span></span>  <br/> |<span data-ttu-id="291f6-145">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="291f6-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="291f6-146">可选</span><span class="sxs-lookup"><span data-stu-id="291f6-146">optional</span></span>  <br/> |<span data-ttu-id="291f6-147">指定与父验证问题相关的验证规则的相关信息。</span><span class="sxs-lookup"><span data-stu-id="291f6-147">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |<span data-ttu-id="291f6-148">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="291f6-148">Values of the xsd:boolean type.</span></span>  <br/> |
   

