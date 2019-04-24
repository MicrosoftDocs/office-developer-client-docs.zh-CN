---
title: Text 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46211968-9ad8-07da-f725-3ad136b7a8a1
description: 包含形状的文本。
ms.openlocfilehash: f2c809d7db895a3635a5898d83d4583cd38f1249
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332366"
---
# <a name="text-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="9e2f2-103">Text 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9e2f2-103">Text element (ShapeSheet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9e2f2-104">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-104">Contains the text of a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9e2f2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9e2f2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9e2f2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9e2f2-107">Text_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-107">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9e2f2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9e2f2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9e2f2-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="9e2f2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9e2f2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9e2f2-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="9e2f2-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9e2f2-113">定义</span><span class="sxs-lookup"><span data-stu-id="9e2f2-113">Definition</span></span>

```XML
< xs:element name="Text" type="Text_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9e2f2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9e2f2-114">Elements and attributes</span></span>

<span data-ttu-id="9e2f2-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9e2f2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9e2f2-116">Parent elements</span></span>

|<span data-ttu-id="9e2f2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-117">**Element**</span></span>|<span data-ttu-id="9e2f2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-118">**Type**</span></span>|<span data-ttu-id="9e2f2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9e2f2-120">Shape</span><span class="sxs-lookup"><span data-stu-id="9e2f2-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e2f2-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e2f2-122">包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9e2f2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9e2f2-123">Child elements</span></span>

|<span data-ttu-id="9e2f2-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-124">**Element**</span></span>|<span data-ttu-id="9e2f2-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-125">**Type**</span></span>|<span data-ttu-id="9e2f2-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e2f2-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9e2f2-127">cp</span><span class="sxs-lookup"><span data-stu-id="9e2f2-127">cp</span></span>](cp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e2f2-128">cp_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-128">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e2f2-129">标记根据相应的 Char 元素格式化的字符属性的开头。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-129">Marks the beginning of a character properties run that is formatted according to the corresponding Char element.</span></span>  <br/> |
|[<span data-ttu-id="9e2f2-130">.fld</span><span class="sxs-lookup"><span data-stu-id="9e2f2-130">fld</span></span>](fld-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e2f2-131">fld_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-131">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e2f2-132">指示对应的 field 元素的文本字段插入点。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-132">Indicates a text-field insertion point for the corresponding Field element.</span></span>  <br/> |
|[<span data-ttu-id="9e2f2-133">pp</span><span class="sxs-lookup"><span data-stu-id="9e2f2-133">pp</span></span>](pp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e2f2-134">pp_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-134">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e2f2-135">指定段落属性的开头。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-135">Specifies the beginning of a paragraph properties run.</span></span>  <br/> |
|[<span data-ttu-id="9e2f2-136">tp</span><span class="sxs-lookup"><span data-stu-id="9e2f2-136">tp</span></span>](tp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9e2f2-137">tp_Type</span><span class="sxs-lookup"><span data-stu-id="9e2f2-137">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9e2f2-138">指定要运行的选项卡属性的开头。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-138">Specifies the beginning of a tabs properties run.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="9e2f2-139">Attributes</span><span class="sxs-lookup"><span data-stu-id="9e2f2-139">Attributes</span></span>

<span data-ttu-id="9e2f2-140">无。</span><span class="sxs-lookup"><span data-stu-id="9e2f2-140">None.</span></span>
  

