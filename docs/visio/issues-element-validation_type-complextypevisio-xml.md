---
title: 问题元素 （Validation_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 23544055-c554-28b7-c351-370ab9b3c96c
description: 包含文档的所有问题元素。
ms.openlocfilehash: 9205bf014c81aa699b8bc4a2a7412c5ce59c5fd0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780491"
---
# <a name="issues-element-validationtype-complextype-visio-xml"></a><span data-ttu-id="19380-103">问题元素 （Validation_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="19380-103">Issues element (Validation_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="19380-104">包含文档的所有问题元素。</span><span class="sxs-lookup"><span data-stu-id="19380-104">Contains all the Issue elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="19380-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="19380-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="19380-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="19380-106">**Element type**</span></span> <br/> |[<span data-ttu-id="19380-107">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="19380-107">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="19380-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="19380-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="19380-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="19380-109">**Schema file**</span></span> <br/> |<span data-ttu-id="19380-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="19380-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="19380-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="19380-111">**Document parts**</span></span> <br/> |<span data-ttu-id="19380-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="19380-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="19380-113">定义</span><span class="sxs-lookup"><span data-stu-id="19380-113">Definition</span></span>

```XML
< xs:element name="Issues" type="Issues_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="19380-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="19380-114">Elements and attributes</span></span>

<span data-ttu-id="19380-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="19380-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="19380-116">父元素</span><span class="sxs-lookup"><span data-stu-id="19380-116">Parent elements</span></span>

|<span data-ttu-id="19380-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="19380-117">**Element**</span></span>|<span data-ttu-id="19380-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="19380-118">**Type**</span></span>|<span data-ttu-id="19380-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="19380-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="19380-120">验证</span><span class="sxs-lookup"><span data-stu-id="19380-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="19380-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="19380-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="19380-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="19380-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="19380-123">子元素</span><span class="sxs-lookup"><span data-stu-id="19380-123">Child elements</span></span>

|<span data-ttu-id="19380-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="19380-124">**Element**</span></span>|<span data-ttu-id="19380-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="19380-125">**Type**</span></span>|<span data-ttu-id="19380-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="19380-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="19380-127">问题</span><span class="sxs-lookup"><span data-stu-id="19380-127">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="19380-128">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="19380-128">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="19380-129">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="19380-129">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="19380-130">属性</span><span class="sxs-lookup"><span data-stu-id="19380-130">Attributes</span></span>

<span data-ttu-id="19380-131">无。</span><span class="sxs-lookup"><span data-stu-id="19380-131">None.</span></span>
  

