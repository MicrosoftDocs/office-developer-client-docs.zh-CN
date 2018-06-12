---
title: tp 元素 （Text_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b13b9328-c6a0-e282-257c-2de55901df6a
description: 指定运行选项卡属性的开头。 到末尾的文字或直到下一个标记定义运行。
ms.openlocfilehash: 9b98374af4ffbf2eaeaea61dcb1dbb49214f01b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781542"
---
# <a name="tp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="09118-104">tp 元素 （Text_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="09118-104">tp element (Text_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="09118-105">指定运行选项卡属性的开头。</span><span class="sxs-lookup"><span data-stu-id="09118-105">Specifies the beginning of a tabs properties run.</span></span> <span data-ttu-id="09118-106">到末尾的文字或直到下一个标记定义运行。</span><span class="sxs-lookup"><span data-stu-id="09118-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="09118-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="09118-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="09118-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="09118-108">**Element type**</span></span> <br/> |[<span data-ttu-id="09118-109">tp_Type</span><span class="sxs-lookup"><span data-stu-id="09118-109">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="09118-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="09118-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="09118-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="09118-111">**Schema file**</span></span> <br/> |<span data-ttu-id="09118-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="09118-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="09118-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="09118-113">**Document parts**</span></span> <br/> |<span data-ttu-id="09118-114">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="09118-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="09118-115">定义</span><span class="sxs-lookup"><span data-stu-id="09118-115">Definition</span></span>

```XML
< xs:element name="tp" type="tp_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="09118-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="09118-116">Elements and attributes</span></span>

<span data-ttu-id="09118-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="09118-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="09118-118">父元素</span><span class="sxs-lookup"><span data-stu-id="09118-118">Parent elements</span></span>

|<span data-ttu-id="09118-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="09118-119">**Element**</span></span>|<span data-ttu-id="09118-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="09118-120">**Type**</span></span>|<span data-ttu-id="09118-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="09118-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="09118-122">Text</span><span class="sxs-lookup"><span data-stu-id="09118-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="09118-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="09118-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="09118-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="09118-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="09118-125">子元素</span><span class="sxs-lookup"><span data-stu-id="09118-125">Child elements</span></span>

<span data-ttu-id="09118-126">无。</span><span class="sxs-lookup"><span data-stu-id="09118-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="09118-127">属性</span><span class="sxs-lookup"><span data-stu-id="09118-127">Attributes</span></span>

|<span data-ttu-id="09118-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="09118-128">**Attribute**</span></span>|<span data-ttu-id="09118-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="09118-129">**Type**</span></span>|<span data-ttu-id="09118-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="09118-130">**Required**</span></span>|<span data-ttu-id="09118-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="09118-131">**Description**</span></span>|<span data-ttu-id="09118-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="09118-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="09118-133">IX</span><span class="sxs-lookup"><span data-stu-id="09118-133">IX</span></span>  <br/> |<span data-ttu-id="09118-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="09118-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="09118-135">必需</span><span class="sxs-lookup"><span data-stu-id="09118-135">required</span></span>  <br/> |<span data-ttu-id="09118-136">其父元素中的元素的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="09118-136">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="09118-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="09118-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

