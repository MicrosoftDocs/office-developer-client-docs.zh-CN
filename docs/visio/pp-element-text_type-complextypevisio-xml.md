---
title: pp 元素 (Text_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5444543-fcd9-91cc-e7f8-cf860caa9fcc
description: 指定段落属性的开头。 运行被定义为文本的末尾或直到下一个标记。
ms.openlocfilehash: 695958c77f730abed03f50d6ad9c71f4de76dd63
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34537736"
---
# <a name="pp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="bfbe3-104">pp 元素 (Text_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="bfbe3-104">pp element (Text_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="bfbe3-105">指定段落属性的开头。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-105">Specifies the beginning of a paragraph properties run.</span></span> <span data-ttu-id="bfbe3-106">运行被定义为文本的末尾或直到下一个标记。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="bfbe3-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="bfbe3-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bfbe3-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-108">**Element type**</span></span> <br/> |[<span data-ttu-id="bfbe3-109">pp_Type</span><span class="sxs-lookup"><span data-stu-id="bfbe3-109">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="bfbe3-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="bfbe3-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-111">**Schema file**</span></span> <br/> |<span data-ttu-id="bfbe3-112">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="bfbe3-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="bfbe3-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-113">**Document parts**</span></span> <br/> |<span data-ttu-id="bfbe3-114">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="bfbe3-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bfbe3-115">定义</span><span class="sxs-lookup"><span data-stu-id="bfbe3-115">Definition</span></span>

```XML
< xs:element name="pp" type="pp_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bfbe3-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bfbe3-116">Elements and attributes</span></span>

<span data-ttu-id="bfbe3-117">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="bfbe3-118">父元素</span><span class="sxs-lookup"><span data-stu-id="bfbe3-118">Parent elements</span></span>

|<span data-ttu-id="bfbe3-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-119">**Element**</span></span>|<span data-ttu-id="bfbe3-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-120">**Type**</span></span>|<span data-ttu-id="bfbe3-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bfbe3-122">Text</span><span class="sxs-lookup"><span data-stu-id="bfbe3-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bfbe3-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="bfbe3-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bfbe3-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="bfbe3-125">子元素</span><span class="sxs-lookup"><span data-stu-id="bfbe3-125">Child elements</span></span>

<span data-ttu-id="bfbe3-126">无。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="bfbe3-127">属性</span><span class="sxs-lookup"><span data-stu-id="bfbe3-127">Attributes</span></span>

|<span data-ttu-id="bfbe3-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-128">**Attribute**</span></span>|<span data-ttu-id="bfbe3-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-129">**Type**</span></span>|<span data-ttu-id="bfbe3-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-130">**Required**</span></span>|<span data-ttu-id="bfbe3-131">**描述**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-131">**Description**</span></span>|<span data-ttu-id="bfbe3-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="bfbe3-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bfbe3-133">IX</span><span class="sxs-lookup"><span data-stu-id="bfbe3-133">IX</span></span>  <br/> |<span data-ttu-id="bfbe3-134">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="bfbe3-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="bfbe3-135">必需</span><span class="sxs-lookup"><span data-stu-id="bfbe3-135">required</span></span>  <br/> |<span data-ttu-id="bfbe3-136">**段落**元素的索引, 该元素指定应用于此运行的格式。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-136">The index of the **Para** element that specifies the formatting applied to this run.</span></span>  <br/> |<span data-ttu-id="bfbe3-137">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="bfbe3-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

