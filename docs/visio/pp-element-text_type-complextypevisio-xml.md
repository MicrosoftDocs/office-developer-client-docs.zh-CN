---
title: pp 元素 （Text_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5444543-fcd9-91cc-e7f8-cf860caa9fcc
description: 指定段落属性开始运行。 到末尾的文字或直到下一个标记定义运行。
ms.openlocfilehash: bb2b0ab7a76c142b810ecd02dbc1b5ba7463520a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400097"
---
# <a name="pp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="18688-104">pp 元素 （Text_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="18688-104">pp element (Text_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="18688-105">指定段落属性开始运行。</span><span class="sxs-lookup"><span data-stu-id="18688-105">Specifies the beginning of a paragraph properties run.</span></span> <span data-ttu-id="18688-106">到末尾的文字或直到下一个标记定义运行。</span><span class="sxs-lookup"><span data-stu-id="18688-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="18688-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="18688-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="18688-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="18688-108">**Element type**</span></span> <br/> |[<span data-ttu-id="18688-109">pp_Type</span><span class="sxs-lookup"><span data-stu-id="18688-109">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="18688-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="18688-110">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="18688-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="18688-111">**Schema file**</span></span> <br/> |<span data-ttu-id="18688-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="18688-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="18688-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="18688-113">**Document parts**</span></span> <br/> |<span data-ttu-id="18688-114">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="18688-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="18688-115">定义</span><span class="sxs-lookup"><span data-stu-id="18688-115">Definition</span></span>

```XML
< xs:element name="pp" type="pp_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="18688-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="18688-116">Elements and attributes</span></span>

<span data-ttu-id="18688-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="18688-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="18688-118">父元素</span><span class="sxs-lookup"><span data-stu-id="18688-118">Parent elements</span></span>

|<span data-ttu-id="18688-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="18688-119">**Element**</span></span>|<span data-ttu-id="18688-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="18688-120">**Type**</span></span>|<span data-ttu-id="18688-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="18688-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="18688-122">Text</span><span class="sxs-lookup"><span data-stu-id="18688-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="18688-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="18688-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="18688-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="18688-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="18688-125">子元素</span><span class="sxs-lookup"><span data-stu-id="18688-125">Child elements</span></span>

<span data-ttu-id="18688-126">无。</span><span class="sxs-lookup"><span data-stu-id="18688-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="18688-127">属性</span><span class="sxs-lookup"><span data-stu-id="18688-127">Attributes</span></span>

|<span data-ttu-id="18688-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="18688-128">**Attribute**</span></span>|<span data-ttu-id="18688-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="18688-129">**Type**</span></span>|<span data-ttu-id="18688-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="18688-130">**Required**</span></span>|<span data-ttu-id="18688-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="18688-131">**Description**</span></span>|<span data-ttu-id="18688-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="18688-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="18688-133">IX</span><span class="sxs-lookup"><span data-stu-id="18688-133">IX</span></span>  <br/> |<span data-ttu-id="18688-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="18688-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="18688-135">必需</span><span class="sxs-lookup"><span data-stu-id="18688-135">required</span></span>  <br/> |<span data-ttu-id="18688-136">指定的格式应用于此运行**段落**元素的索引。</span><span class="sxs-lookup"><span data-stu-id="18688-136">The index of the **Para** element that specifies the formatting applied to this run.</span></span>  <br/> |<span data-ttu-id="18688-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="18688-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

