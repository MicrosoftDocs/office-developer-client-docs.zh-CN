---
title: 问题元素 （Validation_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 23544055-c554-28b7-c351-370ab9b3c96c
description: 包含文档的所有问题元素。
ms.openlocfilehash: da3156e34af1536fab39d3d4949acac1efe67264
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400577"
---
# <a name="issues-element-validationtype-complextype-visio-xml"></a><span data-ttu-id="5b200-103">问题元素 （Validation_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5b200-103">Issues element (Validation_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="5b200-104">包含文档的所有问题元素。</span><span class="sxs-lookup"><span data-stu-id="5b200-104">Contains all the Issue elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5b200-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5b200-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5b200-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5b200-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5b200-107">Issues_Type</span><span class="sxs-lookup"><span data-stu-id="5b200-107">Issues_Type</span></span>](issues_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5b200-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5b200-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5b200-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5b200-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5b200-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5b200-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5b200-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5b200-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5b200-112">validation.xml</span><span class="sxs-lookup"><span data-stu-id="5b200-112">validation.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5b200-113">定义</span><span class="sxs-lookup"><span data-stu-id="5b200-113">Definition</span></span>

```XML
< xs:element name="Issues" type="Issues_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5b200-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5b200-114">Elements and attributes</span></span>

<span data-ttu-id="5b200-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5b200-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5b200-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5b200-116">Parent elements</span></span>

|<span data-ttu-id="5b200-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5b200-117">**Element**</span></span>|<span data-ttu-id="5b200-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b200-118">**Type**</span></span>|<span data-ttu-id="5b200-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b200-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5b200-120">验证</span><span class="sxs-lookup"><span data-stu-id="5b200-120">Validation</span></span>](validation-elementvisio-xml.md) <br/> |[<span data-ttu-id="5b200-121">Validation_Type</span><span class="sxs-lookup"><span data-stu-id="5b200-121">Validation_Type</span></span>](validation_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5b200-122">存储有关文档图表验证的信息。</span><span class="sxs-lookup"><span data-stu-id="5b200-122">Stores information about diagram validation for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5b200-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5b200-123">Child elements</span></span>

|<span data-ttu-id="5b200-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="5b200-124">**Element**</span></span>|<span data-ttu-id="5b200-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="5b200-125">**Type**</span></span>|<span data-ttu-id="5b200-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="5b200-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5b200-127">问题</span><span class="sxs-lookup"><span data-stu-id="5b200-127">Issue</span></span>](issue-element-issues_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5b200-128">Issue_Type</span><span class="sxs-lookup"><span data-stu-id="5b200-128">Issue_Type</span></span>](issue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5b200-129">代表文档中的一个验证问题。</span><span class="sxs-lookup"><span data-stu-id="5b200-129">Represents a single validation issue in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="5b200-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="5b200-130">Attributes</span></span>

<span data-ttu-id="5b200-131">无。</span><span class="sxs-lookup"><span data-stu-id="5b200-131">None.</span></span>
  

