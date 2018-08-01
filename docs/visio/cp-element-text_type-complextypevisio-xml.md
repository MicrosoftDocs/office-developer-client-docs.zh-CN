---
title: cp 元素 （Text_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4edd0a3f-e433-bf54-34cd-3b05fd10a5a5
description: 根据对应的 Char 元素格式的标记字符属性的开头，它是运行。 到末尾的文字或直到下一个标记定义运行。
ms.openlocfilehash: 16e5bb94afeb860220c6cb49a9b98e36e45d76cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780007"
---
# <a name="cp-element-texttype-complextype-visio-xml"></a><span data-ttu-id="34d39-104">cp 元素 （Text_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="34d39-104">cp element (Text_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="34d39-105">根据对应的 Char 元素格式的标记字符属性的开头，它是运行。</span><span class="sxs-lookup"><span data-stu-id="34d39-105">Marks the beginning of a character properties run that is formatted according to the corresponding Char element.</span></span> <span data-ttu-id="34d39-106">到末尾的文字或直到下一个标记定义运行。</span><span class="sxs-lookup"><span data-stu-id="34d39-106">The run is defined to the end of the text or until the next tag.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="34d39-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="34d39-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="34d39-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="34d39-108">**Element type**</span></span> <br/> |[<span data-ttu-id="34d39-109">cp_Type</span><span class="sxs-lookup"><span data-stu-id="34d39-109">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="34d39-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="34d39-110">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="34d39-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="34d39-111">**Schema file**</span></span> <br/> |<span data-ttu-id="34d39-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="34d39-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="34d39-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="34d39-113">**Document parts**</span></span> <br/> |<span data-ttu-id="34d39-114">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="34d39-114">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="34d39-115">定义</span><span class="sxs-lookup"><span data-stu-id="34d39-115">Definition</span></span>

```XML
< xs:element name="cp" type="cp_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="34d39-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="34d39-116">Elements and attributes</span></span>

<span data-ttu-id="34d39-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="34d39-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="34d39-118">父元素</span><span class="sxs-lookup"><span data-stu-id="34d39-118">Parent elements</span></span>

|<span data-ttu-id="34d39-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="34d39-119">**Element**</span></span>|<span data-ttu-id="34d39-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="34d39-120">**Type**</span></span>|<span data-ttu-id="34d39-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="34d39-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="34d39-122">Text</span><span class="sxs-lookup"><span data-stu-id="34d39-122">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="34d39-123">Text_Type</span><span class="sxs-lookup"><span data-stu-id="34d39-123">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="34d39-124">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="34d39-124">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="34d39-125">子元素</span><span class="sxs-lookup"><span data-stu-id="34d39-125">Child elements</span></span>

<span data-ttu-id="34d39-126">无。</span><span class="sxs-lookup"><span data-stu-id="34d39-126">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="34d39-127">属性</span><span class="sxs-lookup"><span data-stu-id="34d39-127">Attributes</span></span>

|<span data-ttu-id="34d39-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="34d39-128">**Attribute**</span></span>|<span data-ttu-id="34d39-129">**类型**</span><span class="sxs-lookup"><span data-stu-id="34d39-129">**Type**</span></span>|<span data-ttu-id="34d39-130">**必需**</span><span class="sxs-lookup"><span data-stu-id="34d39-130">**Required**</span></span>|<span data-ttu-id="34d39-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="34d39-131">**Description**</span></span>|<span data-ttu-id="34d39-132">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="34d39-132">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="34d39-133">IX</span><span class="sxs-lookup"><span data-stu-id="34d39-133">IX</span></span>  <br/> |<span data-ttu-id="34d39-134">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="34d39-134">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="34d39-135">必需</span><span class="sxs-lookup"><span data-stu-id="34d39-135">required</span></span>  <br/> |<span data-ttu-id="34d39-136">运行此属性表示 Char 元素索引。</span><span class="sxs-lookup"><span data-stu-id="34d39-136">The Char element index that this property run represents.</span></span>  <br/> |<span data-ttu-id="34d39-137">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="34d39-137">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

