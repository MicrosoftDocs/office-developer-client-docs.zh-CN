---
title: DocumentSheet 元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b8673e1-b913-52db-2d1d-b3e8f4b8f952
description: 指定 DocumentSheet 结构。
ms.openlocfilehash: a2594e0325cc2743036a03998eb7ac71ed2183c8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356362"
---
# <a name="documentsheet-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="15f6d-103">DocumentSheet 元素 (VisioDocument_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="15f6d-103">DocumentSheet element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="15f6d-104">指定 DocumentSheet 结构。</span><span class="sxs-lookup"><span data-stu-id="15f6d-104">Specifies a DocumentSheet structure.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="15f6d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="15f6d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="15f6d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="15f6d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="15f6d-107">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="15f6d-107">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="15f6d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="15f6d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="15f6d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="15f6d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="15f6d-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="15f6d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="15f6d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="15f6d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="15f6d-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="15f6d-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="15f6d-113">定义</span><span class="sxs-lookup"><span data-stu-id="15f6d-113">Definition</span></span>

```XML
< xs:element name="DocumentSheet" type="DocumentSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="15f6d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="15f6d-114">Elements and attributes</span></span>

<span data-ttu-id="15f6d-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="15f6d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="15f6d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="15f6d-116">Parent elements</span></span>

|<span data-ttu-id="15f6d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="15f6d-117">**Element**</span></span>|<span data-ttu-id="15f6d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="15f6d-118">**Type**</span></span>|<span data-ttu-id="15f6d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="15f6d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="15f6d-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="15f6d-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="15f6d-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="15f6d-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="15f6d-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="15f6d-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="15f6d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="15f6d-123">Child elements</span></span>

|<span data-ttu-id="15f6d-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="15f6d-124">**Element**</span></span>|<span data-ttu-id="15f6d-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="15f6d-125">**Type**</span></span>|<span data-ttu-id="15f6d-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="15f6d-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="15f6d-127">Cell</span><span class="sxs-lookup"><span data-stu-id="15f6d-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="15f6d-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="15f6d-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="15f6d-129">指定 DocumentSheet 中的单元格。</span><span class="sxs-lookup"><span data-stu-id="15f6d-129">Specifies a cell in a DocumentSheet.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="15f6d-130">属性</span><span class="sxs-lookup"><span data-stu-id="15f6d-130">Attributes</span></span>

|<span data-ttu-id="15f6d-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="15f6d-131">**Attribute**</span></span>|<span data-ttu-id="15f6d-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="15f6d-132">**Type**</span></span>|<span data-ttu-id="15f6d-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="15f6d-133">**Required**</span></span>|<span data-ttu-id="15f6d-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="15f6d-134">**Description**</span></span>|<span data-ttu-id="15f6d-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="15f6d-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15f6d-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="15f6d-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="15f6d-137">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="15f6d-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="15f6d-138">可选</span><span class="sxs-lookup"><span data-stu-id="15f6d-138">optional</span></span>  <br/> |<span data-ttu-id="15f6d-139">描述该名称是否已由用户自定义。</span><span class="sxs-lookup"><span data-stu-id="15f6d-139">Describes whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="15f6d-140">xsd: Boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15f6d-140">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="15f6d-141">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="15f6d-141">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="15f6d-142">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="15f6d-142">xsd:boolean</span></span>  <br/> |<span data-ttu-id="15f6d-143">可选</span><span class="sxs-lookup"><span data-stu-id="15f6d-143">optional</span></span>  <br/> |<span data-ttu-id="15f6d-144">描述通用名称是否已由用户自定义。</span><span class="sxs-lookup"><span data-stu-id="15f6d-144">Describes whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="15f6d-145">xsd: Boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15f6d-145">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="15f6d-146">名称</span><span class="sxs-lookup"><span data-stu-id="15f6d-146">Name</span></span>  <br/> |<span data-ttu-id="15f6d-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="15f6d-147">xsd:string</span></span>  <br/> |<span data-ttu-id="15f6d-148">可选</span><span class="sxs-lookup"><span data-stu-id="15f6d-148">optional</span></span>  <br/> |<span data-ttu-id="15f6d-149">指定 DocumentSheet 的与语言相关的名称。</span><span class="sxs-lookup"><span data-stu-id="15f6d-149">Specifies the language-dependent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="15f6d-150">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15f6d-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="15f6d-151">NameU</span><span class="sxs-lookup"><span data-stu-id="15f6d-151">NameU</span></span>  <br/> |<span data-ttu-id="15f6d-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="15f6d-152">xsd:string</span></span>  <br/> |<span data-ttu-id="15f6d-153">可选</span><span class="sxs-lookup"><span data-stu-id="15f6d-153">optional</span></span>  <br/> |<span data-ttu-id="15f6d-154">指定 DocumentSheet 的独立于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="15f6d-154">Specifies the language- independent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="15f6d-155">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15f6d-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="15f6d-156">UniqueID</span><span class="sxs-lookup"><span data-stu-id="15f6d-156">UniqueID</span></span>  <br/> |<span data-ttu-id="15f6d-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="15f6d-157">xsd:string</span></span>  <br/> |<span data-ttu-id="15f6d-158">可选</span><span class="sxs-lookup"><span data-stu-id="15f6d-158">optional</span></span>  <br/> |<span data-ttu-id="15f6d-159">可选属性，类型为 string。</span><span class="sxs-lookup"><span data-stu-id="15f6d-159">Optional string.</span></span> <span data-ttu-id="15f6d-160">标识形状的 GUID (全局唯一标识符)。</span><span class="sxs-lookup"><span data-stu-id="15f6d-160">A GUID (globally unique identifier) identifying the shape.</span></span>  <br/> |<span data-ttu-id="15f6d-161">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="15f6d-161">Values of the xsd:string type.</span></span>  <br/> |
   

