---
title: IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd9a5d5f-16fe-29b4-5af0-913b14d2be16
description: 根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。 如果父验证问题目标为文档、 IssueTarget 指定的页和形状都不。
ms.openlocfilehash: 72789782a37b29daa48cd01adb0b8eda4ebf73ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780519"
---
# <a name="issuetarget-element-issuetype-complextype-visio-xml"></a><span data-ttu-id="55193-104">IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="55193-104">IssueTarget element (Issue_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="55193-105">根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。</span><span class="sxs-lookup"><span data-stu-id="55193-105">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span> <span data-ttu-id="55193-106">如果父验证问题目标为文档、 **IssueTarget**指定的页和形状都不。</span><span class="sxs-lookup"><span data-stu-id="55193-106">If the target of the parent validation issue is a document, **IssueTarget** specifes neither a page nor a shape.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="55193-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="55193-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55193-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="55193-108">**Element type**</span></span> <br/> |[<span data-ttu-id="55193-109">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="55193-109">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="55193-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="55193-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="55193-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="55193-111">**Schema file**</span></span> <br/> |<span data-ttu-id="55193-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="55193-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="55193-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="55193-113">**Document parts**</span></span> <br/> |<span data-ttu-id="55193-114">validation.xml</span><span class="sxs-lookup"><span data-stu-id="55193-114">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="55193-115">定义</span><span class="sxs-lookup"><span data-stu-id="55193-115">Definition</span></span>

```XML
< xs:element name="IssueTarget" type="IssueTarget_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="55193-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="55193-116">Elements and attributes</span></span>

<span data-ttu-id="55193-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="55193-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="55193-118">父元素</span><span class="sxs-lookup"><span data-stu-id="55193-118">Parent elements</span></span>

|<span data-ttu-id="55193-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="55193-119">**Element**</span></span>|<span data-ttu-id="55193-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="55193-120">**Type**</span></span>|<span data-ttu-id="55193-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="55193-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="55193-122">问题</span><span class="sxs-lookup"><span data-stu-id="55193-122">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="55193-123">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="55193-123">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="55193-124">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="55193-124">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="55193-125">子元素</span><span class="sxs-lookup"><span data-stu-id="55193-125">Child elements</span></span>

<span data-ttu-id="55193-126">无。</span><span class="sxs-lookup"><span data-stu-id="55193-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="55193-127">属性</span><span class="sxs-lookup"><span data-stu-id="55193-127">Attributes</span></span>

|<span data-ttu-id="55193-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="55193-128">**Attribute**</span></span>|<span data-ttu-id="55193-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="55193-129">**Type**</span></span>|<span data-ttu-id="55193-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="55193-130">**Required**</span></span>|<span data-ttu-id="55193-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="55193-131">**Description**</span></span>|<span data-ttu-id="55193-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="55193-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55193-133">PageID</span><span class="sxs-lookup"><span data-stu-id="55193-133">PageID</span></span>  <br/> |<span data-ttu-id="55193-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="55193-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="55193-135">必需</span><span class="sxs-lookup"><span data-stu-id="55193-135">required</span></span>  <br/> |<span data-ttu-id="55193-136">指定的页面的父验证问题与相关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="55193-136">Specifies the unique identifier of the page that is associated with the parent validation issue.</span></span> <span data-ttu-id="55193-137">如果目标是文档，则 PageID 值可以是 0xFFFFFFFF。</span><span class="sxs-lookup"><span data-stu-id="55193-137">If the target is the document, the PageID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="55193-138">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="55193-138">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="55193-139">ShapeID</span><span class="sxs-lookup"><span data-stu-id="55193-139">ShapeID</span></span>  <br/> |<span data-ttu-id="55193-140">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="55193-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="55193-141">必需</span><span class="sxs-lookup"><span data-stu-id="55193-141">required</span></span>  <br/> |<span data-ttu-id="55193-142">指定与父验证问题关联的形状的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="55193-142">Specifies the unique identifier of the shape that is associated with the parent validation issue.</span></span> <span data-ttu-id="55193-143">如果目标是文档或页面，ShapeID 值可以是 0xFFFFFFFF。</span><span class="sxs-lookup"><span data-stu-id="55193-143">If the target is the document or a page, the ShapeID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="55193-144">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="55193-144">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

