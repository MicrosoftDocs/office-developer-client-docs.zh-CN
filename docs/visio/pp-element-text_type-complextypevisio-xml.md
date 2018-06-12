---
title: pp 元素 （Text_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5444543-fcd9-91cc-e7f8-cf860caa9fcc
description: 指定段落属性开始运行。 到末尾的文字或直到下一个标记定义运行。
ms.openlocfilehash: ce1bdd89ca9a5eb5b7ce9b73cc2354ccfde1c125
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780957"
---
# <a name="pp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="925b4-104">pp 元素 （Text_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="925b4-104">pp element (Text_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="925b4-105">指定段落属性开始运行。</span><span class="sxs-lookup"><span data-stu-id="925b4-105">Specifies the beginning of a paragraph properties run.</span></span> <span data-ttu-id="925b4-106">到末尾的文字或直到下一个标记定义运行。</span><span class="sxs-lookup"><span data-stu-id="925b4-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="925b4-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="925b4-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="925b4-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="925b4-108">**Element type**</span></span> <br/> |[<span data-ttu-id="925b4-109">pp_Type</span><span class="sxs-lookup"><span data-stu-id="925b4-109">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="925b4-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="925b4-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="925b4-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="925b4-111">**Schema file**</span></span> <br/> |<span data-ttu-id="925b4-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="925b4-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="925b4-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="925b4-113">**Document parts**</span></span> <br/> |<span data-ttu-id="925b4-114">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="925b4-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="925b4-115">定义</span><span class="sxs-lookup"><span data-stu-id="925b4-115">Definition</span></span>

```XML
< xs:element name="pp" type="pp_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="925b4-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="925b4-116">Elements and attributes</span></span>

<span data-ttu-id="925b4-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="925b4-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="925b4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="925b4-118">Parent elements</span></span>

|<span data-ttu-id="925b4-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="925b4-119">**Element**</span></span>|<span data-ttu-id="925b4-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="925b4-120">**Type**</span></span>|<span data-ttu-id="925b4-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="925b4-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="925b4-122">Text</span><span class="sxs-lookup"><span data-stu-id="925b4-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="925b4-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="925b4-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="925b4-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="925b4-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="925b4-125">子元素</span><span class="sxs-lookup"><span data-stu-id="925b4-125">Child elements</span></span>

<span data-ttu-id="925b4-126">无。</span><span class="sxs-lookup"><span data-stu-id="925b4-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="925b4-127">属性</span><span class="sxs-lookup"><span data-stu-id="925b4-127">Attributes</span></span>

|<span data-ttu-id="925b4-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="925b4-128">**Attribute**</span></span>|<span data-ttu-id="925b4-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="925b4-129">**Type**</span></span>|<span data-ttu-id="925b4-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="925b4-130">**Required**</span></span>|<span data-ttu-id="925b4-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="925b4-131">**Description**</span></span>|<span data-ttu-id="925b4-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="925b4-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="925b4-133">IX</span><span class="sxs-lookup"><span data-stu-id="925b4-133">IX</span></span>  <br/> |<span data-ttu-id="925b4-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="925b4-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="925b4-135">必需</span><span class="sxs-lookup"><span data-stu-id="925b4-135">required</span></span>  <br/> |<span data-ttu-id="925b4-136">指定的格式应用于此运行**段落**元素的索引。</span><span class="sxs-lookup"><span data-stu-id="925b4-136">The index of the **Para** element that specifies the formatting applied to this run.</span></span>  <br/> |<span data-ttu-id="925b4-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="925b4-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

