---
title: 形状元素 （ShapeSheet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 85aa7df3-d9bd-acb3-61b3-2bd5fa256435
description: 包含形状元素的集合。
ms.openlocfilehash: d2e725a28873cac8dded49587a98400df1d9bf7f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781296"
---
# <a name="shapes-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="10ae8-103">形状元素 （ShapeSheet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="10ae8-103">Shapes element (ShapeSheet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="10ae8-104">包含形状元素的集合。</span><span class="sxs-lookup"><span data-stu-id="10ae8-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="10ae8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="10ae8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="10ae8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="10ae8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="10ae8-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="10ae8-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="10ae8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="10ae8-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="10ae8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="10ae8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="10ae8-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="10ae8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="10ae8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="10ae8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="10ae8-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="10ae8-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="10ae8-113">定义</span><span class="sxs-lookup"><span data-stu-id="10ae8-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="10ae8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="10ae8-114">Elements and attributes</span></span>

<span data-ttu-id="10ae8-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="10ae8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="10ae8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="10ae8-116">Parent elements</span></span>

|<span data-ttu-id="10ae8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="10ae8-117">**Element**</span></span>|<span data-ttu-id="10ae8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="10ae8-118">**Type**</span></span>|<span data-ttu-id="10ae8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="10ae8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="10ae8-120">Shape</span><span class="sxs-lookup"><span data-stu-id="10ae8-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="10ae8-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="10ae8-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="10ae8-122">指定与形状关联的属性集合。</span><span class="sxs-lookup"><span data-stu-id="10ae8-122">Specifies a collection of properties associated with a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="10ae8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="10ae8-123">Child elements</span></span>

|<span data-ttu-id="10ae8-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="10ae8-124">**Element**</span></span>|<span data-ttu-id="10ae8-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="10ae8-125">**Type**</span></span>|<span data-ttu-id="10ae8-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="10ae8-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="10ae8-127">Shape</span><span class="sxs-lookup"><span data-stu-id="10ae8-127">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="10ae8-128">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="10ae8-128">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="10ae8-129">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="10ae8-129">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="10ae8-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="10ae8-130">Attributes</span></span>

<span data-ttu-id="10ae8-131">无。</span><span class="sxs-lookup"><span data-stu-id="10ae8-131">None.</span></span>
  

