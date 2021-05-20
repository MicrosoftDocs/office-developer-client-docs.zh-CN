---
title: 'ValidationProperties 元素 (Validation_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a51a60c9-479b-7d7b-860f-bb46fc8b4d63
description: 封装与文档验证相关的属性。
ms.openlocfilehash: 35e6f3f13eecef826fdef0d664bba35fceb0e069
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538520"
---
# <a name="validationproperties-element-validation_type-complextype-visio-xml"></a><span data-ttu-id="14e02-103">ValidationProperties 元素 (Validation_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="14e02-103">ValidationProperties element (Validation_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="14e02-104">封装与文档验证相关的属性。</span><span class="sxs-lookup"><span data-stu-id="14e02-104">Encapsulates the properties that are related to the document's validation.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="14e02-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="14e02-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="14e02-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="14e02-106">**Element type**</span></span> <br/> |[<span data-ttu-id="14e02-107">ValidationProperties_Type</span><span class="sxs-lookup"><span data-stu-id="14e02-107">ValidationProperties_Type</span></span>](validationproperties_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="14e02-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="14e02-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="14e02-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="14e02-109">**Schema file**</span></span> <br/> |<span data-ttu-id="14e02-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="14e02-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="14e02-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="14e02-111">**Document parts**</span></span> <br/> |<span data-ttu-id="14e02-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="14e02-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="14e02-113">定义</span><span class="sxs-lookup"><span data-stu-id="14e02-113">Definition</span></span>

```XML
< xs:element name="ValidationProperties" type="ValidationProperties_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="14e02-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="14e02-114">Elements and attributes</span></span>

<span data-ttu-id="14e02-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="14e02-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="14e02-116">父元素</span><span class="sxs-lookup"><span data-stu-id="14e02-116">Parent elements</span></span>

|<span data-ttu-id="14e02-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="14e02-117">**Element**</span></span>|<span data-ttu-id="14e02-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="14e02-118">**Type**</span></span>|<span data-ttu-id="14e02-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="14e02-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="14e02-120">Validation</span><span class="sxs-lookup"><span data-stu-id="14e02-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="14e02-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="14e02-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="14e02-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="14e02-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="14e02-123">子元素</span><span class="sxs-lookup"><span data-stu-id="14e02-123">Child elements</span></span>

<span data-ttu-id="14e02-124">无。</span><span class="sxs-lookup"><span data-stu-id="14e02-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="14e02-125">属性</span><span class="sxs-lookup"><span data-stu-id="14e02-125">Attributes</span></span>

|<span data-ttu-id="14e02-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="14e02-126">**Attribute**</span></span>|<span data-ttu-id="14e02-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="14e02-127">**Type**</span></span>|<span data-ttu-id="14e02-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="14e02-128">**Required**</span></span>|<span data-ttu-id="14e02-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="14e02-129">**Description**</span></span>|<span data-ttu-id="14e02-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="14e02-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14e02-131">LastValidated</span><span class="sxs-lookup"><span data-stu-id="14e02-131">LastValidated</span></span>  <br/> |<span data-ttu-id="14e02-132">xsd：dateTime</span><span class="sxs-lookup"><span data-stu-id="14e02-132">xsd:dateTime</span></span>  <br/> |<span data-ttu-id="14e02-133">必需</span><span class="sxs-lookup"><span data-stu-id="14e02-133">required</span></span>  <br/> |<span data-ttu-id="14e02-134">上次验证文档的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="14e02-134">The date and time that the document was last validated.</span></span>  <br/> |<span data-ttu-id="14e02-135">xsd：dateTime 类型的值。</span><span class="sxs-lookup"><span data-stu-id="14e02-135">Values of the xsd:dateTime type.</span></span>  <br/> |
|<span data-ttu-id="14e02-136">ShowIgnored</span><span class="sxs-lookup"><span data-stu-id="14e02-136">ShowIgnored</span></span>  <br/> |<span data-ttu-id="14e02-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="14e02-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="14e02-138">必需</span><span class="sxs-lookup"><span data-stu-id="14e02-138">required</span></span>  <br/> |<span data-ttu-id="14e02-139">指定是否在"问题"窗口中显示被忽略的验证问题。</span><span class="sxs-lookup"><span data-stu-id="14e02-139">Specifies whether to show ignored validation issues in the Issues window.</span></span>  <br/> |<span data-ttu-id="14e02-140">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="14e02-140">Values of the xsd:boolean type.</span></span>  <br/> |
   

