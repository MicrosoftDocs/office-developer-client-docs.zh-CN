---
title: 'PageSheet 元素 (Page_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 99a6549b-099b-1546-cc30-db0010fe3ce1
description: 指定与绘图页关联的绘图页的属性。
ms.openlocfilehash: 2f49d152a0fcb30e3f5aea98cdc251d3b65b8f69
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540621"
---
# <a name="pagesheet-element-page_type-complextype-visio-xml"></a><span data-ttu-id="8a059-103">PageSheet 元素 (Page_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="8a059-103">PageSheet element (Page_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="8a059-104">指定与绘图页关联的绘图页的属性。</span><span class="sxs-lookup"><span data-stu-id="8a059-104">Specifies the properties of the drawing page associated with the drawing page.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8a059-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8a059-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8a059-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8a059-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8a059-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="8a059-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8a059-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8a059-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8a059-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8a059-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8a059-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="8a059-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8a059-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8a059-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8a059-112">pages.xml</span><span class="sxs-lookup"><span data-stu-id="8a059-112">pages.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8a059-113">定义</span><span class="sxs-lookup"><span data-stu-id="8a059-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element > 
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8a059-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8a059-114">Elements and attributes</span></span>

<span data-ttu-id="8a059-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8a059-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8a059-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8a059-116">Parent elements</span></span>

|<span data-ttu-id="8a059-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8a059-117">**Element**</span></span>|<span data-ttu-id="8a059-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8a059-118">**Type**</span></span>|<span data-ttu-id="8a059-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8a059-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8a059-120">Page</span><span class="sxs-lookup"><span data-stu-id="8a059-120">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8a059-121">Page_Type</span><span class="sxs-lookup"><span data-stu-id="8a059-121">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8a059-122">包含定义文档中页面的元素。</span><span class="sxs-lookup"><span data-stu-id="8a059-122">Contains elements that define a page in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8a059-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8a059-123">Child elements</span></span>

<span data-ttu-id="8a059-124">无。</span><span class="sxs-lookup"><span data-stu-id="8a059-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8a059-125">属性</span><span class="sxs-lookup"><span data-stu-id="8a059-125">Attributes</span></span>

|<span data-ttu-id="8a059-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="8a059-126">**Attribute**</span></span>|<span data-ttu-id="8a059-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="8a059-127">**Type**</span></span>|<span data-ttu-id="8a059-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="8a059-128">**Required**</span></span>|<span data-ttu-id="8a059-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="8a059-129">**Description**</span></span>|<span data-ttu-id="8a059-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8a059-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8a059-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="8a059-131">FillStyle</span></span>  <br/> |<span data-ttu-id="8a059-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8a059-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8a059-133">可选</span><span class="sxs-lookup"><span data-stu-id="8a059-133">optional</span></span>  <br/> |<span data-ttu-id="8a059-134">指定从其继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8a059-134">Specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="8a059-135">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8a059-136">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8a059-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="8a059-137">LineStyle</span></span>  <br/> |<span data-ttu-id="8a059-138">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8a059-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8a059-139">可选</span><span class="sxs-lookup"><span data-stu-id="8a059-139">optional</span></span>  <br/> |<span data-ttu-id="8a059-140">指定要从其继承线条格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8a059-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="8a059-141">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8a059-142">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8a059-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="8a059-143">TextStyle</span></span>  <br/> |<span data-ttu-id="8a059-144">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8a059-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8a059-145">可选</span><span class="sxs-lookup"><span data-stu-id="8a059-145">optional</span></span>  <br/> |<span data-ttu-id="8a059-146">指定要从其继承文本格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8a059-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="8a059-147">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8a059-148">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8a059-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="8a059-149">UniqueID</span></span>  <br/> |<span data-ttu-id="8a059-150">xsd：string</span><span class="sxs-lookup"><span data-stu-id="8a059-150">xsd:string</span></span>  <br/> |<span data-ttu-id="8a059-151">可选</span><span class="sxs-lookup"><span data-stu-id="8a059-151">optional</span></span>  <br/> |<span data-ttu-id="8a059-152">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8a059-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="8a059-153">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8a059-153">Values of the xsd:string type.</span></span>  <br/> |
   

