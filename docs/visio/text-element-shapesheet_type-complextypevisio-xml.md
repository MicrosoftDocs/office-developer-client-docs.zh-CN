---
title: Text 元素 （ShapeSheet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46211968-9ad8-07da-f725-3ad136b7a8a1
description: 包含形状的文本。
ms.openlocfilehash: 636f349b0a93719cd157db563b238147af5584cf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781482"
---
# <a name="text-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="d1acd-103">Text 元素 （ShapeSheet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d1acd-103">Text element (ShapeSheet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d1acd-104">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="d1acd-104">Contains the text of a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d1acd-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d1acd-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d1acd-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d1acd-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d1acd-107">Text_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-107">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d1acd-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d1acd-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d1acd-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d1acd-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d1acd-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="d1acd-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d1acd-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d1acd-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d1acd-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="d1acd-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d1acd-113">定义</span><span class="sxs-lookup"><span data-stu-id="d1acd-113">Definition</span></span>

```XML
< xs:element name="Text" type="Text_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d1acd-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d1acd-114">Elements and attributes</span></span>

<span data-ttu-id="d1acd-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="d1acd-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d1acd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d1acd-116">Parent elements</span></span>

|<span data-ttu-id="d1acd-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1acd-117">**Element**</span></span>|<span data-ttu-id="d1acd-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1acd-118">**Type**</span></span>|<span data-ttu-id="d1acd-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1acd-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d1acd-120">Shape</span><span class="sxs-lookup"><span data-stu-id="d1acd-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1acd-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1acd-122">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="d1acd-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d1acd-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d1acd-123">Child elements</span></span>

|<span data-ttu-id="d1acd-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="d1acd-124">**Element**</span></span>|<span data-ttu-id="d1acd-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="d1acd-125">**Type**</span></span>|<span data-ttu-id="d1acd-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1acd-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d1acd-127">cp</span><span class="sxs-lookup"><span data-stu-id="d1acd-127">cp</span></span>](cp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1acd-128">cp_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-128">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1acd-129">根据对应的 Char 元素格式的标记字符属性的开头，它是运行。</span><span class="sxs-lookup"><span data-stu-id="d1acd-129">Marks the beginning of a character properties run that is formatted according to the corresponding Char element.</span></span>  <br/> |
|[<span data-ttu-id="d1acd-130">fld</span><span class="sxs-lookup"><span data-stu-id="d1acd-130">fld</span></span>](fld-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1acd-131">fld_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-131">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1acd-132">指示相应的 Field 元素的文本域插入点。</span><span class="sxs-lookup"><span data-stu-id="d1acd-132">Indicates a text-field insertion point for the corresponding Field element.</span></span>  <br/> |
|[<span data-ttu-id="d1acd-133">pp</span><span class="sxs-lookup"><span data-stu-id="d1acd-133">pp</span></span>](pp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1acd-134">pp_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-134">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1acd-135">指定段落属性开始运行。</span><span class="sxs-lookup"><span data-stu-id="d1acd-135">Specifies the beginning of a paragraph properties run.</span></span>  <br/> |
|[<span data-ttu-id="d1acd-136">tp</span><span class="sxs-lookup"><span data-stu-id="d1acd-136">tp</span></span>](tp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d1acd-137">tp_Type</span><span class="sxs-lookup"><span data-stu-id="d1acd-137">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d1acd-138">指定运行选项卡属性的开头。</span><span class="sxs-lookup"><span data-stu-id="d1acd-138">Specifies the beginning of a tabs properties run.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="d1acd-139">Attributes</span><span class="sxs-lookup"><span data-stu-id="d1acd-139">Attributes</span></span>

<span data-ttu-id="d1acd-140">无。</span><span class="sxs-lookup"><span data-stu-id="d1acd-140">None.</span></span>
  

