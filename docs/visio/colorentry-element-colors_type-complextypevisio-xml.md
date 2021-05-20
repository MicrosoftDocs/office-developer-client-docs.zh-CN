---
title: 'ColorEntry 元素 (Colors_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f325ad8-bbc7-28bf-9e48-1fde4fbdbdc0
description: 包含颜色表条目。
ms.openlocfilehash: f2221d8d32823e5eec4a100eaf4e8f62b914df28
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540180"
---
# <a name="colorentry-element-colors_type-complextype-visio-xml"></a><span data-ttu-id="42201-103">ColorEntry 元素 (Colors_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="42201-103">ColorEntry element (Colors_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="42201-104">包含颜色表条目。</span><span class="sxs-lookup"><span data-stu-id="42201-104">Contains a color table entry.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="42201-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="42201-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="42201-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="42201-106">**Element type**</span></span> <br/> |[<span data-ttu-id="42201-107">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="42201-107">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="42201-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="42201-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="42201-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="42201-109">**Schema file**</span></span> <br/> |<span data-ttu-id="42201-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="42201-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="42201-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="42201-111">**Document parts**</span></span> <br/> |<span data-ttu-id="42201-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="42201-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="42201-113">定义</span><span class="sxs-lookup"><span data-stu-id="42201-113">Definition</span></span>

```XML
< xs:element name="ColorEntry" type="ColorEntry_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="42201-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="42201-114">Elements and attributes</span></span>

<span data-ttu-id="42201-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="42201-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="42201-116">父元素</span><span class="sxs-lookup"><span data-stu-id="42201-116">Parent elements</span></span>

|<span data-ttu-id="42201-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="42201-117">**Element**</span></span>|<span data-ttu-id="42201-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="42201-118">**Type**</span></span>|<span data-ttu-id="42201-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="42201-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="42201-120">Colors</span><span class="sxs-lookup"><span data-stu-id="42201-120">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="42201-121">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="42201-121">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="42201-122">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="42201-122">Contains the document's color table.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="42201-123">子元素</span><span class="sxs-lookup"><span data-stu-id="42201-123">Child elements</span></span>

<span data-ttu-id="42201-124">无。</span><span class="sxs-lookup"><span data-stu-id="42201-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="42201-125">属性</span><span class="sxs-lookup"><span data-stu-id="42201-125">Attributes</span></span>

|<span data-ttu-id="42201-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="42201-126">**Attribute**</span></span>|<span data-ttu-id="42201-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="42201-127">**Type**</span></span>|<span data-ttu-id="42201-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="42201-128">**Required**</span></span>|<span data-ttu-id="42201-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="42201-129">**Description**</span></span>|<span data-ttu-id="42201-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="42201-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42201-131">IX</span><span class="sxs-lookup"><span data-stu-id="42201-131">IX</span></span>  <br/> |<span data-ttu-id="42201-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="42201-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="42201-133">必需</span><span class="sxs-lookup"><span data-stu-id="42201-133">required</span></span>  <br/> |<span data-ttu-id="42201-134">元素在其父元素内的从零开始编制的索引。</span><span class="sxs-lookup"><span data-stu-id="42201-134">The zero-based index of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="42201-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="42201-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="42201-136">RGB</span><span class="sxs-lookup"><span data-stu-id="42201-136">RGB</span></span>  <br/> |<span data-ttu-id="42201-137">xsd：string</span><span class="sxs-lookup"><span data-stu-id="42201-137">xsd:string</span></span>  <br/> |<span data-ttu-id="42201-138">必需</span><span class="sxs-lookup"><span data-stu-id="42201-138">required</span></span>  <br/> |<span data-ttu-id="42201-139">颜色表条目的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="42201-139">The hexadecimal value of the color table entry.</span></span>  <br/> |<span data-ttu-id="42201-140">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="42201-140">Values of the xsd:string type.</span></span>  <br/> |
   

