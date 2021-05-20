---
title: '使用 XML (Master_Type complexType)  (Visio PageSheet) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定与主控板关联的绘图页的属性。
ms.openlocfilehash: 94fde64b130c2a05c4bd70c97552fe4218171ce7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540614"
---
# <a name="pagesheet-element-master_type-complextype-visio-xml"></a><span data-ttu-id="515ce-103">使用 XML (Master_Type complexType)  (Visio PageSheet) </span><span class="sxs-lookup"><span data-stu-id="515ce-103">PageSheet element (Master_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="515ce-104">指定与主控板关联的绘图页的属性。</span><span class="sxs-lookup"><span data-stu-id="515ce-104">Specifies the properties of the drawing page associated with the master.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="515ce-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="515ce-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="515ce-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="515ce-106">**Element type**</span></span> <br/> |[<span data-ttu-id="515ce-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="515ce-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="515ce-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="515ce-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="515ce-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="515ce-109">**Schema file**</span></span> <br/> |<span data-ttu-id="515ce-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="515ce-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="515ce-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="515ce-111">**Document parts**</span></span> <br/> |<span data-ttu-id="515ce-112">masters.xml</span><span class="sxs-lookup"><span data-stu-id="515ce-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="515ce-113">定义</span><span class="sxs-lookup"><span data-stu-id="515ce-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="515ce-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="515ce-114">Elements and attributes</span></span>

<span data-ttu-id="515ce-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="515ce-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="515ce-116">父元素</span><span class="sxs-lookup"><span data-stu-id="515ce-116">Parent elements</span></span>

|<span data-ttu-id="515ce-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="515ce-117">**Element**</span></span>|<span data-ttu-id="515ce-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="515ce-118">**Type**</span></span>|<span data-ttu-id="515ce-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="515ce-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="515ce-120">Master</span><span class="sxs-lookup"><span data-stu-id="515ce-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="515ce-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="515ce-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="515ce-122">指定绘图中的主控图形。</span><span class="sxs-lookup"><span data-stu-id="515ce-122">Specifies a master in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="515ce-123">子元素</span><span class="sxs-lookup"><span data-stu-id="515ce-123">Child elements</span></span>

<span data-ttu-id="515ce-124">无。</span><span class="sxs-lookup"><span data-stu-id="515ce-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="515ce-125">属性</span><span class="sxs-lookup"><span data-stu-id="515ce-125">Attributes</span></span>

|<span data-ttu-id="515ce-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="515ce-126">**Attribute**</span></span>|<span data-ttu-id="515ce-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="515ce-127">**Type**</span></span>|<span data-ttu-id="515ce-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="515ce-128">**Required**</span></span>|<span data-ttu-id="515ce-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="515ce-129">**Description**</span></span>|<span data-ttu-id="515ce-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="515ce-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="515ce-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="515ce-131">FillStyle</span></span>  <br/> |<span data-ttu-id="515ce-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="515ce-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="515ce-133">可选</span><span class="sxs-lookup"><span data-stu-id="515ce-133">optional</span></span>  <br/> |<span data-ttu-id="515ce-134">指定从其继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="515ce-134">specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="515ce-135">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="515ce-136">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="515ce-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="515ce-137">LineStyle</span></span>  <br/> |<span data-ttu-id="515ce-138">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="515ce-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="515ce-139">可选</span><span class="sxs-lookup"><span data-stu-id="515ce-139">optional</span></span>  <br/> |<span data-ttu-id="515ce-140">指定要从其继承线条格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="515ce-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="515ce-141">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="515ce-142">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="515ce-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="515ce-143">TextStyle</span></span>  <br/> |<span data-ttu-id="515ce-144">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="515ce-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="515ce-145">可选</span><span class="sxs-lookup"><span data-stu-id="515ce-145">optional</span></span>  <br/> |<span data-ttu-id="515ce-146">指定要从其继承文本格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="515ce-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="515ce-147">它必须是与绘图中的属性关联的 **ID** **StyleSheet_Type** 的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="515ce-148">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="515ce-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="515ce-149">UniqueID</span></span>  <br/> |<span data-ttu-id="515ce-150">xsd：string</span><span class="sxs-lookup"><span data-stu-id="515ce-150">xsd:string</span></span>  <br/> |<span data-ttu-id="515ce-151">可选</span><span class="sxs-lookup"><span data-stu-id="515ce-151">optional</span></span>  <br/> |<span data-ttu-id="515ce-152">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="515ce-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="515ce-153">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="515ce-153">Values of the xsd:string type.</span></span>  <br/> |
   

