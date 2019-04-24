---
title: IssueTarget 元素 (Issue_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd9a5d5f-16fe-29b4-5af0-913b14d2be16
description: 根据父验证问题的目标, 指定页面或页面和形状, 与父验证问题相关联。 如果父验证问题的目标是文档, 则 IssueTarget 指定不是一个页面, 也不是一个形状。
ms.openlocfilehash: 74005bfb6035e32b7b34fdd5a8a5737813a562a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332520"
---
# <a name="issuetarget-element-issuetype-complextype-visio-xml"></a><span data-ttu-id="c80d0-104">IssueTarget 元素 (Issue_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="c80d0-104">IssueTarget element (Issue_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="c80d0-105">根据父验证问题的目标, 指定页面或页面和形状, 与父验证问题相关联。</span><span class="sxs-lookup"><span data-stu-id="c80d0-105">Depending on the target of the parent validation issue, specifies either the page, or both the page and the shape, associated with the parent validation issue.</span></span> <span data-ttu-id="c80d0-106">如果父验证问题的目标是文档, 则**IssueTarget**指定不是一个页面, 也不是一个形状。</span><span class="sxs-lookup"><span data-stu-id="c80d0-106">If the target of the parent validation issue is a document, **IssueTarget** specifes neither a page nor a shape.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="c80d0-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="c80d0-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c80d0-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c80d0-108">**Element type**</span></span> <br/> |[<span data-ttu-id="c80d0-109">IssueTarget_Type</span><span class="sxs-lookup"><span data-stu-id="c80d0-109">IssueTarget_Type</span></span>](issuetarget_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c80d0-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c80d0-110">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c80d0-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c80d0-111">**Schema file**</span></span> <br/> |<span data-ttu-id="c80d0-112">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="c80d0-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c80d0-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c80d0-113">**Document parts**</span></span> <br/> |<span data-ttu-id="c80d0-114">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="c80d0-114">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c80d0-115">定义</span><span class="sxs-lookup"><span data-stu-id="c80d0-115">Definition</span></span>

```XML
< xs:element name="IssueTarget" type="IssueTarget_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c80d0-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c80d0-116">Elements and attributes</span></span>

<span data-ttu-id="c80d0-117">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c80d0-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c80d0-118">父元素</span><span class="sxs-lookup"><span data-stu-id="c80d0-118">Parent elements</span></span>

|<span data-ttu-id="c80d0-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="c80d0-119">**Element**</span></span>|<span data-ttu-id="c80d0-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="c80d0-120">**Type**</span></span>|<span data-ttu-id="c80d0-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="c80d0-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c80d0-122">问题</span><span class="sxs-lookup"><span data-stu-id="c80d0-122">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c80d0-123">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="c80d0-123">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c80d0-124">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="c80d0-124">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c80d0-125">子元素</span><span class="sxs-lookup"><span data-stu-id="c80d0-125">Child elements</span></span>

<span data-ttu-id="c80d0-126">无。</span><span class="sxs-lookup"><span data-stu-id="c80d0-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="c80d0-127">属性</span><span class="sxs-lookup"><span data-stu-id="c80d0-127">Attributes</span></span>

|<span data-ttu-id="c80d0-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="c80d0-128">**Attribute**</span></span>|<span data-ttu-id="c80d0-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="c80d0-129">**Type**</span></span>|<span data-ttu-id="c80d0-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="c80d0-130">**Required**</span></span>|<span data-ttu-id="c80d0-131">**描述**</span><span class="sxs-lookup"><span data-stu-id="c80d0-131">**Description**</span></span>|<span data-ttu-id="c80d0-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c80d0-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c80d0-133">PageID</span><span class="sxs-lookup"><span data-stu-id="c80d0-133">PageID</span></span>  <br/> |<span data-ttu-id="c80d0-134">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c80d0-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c80d0-135">必需</span><span class="sxs-lookup"><span data-stu-id="c80d0-135">required</span></span>  <br/> |<span data-ttu-id="c80d0-136">指定与父验证问题关联的页面的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c80d0-136">Specifies the unique identifier of the page that is associated with the parent validation issue.</span></span> <span data-ttu-id="c80d0-137">如果目标是文档, 则 PageID 值可以为0xffffffff。</span><span class="sxs-lookup"><span data-stu-id="c80d0-137">If the target is the document, the PageID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="c80d0-138">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c80d0-138">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="c80d0-139">ShapeID</span><span class="sxs-lookup"><span data-stu-id="c80d0-139">ShapeID</span></span>  <br/> |<span data-ttu-id="c80d0-140">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="c80d0-140">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="c80d0-141">必需</span><span class="sxs-lookup"><span data-stu-id="c80d0-141">required</span></span>  <br/> |<span data-ttu-id="c80d0-142">指定与父验证问题相关联的形状的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c80d0-142">Specifies the unique identifier of the shape that is associated with the parent validation issue.</span></span> <span data-ttu-id="c80d0-143">如果目标是文档或页面, 则 ShapeID 值可以为0xffffffff。</span><span class="sxs-lookup"><span data-stu-id="c80d0-143">If the target is the document or a page, the ShapeID value can be 0xFFFFFFFF.</span></span>  <br/> |<span data-ttu-id="c80d0-144">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c80d0-144">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

