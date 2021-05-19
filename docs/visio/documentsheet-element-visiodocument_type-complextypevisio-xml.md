---
title: 'DocumentSheet 元素 (VisioDocument_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b8673e1-b913-52db-2d1d-b3e8f4b8f952
description: 指定 DocumentSheet 结构。
ms.openlocfilehash: 279fca457163d5bcbdda885c11c589bfcde0baa9
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540040"
---
# <a name="documentsheet-element-visiodocument_type-complextype-visio-xml"></a><span data-ttu-id="c1562-103">DocumentSheet 元素 (VisioDocument_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="c1562-103">DocumentSheet element (VisioDocument_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="c1562-104">指定 DocumentSheet 结构。</span><span class="sxs-lookup"><span data-stu-id="c1562-104">Specifies a DocumentSheet structure.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="c1562-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="c1562-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c1562-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="c1562-106">**Element type**</span></span> <br/> |[<span data-ttu-id="c1562-107">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="c1562-107">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="c1562-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c1562-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="c1562-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c1562-109">**Schema file**</span></span> <br/> |<span data-ttu-id="c1562-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="c1562-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="c1562-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="c1562-111">**Document parts**</span></span> <br/> |<span data-ttu-id="c1562-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="c1562-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c1562-113">定义</span><span class="sxs-lookup"><span data-stu-id="c1562-113">Definition</span></span>

```XML
< xs:element name="DocumentSheet" type="DocumentSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c1562-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c1562-114">Elements and attributes</span></span>

<span data-ttu-id="c1562-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c1562-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="c1562-116">父元素</span><span class="sxs-lookup"><span data-stu-id="c1562-116">Parent elements</span></span>

|<span data-ttu-id="c1562-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="c1562-117">**Element**</span></span>|<span data-ttu-id="c1562-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="c1562-118">**Type**</span></span>|<span data-ttu-id="c1562-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1562-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c1562-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="c1562-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="c1562-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="c1562-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c1562-122">Microsoft 文档库Visio元素。</span><span class="sxs-lookup"><span data-stu-id="c1562-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="c1562-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c1562-123">Child elements</span></span>

|<span data-ttu-id="c1562-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="c1562-124">**Element**</span></span>|<span data-ttu-id="c1562-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="c1562-125">**Type**</span></span>|<span data-ttu-id="c1562-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1562-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c1562-127">Cell</span><span class="sxs-lookup"><span data-stu-id="c1562-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="c1562-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="c1562-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="c1562-129">指定 DocumentSheet 中的单元格。</span><span class="sxs-lookup"><span data-stu-id="c1562-129">Specifies a cell in a DocumentSheet.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="c1562-130">属性</span><span class="sxs-lookup"><span data-stu-id="c1562-130">Attributes</span></span>

|<span data-ttu-id="c1562-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="c1562-131">**Attribute**</span></span>|<span data-ttu-id="c1562-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="c1562-132">**Type**</span></span>|<span data-ttu-id="c1562-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="c1562-133">**Required**</span></span>|<span data-ttu-id="c1562-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="c1562-134">**Description**</span></span>|<span data-ttu-id="c1562-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c1562-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1562-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="c1562-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="c1562-137">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="c1562-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c1562-138">可选</span><span class="sxs-lookup"><span data-stu-id="c1562-138">optional</span></span>  <br/> |<span data-ttu-id="c1562-139">描述该名称是否已由用户自定义。</span><span class="sxs-lookup"><span data-stu-id="c1562-139">Describes whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="c1562-140">xsd：Boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c1562-140">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="c1562-141">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="c1562-141">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="c1562-142">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="c1562-142">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c1562-143">可选</span><span class="sxs-lookup"><span data-stu-id="c1562-143">optional</span></span>  <br/> |<span data-ttu-id="c1562-144">描述用户是否已自定义通用名称。</span><span class="sxs-lookup"><span data-stu-id="c1562-144">Describes whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="c1562-145">xsd：Boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c1562-145">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="c1562-146">名称</span><span class="sxs-lookup"><span data-stu-id="c1562-146">Name</span></span>  <br/> |<span data-ttu-id="c1562-147">xsd：string</span><span class="sxs-lookup"><span data-stu-id="c1562-147">xsd:string</span></span>  <br/> |<span data-ttu-id="c1562-148">可选</span><span class="sxs-lookup"><span data-stu-id="c1562-148">optional</span></span>  <br/> |<span data-ttu-id="c1562-149">指定 DocumentSheet 与语言相关的名称。</span><span class="sxs-lookup"><span data-stu-id="c1562-149">Specifies the language-dependent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="c1562-150">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c1562-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c1562-151">NameU</span><span class="sxs-lookup"><span data-stu-id="c1562-151">NameU</span></span>  <br/> |<span data-ttu-id="c1562-152">xsd：string</span><span class="sxs-lookup"><span data-stu-id="c1562-152">xsd:string</span></span>  <br/> |<span data-ttu-id="c1562-153">可选</span><span class="sxs-lookup"><span data-stu-id="c1562-153">optional</span></span>  <br/> |<span data-ttu-id="c1562-154">指定 DocumentSheet 的独立于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="c1562-154">Specifies the language- independent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="c1562-155">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c1562-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="c1562-156">UniqueID</span><span class="sxs-lookup"><span data-stu-id="c1562-156">UniqueID</span></span>  <br/> |<span data-ttu-id="c1562-157">xsd：string</span><span class="sxs-lookup"><span data-stu-id="c1562-157">xsd:string</span></span>  <br/> |<span data-ttu-id="c1562-158">可选</span><span class="sxs-lookup"><span data-stu-id="c1562-158">optional</span></span>  <br/> |<span data-ttu-id="c1562-159">可选属性，类型为 string。</span><span class="sxs-lookup"><span data-stu-id="c1562-159">Optional string.</span></span> <span data-ttu-id="c1562-160">GUID (标识形状) 全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c1562-160">A GUID (globally unique identifier) identifying the shape.</span></span>  <br/> |<span data-ttu-id="c1562-161">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c1562-161">Values of the xsd:string type.</span></span>  <br/> |
   

