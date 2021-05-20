---
title: 'cp 元素 (Text_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4edd0a3f-e433-bf54-34cd-3b05fd10a5a5
description: 标记根据相应的 Char 元素设置格式的字符属性的开头。 运行定义到文本的末尾或直到下一个标记。
ms.openlocfilehash: 70f7d3f8333ff0f2c109862455fbd8cc3b340bf4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540558"
---
# <a name="cp-element-text_type-complextype-visio-xml"></a><span data-ttu-id="bf449-104">cp 元素 (Text_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="bf449-104">cp element (Text_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="bf449-105">标记根据相应的 Char 元素设置格式的字符属性的开头。</span><span class="sxs-lookup"><span data-stu-id="bf449-105">Marks the beginning of a character properties run that is formatted according to the corresponding Char element.</span></span> <span data-ttu-id="bf449-106">运行定义到文本的末尾或直到下一个标记。</span><span class="sxs-lookup"><span data-stu-id="bf449-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="bf449-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="bf449-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bf449-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="bf449-108">**Element type**</span></span> <br/> |[<span data-ttu-id="bf449-109">cp_Type</span><span class="sxs-lookup"><span data-stu-id="bf449-109">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="bf449-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bf449-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="bf449-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bf449-111">**Schema file**</span></span> <br/> |<span data-ttu-id="bf449-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="bf449-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="bf449-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="bf449-113">**Document parts**</span></span> <br/> |<span data-ttu-id="bf449-114">page#.xml，master#.xml</span><span class="sxs-lookup"><span data-stu-id="bf449-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bf449-115">定义</span><span class="sxs-lookup"><span data-stu-id="bf449-115">Definition</span></span>

```XML
< xs:element name="cp" type="cp_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bf449-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bf449-116">Elements and attributes</span></span>

<span data-ttu-id="bf449-117">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="bf449-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="bf449-118">父元素</span><span class="sxs-lookup"><span data-stu-id="bf449-118">Parent elements</span></span>

|<span data-ttu-id="bf449-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="bf449-119">**Element**</span></span>|<span data-ttu-id="bf449-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="bf449-120">**Type**</span></span>|<span data-ttu-id="bf449-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf449-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bf449-122">Text</span><span class="sxs-lookup"><span data-stu-id="bf449-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf449-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="bf449-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf449-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="bf449-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="bf449-125">子元素</span><span class="sxs-lookup"><span data-stu-id="bf449-125">Child elements</span></span>

<span data-ttu-id="bf449-126">无。</span><span class="sxs-lookup"><span data-stu-id="bf449-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="bf449-127">属性</span><span class="sxs-lookup"><span data-stu-id="bf449-127">Attributes</span></span>

|<span data-ttu-id="bf449-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="bf449-128">**Attribute**</span></span>|<span data-ttu-id="bf449-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="bf449-129">**Type**</span></span>|<span data-ttu-id="bf449-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="bf449-130">**Required**</span></span>|<span data-ttu-id="bf449-131">**描述**</span><span class="sxs-lookup"><span data-stu-id="bf449-131">**Description**</span></span>|<span data-ttu-id="bf449-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="bf449-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf449-133">IX</span><span class="sxs-lookup"><span data-stu-id="bf449-133">IX</span></span>  <br/> |<span data-ttu-id="bf449-134">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="bf449-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="bf449-135">必需</span><span class="sxs-lookup"><span data-stu-id="bf449-135">required</span></span>  <br/> |<span data-ttu-id="bf449-136">此属性运行表示的 Char 元素索引。</span><span class="sxs-lookup"><span data-stu-id="bf449-136">The Char element index that this property run represents.</span></span>  <br/> |<span data-ttu-id="bf449-137">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="bf449-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

