---
title: Text 元素 (ShapeSheet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46211968-9ad8-07da-f725-3ad136b7a8a1
description: 包含形状的文本。
ms.openlocfilehash: 4b03bc2539b80e49daae9d14f3e2ad07a51de9f1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541923"
---
# <a name="text-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="fe403-103">Text 元素 (ShapeSheet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fe403-103">Text element (ShapeSheet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="fe403-104">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="fe403-104">Contains the text of a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fe403-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fe403-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fe403-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fe403-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fe403-107">Text_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-107">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fe403-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fe403-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fe403-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fe403-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fe403-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="fe403-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fe403-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fe403-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fe403-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="fe403-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fe403-113">定义</span><span class="sxs-lookup"><span data-stu-id="fe403-113">Definition</span></span>

```XML
< xs:element name="Text" type="Text_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fe403-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fe403-114">Elements and attributes</span></span>

<span data-ttu-id="fe403-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="fe403-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fe403-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fe403-116">Parent elements</span></span>

|<span data-ttu-id="fe403-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe403-117">**Element**</span></span>|<span data-ttu-id="fe403-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe403-118">**Type**</span></span>|<span data-ttu-id="fe403-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe403-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fe403-120">Shape</span><span class="sxs-lookup"><span data-stu-id="fe403-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe403-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe403-122">包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。</span><span class="sxs-lookup"><span data-stu-id="fe403-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="fe403-123">子元素</span><span class="sxs-lookup"><span data-stu-id="fe403-123">Child elements</span></span>

|<span data-ttu-id="fe403-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe403-124">**Element**</span></span>|<span data-ttu-id="fe403-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe403-125">**Type**</span></span>|<span data-ttu-id="fe403-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe403-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fe403-127">cp</span><span class="sxs-lookup"><span data-stu-id="fe403-127">cp</span></span>](cp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe403-128">cp_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-128">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe403-129">标记根据相应的 Char 元素格式化的字符属性的开头。</span><span class="sxs-lookup"><span data-stu-id="fe403-129">Marks the beginning of a character properties run that is formatted according to the corresponding Char element.</span></span>  <br/> |
|[<span data-ttu-id="fe403-130">.fld</span><span class="sxs-lookup"><span data-stu-id="fe403-130">fld</span></span>](fld-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe403-131">fld_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-131">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe403-132">指示对应的 Field 元素的文本字段插入点。</span><span class="sxs-lookup"><span data-stu-id="fe403-132">Indicates a text-field insertion point for the corresponding Field element.</span></span>  <br/> |
|[<span data-ttu-id="fe403-133">pp</span><span class="sxs-lookup"><span data-stu-id="fe403-133">pp</span></span>](pp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe403-134">pp_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-134">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe403-135">指定段落属性的开头。</span><span class="sxs-lookup"><span data-stu-id="fe403-135">Specifies the beginning of a paragraph properties run.</span></span>  <br/> |
|[<span data-ttu-id="fe403-136">tp</span><span class="sxs-lookup"><span data-stu-id="fe403-136">tp</span></span>](tp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe403-137">tp_Type</span><span class="sxs-lookup"><span data-stu-id="fe403-137">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe403-138">指定要运行的选项卡属性的开头。</span><span class="sxs-lookup"><span data-stu-id="fe403-138">Specifies the beginning of a tabs properties run.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="fe403-139">Attributes</span><span class="sxs-lookup"><span data-stu-id="fe403-139">Attributes</span></span>

<span data-ttu-id="fe403-140">无。</span><span class="sxs-lookup"><span data-stu-id="fe403-140">None.</span></span>
  

