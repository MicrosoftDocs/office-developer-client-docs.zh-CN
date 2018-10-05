---
title: 问题元素 （Issues_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5c4d07bf-4edc-e241-7827-017f96c11957
description: 代表文档中的一个验证问题。
ms.openlocfilehash: 4ebe7d2d8b2b4627fb9c9e12113ef23ce19db52e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389839"
---
# <a name="issue-element-issuestype-complextype-visio-xml"></a><span data-ttu-id="08636-103">问题元素 （Issues_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="08636-103">Issue element (Issues_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="08636-104">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="08636-104">Represents a single validation issue in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="08636-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="08636-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08636-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="08636-106">**Element type**</span></span> <br/> |[<span data-ttu-id="08636-107">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="08636-107">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="08636-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="08636-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="08636-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="08636-109">**Schema file**</span></span> <br/> |<span data-ttu-id="08636-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="08636-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="08636-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="08636-111">**Document parts**</span></span> <br/> |<span data-ttu-id="08636-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="08636-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="08636-113">定义</span><span class="sxs-lookup"><span data-stu-id="08636-113">Definition</span></span>

```XML
< xs:element name="Issue" type="Issue_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="08636-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="08636-114">Elements and attributes</span></span>

<span data-ttu-id="08636-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="08636-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="08636-116">父元素</span><span class="sxs-lookup"><span data-stu-id="08636-116">Parent elements</span></span>

|<span data-ttu-id="08636-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="08636-117">**Element**</span></span>|<span data-ttu-id="08636-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="08636-118">**Type**</span></span>|<span data-ttu-id="08636-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="08636-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="08636-120">问题</span><span class="sxs-lookup"><span data-stu-id="08636-120">Issues</span></span>](issues-element-validation_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="08636-121">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="08636-121">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="08636-122">包含文档的所有**问题**元素。</span><span class="sxs-lookup"><span data-stu-id="08636-122">Contains all the **Issue** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="08636-123">子元素</span><span class="sxs-lookup"><span data-stu-id="08636-123">Child elements</span></span>

|<span data-ttu-id="08636-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="08636-124">**Element**</span></span>|<span data-ttu-id="08636-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="08636-125">**Type**</span></span>|<span data-ttu-id="08636-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="08636-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="08636-127">IssueTarget</span><span class="sxs-lookup"><span data-stu-id="08636-127">IssueTarget</span></span>](issuetarget-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="08636-128">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="08636-128">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="08636-129">根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。</span><span class="sxs-lookup"><span data-stu-id="08636-129">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span>  <br/> |
|[<span data-ttu-id="08636-130">RuleInfo</span><span class="sxs-lookup"><span data-stu-id="08636-130">RuleInfo</span></span>](ruleinfo-element-issue_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="08636-131">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="08636-131">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="08636-132">指定父验证问题与有效性规则有关的信息。</span><span class="sxs-lookup"><span data-stu-id="08636-132">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="08636-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="08636-133">Attributes</span></span>

|<span data-ttu-id="08636-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="08636-134">**Attribute**</span></span>|<span data-ttu-id="08636-135">**类型**</span><span class="sxs-lookup"><span data-stu-id="08636-135">**Type**</span></span>|<span data-ttu-id="08636-136">**必需**</span><span class="sxs-lookup"><span data-stu-id="08636-136">**Required**</span></span>|<span data-ttu-id="08636-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="08636-137">**Description**</span></span>|<span data-ttu-id="08636-138">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="08636-138">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08636-139">ID</span><span class="sxs-lookup"><span data-stu-id="08636-139">ID</span></span>  <br/> |<span data-ttu-id="08636-140">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="08636-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="08636-141">必需</span><span class="sxs-lookup"><span data-stu-id="08636-141">required</span></span>  <br/> |<span data-ttu-id="08636-142">指定验证问题的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="08636-142">Specifies the unique identifier of the validation issue.</span></span>  <br/> |<span data-ttu-id="08636-143">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="08636-143">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="08636-144">忽略</span><span class="sxs-lookup"><span data-stu-id="08636-144">Ignored</span></span>  <br/> |<span data-ttu-id="08636-145">化</span><span class="sxs-lookup"><span data-stu-id="08636-145">xsd:boolean</span></span>  <br/> |<span data-ttu-id="08636-146">可选</span><span class="sxs-lookup"><span data-stu-id="08636-146">optional</span></span>  <br/> |<span data-ttu-id="08636-147">指定父验证问题与有效性规则有关的信息。</span><span class="sxs-lookup"><span data-stu-id="08636-147">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>  <br/> |<span data-ttu-id="08636-148">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="08636-148">Values of the xsd:boolean type.</span></span>  <br/> |
   

