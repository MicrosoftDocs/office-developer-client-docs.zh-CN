---
title: Shapes 元素 (PageContents_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f9d51d7-e2b7-bc68-dede-c79fb9dbcf60
description: 包含 Shape 元素的集合。
ms.openlocfilehash: 7abece2a9fc8d88817f22c654567272becce981e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349166"
---
# <a name="shapes-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="84f7e-103">Shapes 元素 (PageContents_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="84f7e-103">Shapes element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="84f7e-104">包含 Shape 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="84f7e-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="84f7e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="84f7e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="84f7e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="84f7e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="84f7e-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="84f7e-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="84f7e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="84f7e-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="84f7e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="84f7e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="84f7e-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="84f7e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="84f7e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="84f7e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="84f7e-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="84f7e-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="84f7e-113">定义</span><span class="sxs-lookup"><span data-stu-id="84f7e-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="84f7e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="84f7e-114">Elements and attributes</span></span>

<span data-ttu-id="84f7e-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="84f7e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="84f7e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="84f7e-116">Parent elements</span></span>

|<span data-ttu-id="84f7e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="84f7e-117">**Element**</span></span>|<span data-ttu-id="84f7e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="84f7e-118">**Type**</span></span>|<span data-ttu-id="84f7e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="84f7e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="84f7e-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="84f7e-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="84f7e-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="84f7e-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="84f7e-122">指定有关 Web 绘图中主控形状中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="84f7e-122">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
|[<span data-ttu-id="84f7e-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="84f7e-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="84f7e-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="84f7e-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="84f7e-125">指定有关 Web 绘图中主控形状中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="84f7e-125">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="84f7e-126">子元素</span><span class="sxs-lookup"><span data-stu-id="84f7e-126">Child elements</span></span>

|<span data-ttu-id="84f7e-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="84f7e-127">**Element**</span></span>|<span data-ttu-id="84f7e-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="84f7e-128">**Type**</span></span>|<span data-ttu-id="84f7e-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="84f7e-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="84f7e-130">Shape</span><span class="sxs-lookup"><span data-stu-id="84f7e-130">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="84f7e-131">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="84f7e-131">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="84f7e-132">包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。</span><span class="sxs-lookup"><span data-stu-id="84f7e-132">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="84f7e-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="84f7e-133">Attributes</span></span>

<span data-ttu-id="84f7e-134">无。</span><span class="sxs-lookup"><span data-stu-id="84f7e-134">None.</span></span>
  

