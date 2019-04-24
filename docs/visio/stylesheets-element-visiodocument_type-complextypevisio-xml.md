---
title: 样式表元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: da26de4b-3e5b-326b-de46-e8c542b74f02
description: 包含文档的样式表元素的集合。
ms.openlocfilehash: 4aae3bcbecec34d961f2d14fd6d3865e7cd332f6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329783"
---
# <a name="stylesheets-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="c7103-103">样式表元素 (VisioDocument_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="c7103-103">StyleSheets element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="c7103-104">包含文档的样式表元素的集合。</span><span class="sxs-lookup"><span data-stu-id="c7103-104">Contains a collection of StyleSheet elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c7103-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c7103-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c7103-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c7103-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c7103-107">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="c7103-107">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c7103-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c7103-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c7103-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c7103-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c7103-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="c7103-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c7103-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c7103-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c7103-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="c7103-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c7103-113">定义</span><span class="sxs-lookup"><span data-stu-id="c7103-113">Definition</span></span>

```XML
< xs:element name="StyleSheets" type="StyleSheets_Type" minOccurs="0" maxOccurs="1" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c7103-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c7103-114">Elements and attributes</span></span>

<span data-ttu-id="c7103-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c7103-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c7103-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c7103-116">Parent elements</span></span>

|<span data-ttu-id="c7103-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c7103-117">**Element**</span></span>|<span data-ttu-id="c7103-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c7103-118">**Type**</span></span>|<span data-ttu-id="c7103-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c7103-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c7103-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="c7103-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="c7103-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="c7103-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c7103-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="c7103-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c7103-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c7103-123">Child elements</span></span>

|<span data-ttu-id="c7103-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="c7103-124">**Element**</span></span>|<span data-ttu-id="c7103-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="c7103-125">**Type**</span></span>|<span data-ttu-id="c7103-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c7103-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c7103-127">单</span><span class="sxs-lookup"><span data-stu-id="c7103-127">StyleSheet</span></span>](stylesheet-element-stylesheets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c7103-128">StyleSheet_Type</span><span class="sxs-lookup"><span data-stu-id="c7103-128">StyleSheet_Type</span></span>](stylesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c7103-129">表示在文档中定义的样式。</span><span class="sxs-lookup"><span data-stu-id="c7103-129">Represents a style defined in a document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c7103-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="c7103-130">Attributes</span></span>

<span data-ttu-id="c7103-131">无。</span><span class="sxs-lookup"><span data-stu-id="c7103-131">None.</span></span>
  

