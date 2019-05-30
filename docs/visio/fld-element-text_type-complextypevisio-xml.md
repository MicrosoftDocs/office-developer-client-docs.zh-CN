---
title: .fld 元素 (Text_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 92d90240-012b-9598-c893-6e7085813aa5
description: 指示对应的 Field 元素的文本字段插入点。
ms.openlocfilehash: efacb7ed11968dec5d5c2f62b0ca3e3bcd8580c0
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539612"
---
# <a name="fld-element-texttype-complextype-visio-xml"></a><span data-ttu-id="279f8-103">.fld 元素 (Text_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="279f8-103">fld element (Text_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="279f8-104">指示对应的**field**元素的文本字段插入点。</span><span class="sxs-lookup"><span data-stu-id="279f8-104">Indicates a text-field insertion point for the corresponding **Field** element.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="279f8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="279f8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="279f8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="279f8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="279f8-107">fld_Type</span><span class="sxs-lookup"><span data-stu-id="279f8-107">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="279f8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="279f8-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="279f8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="279f8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="279f8-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="279f8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="279f8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="279f8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="279f8-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="279f8-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="279f8-113">定义</span><span class="sxs-lookup"><span data-stu-id="279f8-113">Definition</span></span>

```XML
< xs:element name="fld" type="fld_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="279f8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="279f8-114">Elements and attributes</span></span>

<span data-ttu-id="279f8-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="279f8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="279f8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="279f8-116">Parent elements</span></span>

|<span data-ttu-id="279f8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="279f8-117">**Element**</span></span>|<span data-ttu-id="279f8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="279f8-118">**Type**</span></span>|<span data-ttu-id="279f8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="279f8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="279f8-120">Text</span><span class="sxs-lookup"><span data-stu-id="279f8-120">Text</span></span>](text-element-shapesheet_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="279f8-121">Text_Type</span><span class="sxs-lookup"><span data-stu-id="279f8-121">Text_Type</span></span>](text_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="279f8-122">包含形状的文本。</span><span class="sxs-lookup"><span data-stu-id="279f8-122">Contains the text of a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="279f8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="279f8-123">Child elements</span></span>

<span data-ttu-id="279f8-124">无。</span><span class="sxs-lookup"><span data-stu-id="279f8-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="279f8-125">属性</span><span class="sxs-lookup"><span data-stu-id="279f8-125">Attributes</span></span>

|<span data-ttu-id="279f8-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="279f8-126">**Attribute**</span></span>|<span data-ttu-id="279f8-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="279f8-127">**Type**</span></span>|<span data-ttu-id="279f8-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="279f8-128">**Required**</span></span>|<span data-ttu-id="279f8-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="279f8-129">**Description**</span></span>|<span data-ttu-id="279f8-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="279f8-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="279f8-131">IX</span><span class="sxs-lookup"><span data-stu-id="279f8-131">IX</span></span>  <br/> |<span data-ttu-id="279f8-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="279f8-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="279f8-133">必需</span><span class="sxs-lookup"><span data-stu-id="279f8-133">required</span></span>  <br/> |<span data-ttu-id="279f8-134">元素在其父元素中的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="279f8-134">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="279f8-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="279f8-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

