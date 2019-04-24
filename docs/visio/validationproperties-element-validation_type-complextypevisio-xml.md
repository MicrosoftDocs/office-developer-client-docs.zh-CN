---
title: ValidationProperties 元素 (Validation_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a51a60c9-479b-7d7b-860f-bb46fc8b4d63
description: 封装与文档的验证相关的属性。
ms.openlocfilehash: 9eccb85bd7463411d81c867eda3216d6c9a207f2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355956"
---
# <a name="validationproperties-element-validationtype-complextype-visio-xml"></a><span data-ttu-id="9a8d9-103">ValidationProperties 元素 (Validation_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9a8d9-103">ValidationProperties element (Validation_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9a8d9-104">封装与文档的验证相关的属性。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-104">Encapsulates the properties that are related to the document's validation.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9a8d9-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9a8d9-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9a8d9-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9a8d9-107">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="9a8d9-107">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9a8d9-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9a8d9-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9a8d9-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="9a8d9-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9a8d9-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9a8d9-112">验证 .xml</span><span class="sxs-lookup"><span data-stu-id="9a8d9-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9a8d9-113">定义</span><span class="sxs-lookup"><span data-stu-id="9a8d9-113">Definition</span></span>

```XML
< xs:element name="ValidationProperties" type="ValidationProperties_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9a8d9-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9a8d9-114">Elements and attributes</span></span>

<span data-ttu-id="9a8d9-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9a8d9-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9a8d9-116">Parent elements</span></span>

|<span data-ttu-id="9a8d9-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-117">**Element**</span></span>|<span data-ttu-id="9a8d9-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-118">**Type**</span></span>|<span data-ttu-id="9a8d9-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9a8d9-120">Validation</span><span class="sxs-lookup"><span data-stu-id="9a8d9-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="9a8d9-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="9a8d9-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9a8d9-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9a8d9-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9a8d9-123">Child elements</span></span>

<span data-ttu-id="9a8d9-124">无。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9a8d9-125">属性</span><span class="sxs-lookup"><span data-stu-id="9a8d9-125">Attributes</span></span>

|<span data-ttu-id="9a8d9-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-126">**Attribute**</span></span>|<span data-ttu-id="9a8d9-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-127">**Type**</span></span>|<span data-ttu-id="9a8d9-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-128">**Required**</span></span>|<span data-ttu-id="9a8d9-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-129">**Description**</span></span>|<span data-ttu-id="9a8d9-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a8d9-131">LastValidated</span><span class="sxs-lookup"><span data-stu-id="9a8d9-131">LastValidated</span></span>  <br/> |<span data-ttu-id="9a8d9-132">xsd: dateTime</span><span class="sxs-lookup"><span data-stu-id="9a8d9-132">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="9a8d9-133">必需</span><span class="sxs-lookup"><span data-stu-id="9a8d9-133">required</span></span>  <br/> |<span data-ttu-id="9a8d9-134">上次验证文档的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-134">The date and time that the document was last validated.</span></span>  <br/> |<span data-ttu-id="9a8d9-135">xsd: dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-135">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="9a8d9-136">ShowIgnored</span><span class="sxs-lookup"><span data-stu-id="9a8d9-136">ShowIgnored</span></span>  <br/> |<span data-ttu-id="9a8d9-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="9a8d9-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="9a8d9-138">必需</span><span class="sxs-lookup"><span data-stu-id="9a8d9-138">required</span></span>  <br/> |<span data-ttu-id="9a8d9-139">指定是否在 "问题" 窗口中显示忽略的验证问题。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-139">Specifies whether to show ignored validation issues in the Issues window.</span></span>  <br/> |<span data-ttu-id="9a8d9-140">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9a8d9-140">Values of the xsd:boolean type.</span></span>  <br/> |
   

