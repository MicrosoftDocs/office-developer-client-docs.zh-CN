---
title: FaceName 元素 (FaceNames_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b1783f05-ced1-917f-8298-eca4ecfa3912
description: 包含有关字体的信息。
ms.openlocfilehash: 4c8f047d655be167dc058b3e29ac62161887ce99
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322601"
---
# <a name="facename-element-facenamestype-complextype-visio-xml"></a><span data-ttu-id="3dfa4-103">FaceName 元素 (FaceNames_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="3dfa4-103">FaceName element (FaceNames_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="3dfa4-104">包含有关字体的信息。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-104">Contains information about a font.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="3dfa4-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="3dfa4-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3dfa4-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-106">**Element type**</span></span> <br/> |[<span data-ttu-id="3dfa4-107">FaceName_Type</span><span class="sxs-lookup"><span data-stu-id="3dfa4-107">FaceName_Type</span></span>](facename_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="3dfa4-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="3dfa4-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-109">**Schema file**</span></span> <br/> |<span data-ttu-id="3dfa4-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="3dfa4-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="3dfa4-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-111">**Document parts**</span></span> <br/> |<span data-ttu-id="3dfa4-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="3dfa4-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3dfa4-113">定义</span><span class="sxs-lookup"><span data-stu-id="3dfa4-113">Definition</span></span>

```XML
< xs:element name="FaceName" type="FaceName_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element > 
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3dfa4-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3dfa4-114">Elements and attributes</span></span>

<span data-ttu-id="3dfa4-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="3dfa4-116">父元素</span><span class="sxs-lookup"><span data-stu-id="3dfa4-116">Parent elements</span></span>

|<span data-ttu-id="3dfa4-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-117">**Element**</span></span>|<span data-ttu-id="3dfa4-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-118">**Type**</span></span>|<span data-ttu-id="3dfa4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3dfa4-120">FaceNames</span><span class="sxs-lookup"><span data-stu-id="3dfa4-120">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3dfa4-121">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="3dfa4-121">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="3dfa4-122">包含**FaceName**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-122">Contains a collection of **FaceName** elements.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="3dfa4-123">子元素</span><span class="sxs-lookup"><span data-stu-id="3dfa4-123">Child elements</span></span>

<span data-ttu-id="3dfa4-124">无。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3dfa4-125">属性</span><span class="sxs-lookup"><span data-stu-id="3dfa4-125">Attributes</span></span>

|<span data-ttu-id="3dfa4-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-126">**Attribute**</span></span>|<span data-ttu-id="3dfa4-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-127">**Type**</span></span>|<span data-ttu-id="3dfa4-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-128">**Required**</span></span>|<span data-ttu-id="3dfa4-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-129">**Description**</span></span>|<span data-ttu-id="3dfa4-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3dfa4-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3dfa4-131">CharSets</span><span class="sxs-lookup"><span data-stu-id="3dfa4-131">CharSets</span></span>  <br/> |<span data-ttu-id="3dfa4-132">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3dfa4-132">xsd:string</span></span>  <br/> |<span data-ttu-id="3dfa4-133">可选</span><span class="sxs-lookup"><span data-stu-id="3dfa4-133">optional</span></span>  <br/> |<span data-ttu-id="3dfa4-134">受支持的字体字符集。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-134">The supported character sets of the font.</span></span>  <br/> |<span data-ttu-id="3dfa4-135">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-135">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="3dfa4-136">Flags</span><span class="sxs-lookup"><span data-stu-id="3dfa4-136">Flags</span></span>  <br/> |<span data-ttu-id="3dfa4-137">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3dfa4-137">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3dfa4-138">可选</span><span class="sxs-lookup"><span data-stu-id="3dfa4-138">optional</span></span>  <br/> |<span data-ttu-id="3dfa4-139">指示以下内容的标志: 缺少字体、默认字体、中文字体、复杂字体、垂直字体和字体类型。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-139">Flags that indicate the following: missing font, default font, asian font, complex font, vertical font, and font type.</span></span>  <br/> |<span data-ttu-id="3dfa4-140">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-140">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="3dfa4-141">NameU</span><span class="sxs-lookup"><span data-stu-id="3dfa4-141">NameU</span></span>  <br/> |<span data-ttu-id="3dfa4-142">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3dfa4-142">xsd:string</span></span>  <br/> |<span data-ttu-id="3dfa4-143">必需</span><span class="sxs-lookup"><span data-stu-id="3dfa4-143">required</span></span>  <br/> |<span data-ttu-id="3dfa4-144">UTF-16 Unicode 字符串形式的字体名称。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-144">The name of the font as a UTF-16 Unicode string.</span></span>  <br/> ||
|<span data-ttu-id="3dfa4-145">Panos</span><span class="sxs-lookup"><span data-stu-id="3dfa4-145">Panos</span></span>  <br/> |<span data-ttu-id="3dfa4-146">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3dfa4-146">xsd:string</span></span>  <br/> |<span data-ttu-id="3dfa4-147">可选</span><span class="sxs-lookup"><span data-stu-id="3dfa4-147">optional</span></span>  <br/> |<span data-ttu-id="3dfa4-148">字体的 panose 签名。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-148">The panose signature for the font.</span></span> <span data-ttu-id="3dfa4-149">Panose 是一个分类系统, 用于根据其视觉特征对它们进行分类。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-149">Panose is a classification system for typefaces that categorizes them based upon their visual characteristics.</span></span>  <br/> |<span data-ttu-id="3dfa4-150">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="3dfa4-151">UnicodeRanges</span><span class="sxs-lookup"><span data-stu-id="3dfa4-151">UnicodeRanges</span></span>  <br/> |<span data-ttu-id="3dfa4-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3dfa4-152">xsd:string</span></span>  <br/> |<span data-ttu-id="3dfa4-153">可选</span><span class="sxs-lookup"><span data-stu-id="3dfa4-153">optional</span></span>  <br/> |<span data-ttu-id="3dfa4-154">所支持的字体的 Unicode 范围。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-154">The supported Unicode ranges of the font.</span></span>  <br/> |<span data-ttu-id="3dfa4-155">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dfa4-155">Values of the xsd:string type.</span></span>  <br/> |
   

