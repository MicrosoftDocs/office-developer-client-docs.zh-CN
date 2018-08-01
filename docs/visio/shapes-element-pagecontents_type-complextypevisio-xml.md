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
# <a name="shapes-element-pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="39336-103">形状元素 （PageContents_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="39336-103">Shapes element (PageContents_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="39336-104">包含形状元素的集合。</span><span class="sxs-lookup"><span data-stu-id="39336-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="39336-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="39336-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="39336-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="39336-106">**Element type**</span></span> <br/> |[<span data-ttu-id="39336-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="39336-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="39336-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="39336-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="39336-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="39336-109">**Schema file**</span></span> <br/> |<span data-ttu-id="39336-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="39336-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="39336-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="39336-111">**Document parts**</span></span> <br/> |<span data-ttu-id="39336-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="39336-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="39336-113">定义</span><span class="sxs-lookup"><span data-stu-id="39336-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="39336-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="39336-114">Elements and attributes</span></span>

<span data-ttu-id="39336-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="39336-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="39336-116">父元素</span><span class="sxs-lookup"><span data-stu-id="39336-116">Parent elements</span></span>

|<span data-ttu-id="39336-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="39336-117">**Element**</span></span>|<span data-ttu-id="39336-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="39336-118">**Type**</span></span>|<span data-ttu-id="39336-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="39336-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="39336-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="39336-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="39336-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="39336-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="39336-122">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="39336-122">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
|[<span data-ttu-id="39336-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="39336-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="39336-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="39336-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="39336-125">指定 Web 绘图中的主控形状中的形状的有关信息。</span><span class="sxs-lookup"><span data-stu-id="39336-125">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="39336-126">子元素</span><span class="sxs-lookup"><span data-stu-id="39336-126">Child elements</span></span>

|<span data-ttu-id="39336-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="39336-127">**Element**</span></span>|<span data-ttu-id="39336-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="39336-128">**Type**</span></span>|<span data-ttu-id="39336-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="39336-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="39336-130">Shape</span><span class="sxs-lookup"><span data-stu-id="39336-130">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="39336-131">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="39336-131">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="39336-132">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="39336-132">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="39336-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="39336-133">Attributes</span></span>

<span data-ttu-id="39336-134">无。</span><span class="sxs-lookup"><span data-stu-id="39336-134">None.</span></span>
  

