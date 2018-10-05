---
title: IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd9a5d5f-16fe-29b4-5af0-913b14d2be16
description: 根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。 如果父验证问题目标为文档、 IssueTarget 指定的页和形状都不。
ms.openlocfilehash: 74005bfb6035e32b7b34fdd5a8a5737813a562a0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385359"
---
# <a name="issuetarget-element-issuetype-complextype-visio-xml"></a><span data-ttu-id="65f6d-104">IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="65f6d-104">IssueTarget element (Issue_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="65f6d-105">根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。</span><span class="sxs-lookup"><span data-stu-id="65f6d-105">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span> <span data-ttu-id="65f6d-106">如果父验证问题目标为文档、 **IssueTarget**指定的页和形状都不。</span><span class="sxs-lookup"><span data-stu-id="65f6d-106">If the target of the parent validation issue is a document, **IssueTarget** specifes neither a page nor a shape.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="65f6d-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="65f6d-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="65f6d-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="65f6d-108">**Element type**</span></span> <br/> |[<span data-ttu-id="65f6d-109">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="65f6d-109">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="65f6d-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="65f6d-110">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="65f6d-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="65f6d-111">**Schema file**</span></span> <br/> |<span data-ttu-id="65f6d-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="65f6d-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="65f6d-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="65f6d-113">**Document parts**</span></span> <br/> |<span data-ttu-id="65f6d-114">validation.xml</span><span class="sxs-lookup"><span data-stu-id="65f6d-114">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="65f6d-115">定义</span><span class="sxs-lookup"><span data-stu-id="65f6d-115">Definition</span></span>

```XML
< xs:element name="IssueTarget" type="IssueTarget_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="65f6d-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="65f6d-116">Elements and attributes</span></span>

<span data-ttu-id="65f6d-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="65f6d-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="65f6d-118">父元素</span><span class="sxs-lookup"><span data-stu-id="65f6d-118">Parent elements</span></span>

|<span data-ttu-id="65f6d-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="65f6d-119">**Element**</span></span>|<span data-ttu-id="65f6d-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="65f6d-120">**Type**</span></span>|<span data-ttu-id="65f6d-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="65f6d-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="65f6d-122">问题</span><span class="sxs-lookup"><span data-stu-id="65f6d-122">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="65f6d-123">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="65f6d-123">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="65f6d-124">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="65f6d-124">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="65f6d-125">子元素</span><span class="sxs-lookup"><span data-stu-id="65f6d-125">Child elements</span></span>

<span data-ttu-id="65f6d-126">无。</span><span class="sxs-lookup"><span data-stu-id="65f6d-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="65f6d-127">属性</span><span class="sxs-lookup"><span data-stu-id="65f6d-127">Attributes</span></span>

|<span data-ttu-id="65f6d-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="65f6d-128">**Attribute**</span></span>|<span data-ttu-id="65f6d-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="65f6d-129">**Type**</span></span>|<span data-ttu-id="65f6d-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="65f6d-130">**Required**</span></span>|<span data-ttu-id="65f6d-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="65f6d-131">**Description**</span></span>|<span data-ttu-id="65f6d-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="65f6d-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65f6d-133">PageID</span><span class="sxs-lookup"><span data-stu-id="65f6d-133">PageID</span></span>  <br/> |<span data-ttu-id="65f6d-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="65f6d-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="65f6d-135">必需</span><span class="sxs-lookup"><span data-stu-id="65f6d-135">required</span></span>  <br/> |<span data-ttu-id="65f6d-136">指定的页面的父验证问题与相关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65f6d-136">Specifies the unique identifier of the page that is associated with the parent validation issue.</span></span> <span data-ttu-id="65f6d-137">如果目标是文档，则 PageID 值可以是 0xFFFFFFFF。</span><span class="sxs-lookup"><span data-stu-id="65f6d-137">If the target is the document, the PageID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="65f6d-138">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="65f6d-138">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="65f6d-139">ShapeID</span><span class="sxs-lookup"><span data-stu-id="65f6d-139">ShapeID</span></span>  <br/> |<span data-ttu-id="65f6d-140">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="65f6d-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="65f6d-141">必需</span><span class="sxs-lookup"><span data-stu-id="65f6d-141">required</span></span>  <br/> |<span data-ttu-id="65f6d-142">指定与父验证问题关联的形状的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="65f6d-142">Specifies the unique identifier of the shape that is associated with the parent validation issue.</span></span> <span data-ttu-id="65f6d-143">如果目标是文档或页面，ShapeID 值可以是 0xFFFFFFFF。</span><span class="sxs-lookup"><span data-stu-id="65f6d-143">If the target is the document or a page, the ShapeID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="65f6d-144">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="65f6d-144">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

