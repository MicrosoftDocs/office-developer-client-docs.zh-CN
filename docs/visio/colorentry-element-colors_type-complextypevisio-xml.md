---
title: ColorEntry 元素 （Colors_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f325ad8-bbc7-28bf-9e48-1fde4fbdbdc0
description: 包含颜色表项。
ms.openlocfilehash: 934680b36428dd272d383ce421e86ae6d5c707cf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779906"
---
# <a name="colorentry-element-colorstype-complextype-visio-xml"></a><span data-ttu-id="4805a-103">ColorEntry 元素 （Colors_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4805a-103">ColorEntry element (Colors_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="4805a-104">包含颜色表项。</span><span class="sxs-lookup"><span data-stu-id="4805a-104">Contains a color table entry.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4805a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4805a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4805a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4805a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4805a-107">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="4805a-107">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4805a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4805a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4805a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4805a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4805a-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4805a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4805a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4805a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4805a-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="4805a-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4805a-113">定义</span><span class="sxs-lookup"><span data-stu-id="4805a-113">Definition</span></span>

```XML
< xs:element name="ColorEntry" type="ColorEntry_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4805a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4805a-114">Elements and attributes</span></span>

<span data-ttu-id="4805a-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4805a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4805a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4805a-116">Parent elements</span></span>

|<span data-ttu-id="4805a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4805a-117">**Element**</span></span>|<span data-ttu-id="4805a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4805a-118">**Type**</span></span>|<span data-ttu-id="4805a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4805a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4805a-120">颜色</span><span class="sxs-lookup"><span data-stu-id="4805a-120">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4805a-121">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="4805a-121">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4805a-122">包含文档颜色表。</span><span class="sxs-lookup"><span data-stu-id="4805a-122">Contains the document's color table.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4805a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4805a-123">Child elements</span></span>

<span data-ttu-id="4805a-124">无。</span><span class="sxs-lookup"><span data-stu-id="4805a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4805a-125">属性</span><span class="sxs-lookup"><span data-stu-id="4805a-125">Attributes</span></span>

|<span data-ttu-id="4805a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="4805a-126">**Attribute**</span></span>|<span data-ttu-id="4805a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="4805a-127">**Type**</span></span>|<span data-ttu-id="4805a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="4805a-128">**Required**</span></span>|<span data-ttu-id="4805a-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="4805a-129">**Description**</span></span>|<span data-ttu-id="4805a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4805a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4805a-131">IX</span><span class="sxs-lookup"><span data-stu-id="4805a-131">IX</span></span>  <br/> |<span data-ttu-id="4805a-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4805a-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4805a-133">必需</span><span class="sxs-lookup"><span data-stu-id="4805a-133">required</span></span>  <br/> |<span data-ttu-id="4805a-134">其父元素中的元素的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="4805a-134">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="4805a-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4805a-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4805a-136">RGB</span><span class="sxs-lookup"><span data-stu-id="4805a-136">RGB</span></span>  <br/> |<span data-ttu-id="4805a-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4805a-137">xsd:string</span></span>  <br/> |<span data-ttu-id="4805a-138">必需</span><span class="sxs-lookup"><span data-stu-id="4805a-138">required</span></span>  <br/> |<span data-ttu-id="4805a-139">颜色表条目的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="4805a-139">The hexadecimal value of the color table entry.</span></span>  <br/> |<span data-ttu-id="4805a-140">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4805a-140">Values of the xsd:string type.</span></span>  <br/> |
   

