---
title: ColorEntry 元素 (Colors_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f325ad8-bbc7-28bf-9e48-1fde4fbdbdc0
description: 包含颜色表项。
ms.openlocfilehash: 14ef92069ce8d963ce4a0770324843321804c5cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358084"
---
# <a name="colorentry-element-colorstype-complextype-visio-xml"></a><span data-ttu-id="e1ee3-103">ColorEntry 元素 (Colors_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e1ee3-103">ColorEntry element (Colors_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="e1ee3-104">包含颜色表项。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-104">Contains a color table entry.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e1ee3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e1ee3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e1ee3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e1ee3-107">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="e1ee3-107">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e1ee3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e1ee3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e1ee3-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e1ee3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e1ee3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e1ee3-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="e1ee3-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e1ee3-113">定义</span><span class="sxs-lookup"><span data-stu-id="e1ee3-113">Definition</span></span>

```XML
< xs:element name="ColorEntry" type="ColorEntry_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e1ee3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e1ee3-114">Elements and attributes</span></span>

<span data-ttu-id="e1ee3-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e1ee3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e1ee3-116">Parent elements</span></span>

|<span data-ttu-id="e1ee3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-117">**Element**</span></span>|<span data-ttu-id="e1ee3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-118">**Type**</span></span>|<span data-ttu-id="e1ee3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e1ee3-120">Colors</span><span class="sxs-lookup"><span data-stu-id="e1ee3-120">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e1ee3-121">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="e1ee3-121">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e1ee3-122">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-122">Contains the document's color table.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e1ee3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e1ee3-123">Child elements</span></span>

<span data-ttu-id="e1ee3-124">无。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e1ee3-125">属性</span><span class="sxs-lookup"><span data-stu-id="e1ee3-125">Attributes</span></span>

|<span data-ttu-id="e1ee3-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-126">**Attribute**</span></span>|<span data-ttu-id="e1ee3-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-127">**Type**</span></span>|<span data-ttu-id="e1ee3-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-128">**Required**</span></span>|<span data-ttu-id="e1ee3-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-129">**Description**</span></span>|<span data-ttu-id="e1ee3-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e1ee3-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1ee3-131">IX</span><span class="sxs-lookup"><span data-stu-id="e1ee3-131">IX</span></span>  <br/> |<span data-ttu-id="e1ee3-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e1ee3-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e1ee3-133">必需</span><span class="sxs-lookup"><span data-stu-id="e1ee3-133">required</span></span>  <br/> |<span data-ttu-id="e1ee3-134">元素在其父元素中的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-134">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="e1ee3-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e1ee3-136">RGB</span><span class="sxs-lookup"><span data-stu-id="e1ee3-136">RGB</span></span>  <br/> |<span data-ttu-id="e1ee3-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e1ee3-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e1ee3-138">必需</span><span class="sxs-lookup"><span data-stu-id="e1ee3-138">required</span></span>  <br/> |<span data-ttu-id="e1ee3-139">颜色表项的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-139">The hexadecimal value of the color table entry.</span></span>  <br/> |<span data-ttu-id="e1ee3-140">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e1ee3-140">Values of the xsd:string type.</span></span>  <br/> |
   

