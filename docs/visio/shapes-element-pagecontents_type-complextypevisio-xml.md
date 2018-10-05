---
title: 形状元素 （PageContents_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f9d51d7-e2b7-bc68-dede-c79fb9dbcf60
description: 包含形状元素的集合。
ms.openlocfilehash: 7abece2a9fc8d88817f22c654567272becce981e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397567"
---
# <a name="shapes-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="36600-103">形状元素 （PageContents_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="36600-103">Shapes element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="36600-104">包含形状元素的集合。</span><span class="sxs-lookup"><span data-stu-id="36600-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="36600-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="36600-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="36600-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="36600-106">**Element type**</span></span> <br/> |[<span data-ttu-id="36600-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="36600-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="36600-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="36600-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="36600-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="36600-109">**Schema file**</span></span> <br/> |<span data-ttu-id="36600-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="36600-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="36600-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="36600-111">**Document parts**</span></span> <br/> |<span data-ttu-id="36600-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="36600-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="36600-113">定义</span><span class="sxs-lookup"><span data-stu-id="36600-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="36600-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="36600-114">Elements and attributes</span></span>

<span data-ttu-id="36600-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="36600-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="36600-116">父元素</span><span class="sxs-lookup"><span data-stu-id="36600-116">Parent elements</span></span>

|<span data-ttu-id="36600-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="36600-117">**Element**</span></span>|<span data-ttu-id="36600-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="36600-118">**Type**</span></span>|<span data-ttu-id="36600-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="36600-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="36600-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="36600-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="36600-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="36600-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="36600-122">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="36600-122">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
|[<span data-ttu-id="36600-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="36600-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="36600-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="36600-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="36600-125">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="36600-125">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="36600-126">子元素</span><span class="sxs-lookup"><span data-stu-id="36600-126">Child elements</span></span>

|<span data-ttu-id="36600-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="36600-127">**Element**</span></span>|<span data-ttu-id="36600-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="36600-128">**Type**</span></span>|<span data-ttu-id="36600-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="36600-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="36600-130">Shape</span><span class="sxs-lookup"><span data-stu-id="36600-130">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="36600-131">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="36600-131">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="36600-132">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="36600-132">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="36600-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="36600-133">Attributes</span></span>

<span data-ttu-id="36600-134">无。</span><span class="sxs-lookup"><span data-stu-id="36600-134">None.</span></span>
  

