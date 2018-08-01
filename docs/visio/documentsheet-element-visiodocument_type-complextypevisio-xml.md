---
title: DocumentSheet 元素 （VisioDocument_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9b8673e1-b913-52db-2d1d-b3e8f4b8f952
description: 指定的 DocumentSheet 结构。
ms.openlocfilehash: 50332759ff3bbe94887371d48c4a2e729243fb32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780144"
---
# <a name="documentsheet-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="a9220-103">DocumentSheet 元素 （VisioDocument_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="a9220-103">DocumentSheet element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="a9220-104">指定的 DocumentSheet 结构。</span><span class="sxs-lookup"><span data-stu-id="a9220-104">Specifies a DocumentSheet structure.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="a9220-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="a9220-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a9220-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="a9220-106">**Element type**</span></span> <br/> |[<span data-ttu-id="a9220-107">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="a9220-107">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="a9220-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a9220-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="a9220-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a9220-109">**Schema file**</span></span> <br/> |<span data-ttu-id="a9220-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="a9220-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="a9220-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="a9220-111">**Document parts**</span></span> <br/> |<span data-ttu-id="a9220-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="a9220-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a9220-113">定义</span><span class="sxs-lookup"><span data-stu-id="a9220-113">Definition</span></span>

```XML
< xs:element name="DocumentSheet" type="DocumentSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a9220-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a9220-114">Elements and attributes</span></span>

<span data-ttu-id="a9220-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a9220-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="a9220-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a9220-116">Parent elements</span></span>

|<span data-ttu-id="a9220-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="a9220-117">**Element**</span></span>|<span data-ttu-id="a9220-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9220-118">**Type**</span></span>|<span data-ttu-id="a9220-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9220-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a9220-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="a9220-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="a9220-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="a9220-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a9220-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="a9220-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="a9220-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a9220-123">Child elements</span></span>

|<span data-ttu-id="a9220-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="a9220-124">**Element**</span></span>|<span data-ttu-id="a9220-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9220-125">**Type**</span></span>|<span data-ttu-id="a9220-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9220-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a9220-127">Cell</span><span class="sxs-lookup"><span data-stu-id="a9220-127">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="a9220-128">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="a9220-128">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a9220-129">指定单元格 DocumentSheet。</span><span class="sxs-lookup"><span data-stu-id="a9220-129">Specifies a cell in a DocumentSheet.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="a9220-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="a9220-130">Attributes</span></span>

|<span data-ttu-id="a9220-131">**属性**</span><span class="sxs-lookup"><span data-stu-id="a9220-131">**Attribute**</span></span>|<span data-ttu-id="a9220-132">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9220-132">**Type**</span></span>|<span data-ttu-id="a9220-133">**必需**</span><span class="sxs-lookup"><span data-stu-id="a9220-133">**Required**</span></span>|<span data-ttu-id="a9220-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9220-134">**Description**</span></span>|<span data-ttu-id="a9220-135">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a9220-135">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9220-136">IsCustomName</span><span class="sxs-lookup"><span data-stu-id="a9220-136">IsCustomName</span></span>  <br/> |<span data-ttu-id="a9220-137">化</span><span class="sxs-lookup"><span data-stu-id="a9220-137">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a9220-138">可选</span><span class="sxs-lookup"><span data-stu-id="a9220-138">optional</span></span>  <br/> |<span data-ttu-id="a9220-139">描述是否由用户自定义名称。</span><span class="sxs-lookup"><span data-stu-id="a9220-139">Describes whether the name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="a9220-140">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9220-140">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="a9220-141">IsCustomNameU</span><span class="sxs-lookup"><span data-stu-id="a9220-141">IsCustomNameU</span></span>  <br/> |<span data-ttu-id="a9220-142">化</span><span class="sxs-lookup"><span data-stu-id="a9220-142">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a9220-143">可选</span><span class="sxs-lookup"><span data-stu-id="a9220-143">optional</span></span>  <br/> |<span data-ttu-id="a9220-144">描述是否由用户自定义的通用名称。</span><span class="sxs-lookup"><span data-stu-id="a9220-144">Describes whether the universal name has been customized by the user.</span></span>  <br/> |<span data-ttu-id="a9220-145">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9220-145">Values of the xsd:Boolean type.</span></span>  <br/> |
|<span data-ttu-id="a9220-146">名称</span><span class="sxs-lookup"><span data-stu-id="a9220-146">Name</span></span>  <br/> |<span data-ttu-id="a9220-147">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a9220-147">xsd:string</span></span>  <br/> |<span data-ttu-id="a9220-148">可选</span><span class="sxs-lookup"><span data-stu-id="a9220-148">optional</span></span>  <br/> |<span data-ttu-id="a9220-149">指定的 DocumentSheet 依赖于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="a9220-149">Specifies the language-dependent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="a9220-150">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9220-150">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a9220-151">NameU</span><span class="sxs-lookup"><span data-stu-id="a9220-151">NameU</span></span>  <br/> |<span data-ttu-id="a9220-152">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a9220-152">xsd:string</span></span>  <br/> |<span data-ttu-id="a9220-153">可选</span><span class="sxs-lookup"><span data-stu-id="a9220-153">optional</span></span>  <br/> |<span data-ttu-id="a9220-154">指定的 DocumentSheet 独立于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="a9220-154">Specifies the language- independent name of the DocumentSheet.</span></span>  <br/> |<span data-ttu-id="a9220-155">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9220-155">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a9220-156">UniqueID</span><span class="sxs-lookup"><span data-stu-id="a9220-156">UniqueID</span></span>  <br/> |<span data-ttu-id="a9220-157">xsd: string</span><span class="sxs-lookup"><span data-stu-id="a9220-157">xsd:string</span></span>  <br/> |<span data-ttu-id="a9220-158">可选</span><span class="sxs-lookup"><span data-stu-id="a9220-158">optional</span></span>  <br/> |<span data-ttu-id="a9220-159">可选属性，类型为 string。</span><span class="sxs-lookup"><span data-stu-id="a9220-159">Optional string.</span></span> <span data-ttu-id="a9220-160">标识形状 GUID （全局唯一标识符）。</span><span class="sxs-lookup"><span data-stu-id="a9220-160">A GUID (globally unique identifier) identifying the shape.</span></span>  <br/> |<span data-ttu-id="a9220-161">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9220-161">Values of the xsd:string type.</span></span>  <br/> |
   

