---
title: PageSheet 元素 （Page_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 99a6549b-099b-1546-cc30-db0010fe3ce1
description: 指定绘图页在绘图页相关联的属性。
ms.openlocfilehash: 8b60795c02717e4b752c09af19fa932f87924d1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395131"
---
# <a name="pagesheet-element-pagetype-complextype-visio-xml"></a><span data-ttu-id="5f8de-103">PageSheet 元素 （Page_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="5f8de-103">PageSheet element (Page_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="5f8de-104">指定绘图页在绘图页相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="5f8de-104">Specifies the properties of the drawing page associated with the drawing page.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="5f8de-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="5f8de-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f8de-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="5f8de-106">**Element type**</span></span> <br/> |[<span data-ttu-id="5f8de-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="5f8de-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="5f8de-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5f8de-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="5f8de-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5f8de-109">**Schema file**</span></span> <br/> |<span data-ttu-id="5f8de-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="5f8de-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="5f8de-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="5f8de-111">**Document parts**</span></span> <br/> |<span data-ttu-id="5f8de-112">pages.xml</span><span class="sxs-lookup"><span data-stu-id="5f8de-112">pages.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5f8de-113">定义</span><span class="sxs-lookup"><span data-stu-id="5f8de-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element > 
```

## <a name="elements-and-attributes"></a><span data-ttu-id="5f8de-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5f8de-114">Elements and attributes</span></span>

<span data-ttu-id="5f8de-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5f8de-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="5f8de-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5f8de-116">Parent elements</span></span>

|<span data-ttu-id="5f8de-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="5f8de-117">**Element**</span></span>|<span data-ttu-id="5f8de-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f8de-118">**Type**</span></span>|<span data-ttu-id="5f8de-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f8de-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5f8de-120">网页</span><span class="sxs-lookup"><span data-stu-id="5f8de-120">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5f8de-121">Page_Type</span><span class="sxs-lookup"><span data-stu-id="5f8de-121">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="5f8de-122">包含文档中定义的网页的元素。</span><span class="sxs-lookup"><span data-stu-id="5f8de-122">Contains elements that define a page in the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="5f8de-123">子元素</span><span class="sxs-lookup"><span data-stu-id="5f8de-123">Child elements</span></span>

<span data-ttu-id="5f8de-124">无。</span><span class="sxs-lookup"><span data-stu-id="5f8de-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="5f8de-125">属性</span><span class="sxs-lookup"><span data-stu-id="5f8de-125">Attributes</span></span>

|<span data-ttu-id="5f8de-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="5f8de-126">**Attribute**</span></span>|<span data-ttu-id="5f8de-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="5f8de-127">**Type**</span></span>|<span data-ttu-id="5f8de-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="5f8de-128">**Required**</span></span>|<span data-ttu-id="5f8de-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="5f8de-129">**Description**</span></span>|<span data-ttu-id="5f8de-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5f8de-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f8de-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="5f8de-131">FillStyle</span></span>  <br/> |<span data-ttu-id="5f8de-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5f8de-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5f8de-133">可选</span><span class="sxs-lookup"><span data-stu-id="5f8de-133">optional</span></span>  <br/> |<span data-ttu-id="5f8de-134">指定从中继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="5f8de-134">Specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="5f8de-135">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="5f8de-136">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5f8de-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="5f8de-137">LineStyle</span></span>  <br/> |<span data-ttu-id="5f8de-138">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5f8de-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5f8de-139">可选</span><span class="sxs-lookup"><span data-stu-id="5f8de-139">optional</span></span>  <br/> |<span data-ttu-id="5f8de-140">指定从中继承线条格式样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="5f8de-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="5f8de-141">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="5f8de-142">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5f8de-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="5f8de-143">TextStyle</span></span>  <br/> |<span data-ttu-id="5f8de-144">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5f8de-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5f8de-145">可选</span><span class="sxs-lookup"><span data-stu-id="5f8de-145">optional</span></span>  <br/> |<span data-ttu-id="5f8de-146">指定从中继承文本格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="5f8de-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="5f8de-147">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="5f8de-148">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="5f8de-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="5f8de-149">UniqueID</span></span>  <br/> |<span data-ttu-id="5f8de-150">xsd: string</span><span class="sxs-lookup"><span data-stu-id="5f8de-150">xsd:string</span></span>  <br/> |<span data-ttu-id="5f8de-151">可选</span><span class="sxs-lookup"><span data-stu-id="5f8de-151">optional</span></span>  <br/> |<span data-ttu-id="5f8de-152">其父元素中的元素的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="5f8de-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="5f8de-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5f8de-153">Values of the xsd:string type.</span></span>  <br/> |
   

