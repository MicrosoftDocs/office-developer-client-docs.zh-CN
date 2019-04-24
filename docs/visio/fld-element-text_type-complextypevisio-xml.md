---
title: .fld 元素 (Text_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 92d90240-012b-9598-c893-6e7085813aa5
description: 指示对应的 field 元素的文本字段插入点。
ms.openlocfilehash: a7303697a9471dab68f5b1cf851f60d51650a84e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346212"
---
# <a name="fld-element-texttype-complextype-visio-xml"></a><span data-ttu-id="d2707-103">.fld 元素 (Text_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="d2707-103">fld element (Text_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="d2707-104">指示对应的**field**元素的文本字段插入点。</span><span class="sxs-lookup"><span data-stu-id="d2707-104">Indicates a text-field insertion point for the corresponding **Field** element.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="d2707-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d2707-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d2707-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d2707-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d2707-107">fld_Type</span><span class="sxs-lookup"><span data-stu-id="d2707-107">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d2707-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d2707-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d2707-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d2707-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d2707-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="d2707-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d2707-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d2707-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d2707-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="d2707-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d2707-113">定义</span><span class="sxs-lookup"><span data-stu-id="d2707-113">Definition</span></span>

```XML
< xs:element name="fld" type="fld_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d2707-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d2707-114">Elements and attributes</span></span>

<span data-ttu-id="d2707-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d2707-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d2707-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d2707-116">Parent elements</span></span>

|<span data-ttu-id="d2707-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d2707-117">**Element**</span></span>|<span data-ttu-id="d2707-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d2707-118">**Type**</span></span>|<span data-ttu-id="d2707-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d2707-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d2707-120">Text</span><span class="sxs-lookup"><span data-stu-id="d2707-120">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d2707-121">Text_Type</span><span class="sxs-lookup"><span data-stu-id="d2707-121">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d2707-122">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="d2707-122">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d2707-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d2707-123">Child elements</span></span>

<span data-ttu-id="d2707-124">无。</span><span class="sxs-lookup"><span data-stu-id="d2707-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d2707-125">属性</span><span class="sxs-lookup"><span data-stu-id="d2707-125">Attributes</span></span>

|<span data-ttu-id="d2707-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="d2707-126">**Attribute**</span></span>|<span data-ttu-id="d2707-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="d2707-127">**Type**</span></span>|<span data-ttu-id="d2707-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="d2707-128">**Required**</span></span>|<span data-ttu-id="d2707-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="d2707-129">**Description**</span></span>|<span data-ttu-id="d2707-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="d2707-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2707-131">IX</span><span class="sxs-lookup"><span data-stu-id="d2707-131">IX</span></span>  <br/> |<span data-ttu-id="d2707-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="d2707-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="d2707-133">必需</span><span class="sxs-lookup"><span data-stu-id="d2707-133">required</span></span>  <br/> |<span data-ttu-id="d2707-134">元素在其父元素中的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="d2707-134">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="d2707-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="d2707-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

