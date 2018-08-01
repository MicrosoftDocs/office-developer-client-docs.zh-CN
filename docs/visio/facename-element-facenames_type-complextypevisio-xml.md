---
title: FaceName 元素 （FaceNames_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b1783f05-ced1-917f-8298-eca4ecfa3912
description: 包含有关字体的信息。
ms.openlocfilehash: 8a66d5294e239e4540939cc7053e1f67a777144d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780201"
---
# <a name="facename-element-facenamestype-complextype-visio-xml"></a><span data-ttu-id="ccbf0-103">FaceName 元素 （FaceNames_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ccbf0-103">FaceName element (FaceNames_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="ccbf0-104">包含有关字体的信息。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-104">Contains information about a font.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="ccbf0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ccbf0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ccbf0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ccbf0-107">FaceName_Type</span><span class="sxs-lookup"><span data-stu-id="ccbf0-107">FaceName_Type</span></span>](facename_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ccbf0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ccbf0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ccbf0-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="ccbf0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ccbf0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ccbf0-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="ccbf0-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ccbf0-113">定义</span><span class="sxs-lookup"><span data-stu-id="ccbf0-113">Definition</span></span>

```XML
< xs:element name="FaceName" type="FaceName_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element > 
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ccbf0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ccbf0-114">Elements and attributes</span></span>

<span data-ttu-id="ccbf0-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ccbf0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ccbf0-116">Parent elements</span></span>

|<span data-ttu-id="ccbf0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-117">**Element**</span></span>|<span data-ttu-id="ccbf0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-118">**Type**</span></span>|<span data-ttu-id="ccbf0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ccbf0-120">FaceNames</span><span class="sxs-lookup"><span data-stu-id="ccbf0-120">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ccbf0-121">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="ccbf0-121">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ccbf0-122">包含**FaceName**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-122">Contains a collection of **FaceName** elements.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="ccbf0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ccbf0-123">Child elements</span></span>

<span data-ttu-id="ccbf0-124">无。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ccbf0-125">属性</span><span class="sxs-lookup"><span data-stu-id="ccbf0-125">Attributes</span></span>

|<span data-ttu-id="ccbf0-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-126">**Attribute**</span></span>|<span data-ttu-id="ccbf0-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-127">**Type**</span></span>|<span data-ttu-id="ccbf0-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-128">**Required**</span></span>|<span data-ttu-id="ccbf0-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-129">**Description**</span></span>|<span data-ttu-id="ccbf0-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ccbf0-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ccbf0-131">CharSets</span><span class="sxs-lookup"><span data-stu-id="ccbf0-131">CharSets</span></span>  <br/> |<span data-ttu-id="ccbf0-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ccbf0-132">xsd:string</span></span>  <br/> |<span data-ttu-id="ccbf0-133">可选</span><span class="sxs-lookup"><span data-stu-id="ccbf0-133">optional</span></span>  <br/> |<span data-ttu-id="ccbf0-134">支持的字符的字体设置。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-134">The supported character sets of the font.</span></span>  <br/> |<span data-ttu-id="ccbf0-135">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ccbf0-136">Flags</span><span class="sxs-lookup"><span data-stu-id="ccbf0-136">Flags</span></span>  <br/> |<span data-ttu-id="ccbf0-137">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ccbf0-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ccbf0-138">可选</span><span class="sxs-lookup"><span data-stu-id="ccbf0-138">optional</span></span>  <br/> |<span data-ttu-id="ccbf0-139">这些标志指示以下： 缺少字体、 默认字体、 亚洲字体、 复杂的字体、 垂直字体和字体类型。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-139">Flags that indicate the following: missing font, default font, asian font, complex font, vertical font, and font type.</span></span>  <br/> |<span data-ttu-id="ccbf0-140">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ccbf0-141">NameU</span><span class="sxs-lookup"><span data-stu-id="ccbf0-141">NameU</span></span>  <br/> |<span data-ttu-id="ccbf0-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ccbf0-142">xsd:string</span></span>  <br/> |<span data-ttu-id="ccbf0-143">必需</span><span class="sxs-lookup"><span data-stu-id="ccbf0-143">required</span></span>  <br/> |<span data-ttu-id="ccbf0-144">为 utf-16 Unicode 字符串字体的名称。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-144">The name of the font as a UTF-16 Unicode string.</span></span>  <br/> ||
|<span data-ttu-id="ccbf0-145">Panos</span><span class="sxs-lookup"><span data-stu-id="ccbf0-145">Panos</span></span>  <br/> |<span data-ttu-id="ccbf0-146">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ccbf0-146">xsd:string</span></span>  <br/> |<span data-ttu-id="ccbf0-147">可选</span><span class="sxs-lookup"><span data-stu-id="ccbf0-147">optional</span></span>  <br/> |<span data-ttu-id="ccbf0-148">字体的 panose 签名。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-148">The panose signature for the font.</span></span> <span data-ttu-id="ccbf0-149">Panose 是对其根据其 visual 特征进行分类的分类系统的字体。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-149">Panose is a classification system for typefaces that categorizes them based upon their visual characteristics.</span></span>  <br/> |<span data-ttu-id="ccbf0-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ccbf0-151">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="ccbf0-151">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="ccbf0-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ccbf0-152">xsd:string</span></span>  <br/> |<span data-ttu-id="ccbf0-153">可选</span><span class="sxs-lookup"><span data-stu-id="ccbf0-153">optional</span></span>  <br/> |<span data-ttu-id="ccbf0-154">支持的 Unicode 范围的字体。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-154">The supported Unicode ranges of the font.</span></span>  <br/> |<span data-ttu-id="ccbf0-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ccbf0-155">Values of the xsd:string type.</span></span>  <br/> |
   

