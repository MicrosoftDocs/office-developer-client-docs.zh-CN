---
title: tp 元素 (Text_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b13b9328-c6a0-e282-257c-2de55901df6a
description: 指定要运行的选项卡属性的开头。 运行被定义为文本的末尾或直到下一个标记。
ms.openlocfilehash: dad7a3de715473a75c601c1e391c9d51fc1cab85
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542973"
---
# <a name="tp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="e9917-104">tp 元素 (Text_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e9917-104">tp element (Text_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="e9917-105">指定要运行的选项卡属性的开头。</span><span class="sxs-lookup"><span data-stu-id="e9917-105">Specifies the beginning of a tabs properties run.</span></span> <span data-ttu-id="e9917-106">运行被定义为文本的末尾或直到下一个标记。</span><span class="sxs-lookup"><span data-stu-id="e9917-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e9917-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="e9917-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e9917-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e9917-108">**Element type**</span></span> <br/> |[<span data-ttu-id="e9917-109">tp_Type</span><span class="sxs-lookup"><span data-stu-id="e9917-109">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e9917-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e9917-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e9917-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e9917-111">**Schema file**</span></span> <br/> |<span data-ttu-id="e9917-112">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e9917-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e9917-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e9917-113">**Document parts**</span></span> <br/> |<span data-ttu-id="e9917-114">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="e9917-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e9917-115">定义</span><span class="sxs-lookup"><span data-stu-id="e9917-115">Definition</span></span>

```XML
< xs:element name="tp" type="tp_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e9917-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e9917-116">Elements and attributes</span></span>

<span data-ttu-id="e9917-117">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e9917-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e9917-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e9917-118">Parent elements</span></span>

|<span data-ttu-id="e9917-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="e9917-119">**Element**</span></span>|<span data-ttu-id="e9917-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="e9917-120">**Type**</span></span>|<span data-ttu-id="e9917-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="e9917-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e9917-122">Text</span><span class="sxs-lookup"><span data-stu-id="e9917-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e9917-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="e9917-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e9917-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="e9917-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e9917-125">子元素</span><span class="sxs-lookup"><span data-stu-id="e9917-125">Child elements</span></span>

<span data-ttu-id="e9917-126">无。</span><span class="sxs-lookup"><span data-stu-id="e9917-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e9917-127">属性</span><span class="sxs-lookup"><span data-stu-id="e9917-127">Attributes</span></span>

|<span data-ttu-id="e9917-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="e9917-128">**Attribute**</span></span>|<span data-ttu-id="e9917-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="e9917-129">**Type**</span></span>|<span data-ttu-id="e9917-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="e9917-130">**Required**</span></span>|<span data-ttu-id="e9917-131">**描述**</span><span class="sxs-lookup"><span data-stu-id="e9917-131">**Description**</span></span>|<span data-ttu-id="e9917-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e9917-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9917-133">IX</span><span class="sxs-lookup"><span data-stu-id="e9917-133">IX</span></span>  <br/> |<span data-ttu-id="e9917-134">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e9917-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e9917-135">必需</span><span class="sxs-lookup"><span data-stu-id="e9917-135">required</span></span>  <br/> |<span data-ttu-id="e9917-136">元素在其父元素中的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="e9917-136">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="e9917-137">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e9917-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

