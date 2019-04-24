---
title: RuleInfo 元素 (Issue_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec47b43-adbe-3344-fbac-29554f244c99
description: 指定与父验证问题相关的验证规则的相关信息。
ms.openlocfilehash: f0cf726f0c5d6943ef72669aa92f361a7367459c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356985"
---
# <a name="ruleinfo-element-issuetype-complextype-visio-xml"></a><span data-ttu-id="31f1f-103">RuleInfo 元素 (Issue_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="31f1f-103">RuleInfo element (Issue_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="31f1f-104">指定与父验证问题相关的验证规则的相关信息。</span><span class="sxs-lookup"><span data-stu-id="31f1f-104">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="31f1f-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="31f1f-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="31f1f-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="31f1f-106">**Element type**</span></span> <br/> |[<span data-ttu-id="31f1f-107">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="31f1f-107">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="31f1f-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="31f1f-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="31f1f-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="31f1f-109">**Schema file**</span></span> <br/> |<span data-ttu-id="31f1f-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="31f1f-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="31f1f-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="31f1f-111">**Document parts**</span></span> <br/> |<span data-ttu-id="31f1f-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="31f1f-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="31f1f-113">定义</span><span class="sxs-lookup"><span data-stu-id="31f1f-113">Definition</span></span>

```XML
< xs:element name="RuleInfo" type="RuleInfo_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="31f1f-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="31f1f-114">Elements and attributes</span></span>

<span data-ttu-id="31f1f-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="31f1f-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="31f1f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="31f1f-116">Parent elements</span></span>

|<span data-ttu-id="31f1f-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="31f1f-117">**Element**</span></span>|<span data-ttu-id="31f1f-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="31f1f-118">**Type**</span></span>|<span data-ttu-id="31f1f-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="31f1f-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="31f1f-120">问题</span><span class="sxs-lookup"><span data-stu-id="31f1f-120">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="31f1f-121">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="31f1f-121">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="31f1f-122">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="31f1f-122">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="31f1f-123">子元素</span><span class="sxs-lookup"><span data-stu-id="31f1f-123">Child elements</span></span>

<span data-ttu-id="31f1f-124">无。</span><span class="sxs-lookup"><span data-stu-id="31f1f-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="31f1f-125">属性</span><span class="sxs-lookup"><span data-stu-id="31f1f-125">Attributes</span></span>

|<span data-ttu-id="31f1f-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="31f1f-126">**Attribute**</span></span>|<span data-ttu-id="31f1f-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="31f1f-127">**Type**</span></span>|<span data-ttu-id="31f1f-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="31f1f-128">**Required**</span></span>|<span data-ttu-id="31f1f-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="31f1f-129">**Description**</span></span>|<span data-ttu-id="31f1f-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="31f1f-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="31f1f-131">RuleID</span><span class="sxs-lookup"><span data-stu-id="31f1f-131">RuleID</span></span>  <br/> |<span data-ttu-id="31f1f-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="31f1f-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="31f1f-133">必需</span><span class="sxs-lookup"><span data-stu-id="31f1f-133">required</span></span>  <br/> |<span data-ttu-id="31f1f-134">指定父问题所适用的验证规则的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="31f1f-134">Specifies the unique identifier of the validation rule that the parent issue pertains to.</span></span>  <br/> |<span data-ttu-id="31f1f-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="31f1f-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="31f1f-136">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="31f1f-136">RuleSetID</span></span>  <br/> |<span data-ttu-id="31f1f-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="31f1f-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="31f1f-138">必需</span><span class="sxs-lookup"><span data-stu-id="31f1f-138">required</span></span>  <br/> |<span data-ttu-id="31f1f-139">指定父问题所适用的验证规则集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="31f1f-139">Specifies the unique identifier of the validation rule set that the parent issue pertains to.</span></span>  <br/> |<span data-ttu-id="31f1f-140">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="31f1f-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

