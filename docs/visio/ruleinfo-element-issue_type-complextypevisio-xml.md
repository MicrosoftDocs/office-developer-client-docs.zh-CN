---
title: RuleInfo 元素 （Issue_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec47b43-adbe-3344-fbac-29554f244c99
description: 指定父验证问题与有效性规则有关的信息。
ms.openlocfilehash: f0cf726f0c5d6943ef72669aa92f361a7367459c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394746"
---
# <a name="ruleinfo-element-issuetype-complextype-visio-xml"></a><span data-ttu-id="d7b4e-103">RuleInfo 元素 （Issue_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d7b4e-103">RuleInfo element (Issue_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d7b4e-104">指定父验证问题与有效性规则有关的信息。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-104">Specifies information about the validation rule that the parent validation issue pertains to.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d7b4e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d7b4e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d7b4e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d7b4e-107">RuleInfo_Type</span><span class="sxs-lookup"><span data-stu-id="d7b4e-107">RuleInfo_Type</span></span>](ruleinfo_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d7b4e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d7b4e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d7b4e-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d7b4e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d7b4e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d7b4e-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="d7b4e-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d7b4e-113">定义</span><span class="sxs-lookup"><span data-stu-id="d7b4e-113">Definition</span></span>

```XML
< xs:element name="RuleInfo" type="RuleInfo_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d7b4e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d7b4e-114">Elements and attributes</span></span>

<span data-ttu-id="d7b4e-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d7b4e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d7b4e-116">Parent elements</span></span>

|<span data-ttu-id="d7b4e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-117">**Element**</span></span>|<span data-ttu-id="d7b4e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-118">**Type**</span></span>|<span data-ttu-id="d7b4e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d7b4e-120">问题</span><span class="sxs-lookup"><span data-stu-id="d7b4e-120">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d7b4e-121">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="d7b4e-121">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d7b4e-122">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-122">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d7b4e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d7b4e-123">Child elements</span></span>

<span data-ttu-id="d7b4e-124">无。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d7b4e-125">属性</span><span class="sxs-lookup"><span data-stu-id="d7b4e-125">Attributes</span></span>

|<span data-ttu-id="d7b4e-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-126">**Attribute**</span></span>|<span data-ttu-id="d7b4e-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-127">**Type**</span></span>|<span data-ttu-id="d7b4e-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-128">**Required**</span></span>|<span data-ttu-id="d7b4e-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-129">**Description**</span></span>|<span data-ttu-id="d7b4e-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d7b4e-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7b4e-131">规则 Id</span><span class="sxs-lookup"><span data-stu-id="d7b4e-131">RuleID</span></span>  <br/> |<span data-ttu-id="d7b4e-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7b4e-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7b4e-133">必需</span><span class="sxs-lookup"><span data-stu-id="d7b4e-133">required</span></span>  <br/> |<span data-ttu-id="d7b4e-134">指定父问题与有效性规则的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-134">Specifies the unique identifier of the validation rule that the parent issue pertains to.</span></span>  <br/> |<span data-ttu-id="d7b4e-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="d7b4e-136">RuleSetID</span><span class="sxs-lookup"><span data-stu-id="d7b4e-136">RuleSetID</span></span>  <br/> |<span data-ttu-id="d7b4e-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d7b4e-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d7b4e-138">必需</span><span class="sxs-lookup"><span data-stu-id="d7b4e-138">required</span></span>  <br/> |<span data-ttu-id="d7b4e-139">指定父问题与有效性规则集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-139">Specifies the unique identifier of the validation rule set that the parent issue pertains to.</span></span>  <br/> |<span data-ttu-id="d7b4e-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d7b4e-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

