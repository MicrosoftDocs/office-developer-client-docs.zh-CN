---
title: 形状元素 （PageContents_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f9d51d7-e2b7-bc68-dede-c79fb9dbcf60
description: 包含形状元素的集合。
ms.openlocfilehash: eae86d230c19f1db8c7ed43cca8682460c3f7af1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781291"
---
# <a name="shapes-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="9a830-103">形状元素 （PageContents_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9a830-103">Shapes element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9a830-104">包含形状元素的集合。</span><span class="sxs-lookup"><span data-stu-id="9a830-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9a830-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9a830-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9a830-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9a830-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9a830-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="9a830-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9a830-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9a830-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9a830-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9a830-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9a830-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="9a830-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9a830-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9a830-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9a830-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="9a830-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9a830-113">定义</span><span class="sxs-lookup"><span data-stu-id="9a830-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9a830-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9a830-114">Elements and attributes</span></span>

<span data-ttu-id="9a830-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9a830-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9a830-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9a830-116">Parent elements</span></span>

|<span data-ttu-id="9a830-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9a830-117">**Element**</span></span>|<span data-ttu-id="9a830-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9a830-118">**Type**</span></span>|<span data-ttu-id="9a830-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a830-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9a830-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="9a830-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="9a830-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="9a830-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9a830-122">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="9a830-122">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
|[<span data-ttu-id="9a830-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="9a830-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="9a830-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="9a830-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9a830-125">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="9a830-125">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9a830-126">子元素</span><span class="sxs-lookup"><span data-stu-id="9a830-126">Child elements</span></span>

|<span data-ttu-id="9a830-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="9a830-127">**Element**</span></span>|<span data-ttu-id="9a830-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="9a830-128">**Type**</span></span>|<span data-ttu-id="9a830-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="9a830-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9a830-130">Shape</span><span class="sxs-lookup"><span data-stu-id="9a830-130">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9a830-131">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="9a830-131">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9a830-132">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="9a830-132">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="9a830-133">属性</span><span class="sxs-lookup"><span data-stu-id="9a830-133">Attributes</span></span>

<span data-ttu-id="9a830-134">无。</span><span class="sxs-lookup"><span data-stu-id="9a830-134">None.</span></span>
  

