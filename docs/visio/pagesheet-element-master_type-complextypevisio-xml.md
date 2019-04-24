---
title: PageSheet 元素 (Master_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定与主控形状相关联的绘图页的属性。
ms.openlocfilehash: 579b2b4f02c79a38842a150b8757329e19e7bb3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361122"
---
# <a name="pagesheet-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="67dda-103">PageSheet 元素 (Master_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="67dda-103">PageSheet element (Master_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="67dda-104">指定与主控形状相关联的绘图页的属性。</span><span class="sxs-lookup"><span data-stu-id="67dda-104">Specifies the properties of the drawing page associated with the master.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="67dda-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="67dda-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="67dda-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="67dda-106">**Element type**</span></span> <br/> |[<span data-ttu-id="67dda-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="67dda-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="67dda-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="67dda-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="67dda-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="67dda-109">**Schema file**</span></span> <br/> |<span data-ttu-id="67dda-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="67dda-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="67dda-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="67dda-111">**Document parts**</span></span> <br/> |<span data-ttu-id="67dda-112">主控 xml</span><span class="sxs-lookup"><span data-stu-id="67dda-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="67dda-113">定义</span><span class="sxs-lookup"><span data-stu-id="67dda-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="67dda-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="67dda-114">Elements and attributes</span></span>

<span data-ttu-id="67dda-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="67dda-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="67dda-116">父元素</span><span class="sxs-lookup"><span data-stu-id="67dda-116">Parent elements</span></span>

|<span data-ttu-id="67dda-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="67dda-117">**Element**</span></span>|<span data-ttu-id="67dda-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="67dda-118">**Type**</span></span>|<span data-ttu-id="67dda-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="67dda-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="67dda-120">Master</span><span class="sxs-lookup"><span data-stu-id="67dda-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="67dda-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="67dda-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="67dda-122">指定绘图中的主控形状。</span><span class="sxs-lookup"><span data-stu-id="67dda-122">Specifies a master in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="67dda-123">子元素</span><span class="sxs-lookup"><span data-stu-id="67dda-123">Child elements</span></span>

<span data-ttu-id="67dda-124">无。</span><span class="sxs-lookup"><span data-stu-id="67dda-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="67dda-125">属性</span><span class="sxs-lookup"><span data-stu-id="67dda-125">Attributes</span></span>

|<span data-ttu-id="67dda-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="67dda-126">**Attribute**</span></span>|<span data-ttu-id="67dda-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="67dda-127">**Type**</span></span>|<span data-ttu-id="67dda-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="67dda-128">**Required**</span></span>|<span data-ttu-id="67dda-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="67dda-129">**Description**</span></span>|<span data-ttu-id="67dda-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="67dda-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="67dda-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="67dda-131">FillStyle</span></span>  <br/> |<span data-ttu-id="67dda-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="67dda-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="67dda-133">可选</span><span class="sxs-lookup"><span data-stu-id="67dda-133">optional</span></span>  <br/> |<span data-ttu-id="67dda-134">指定要从中继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="67dda-134">specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="67dda-135">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="67dda-136">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="67dda-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="67dda-137">LineStyle</span></span>  <br/> |<span data-ttu-id="67dda-138">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="67dda-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="67dda-139">可选</span><span class="sxs-lookup"><span data-stu-id="67dda-139">optional</span></span>  <br/> |<span data-ttu-id="67dda-140">指定要从中继承行格式设置的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="67dda-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="67dda-141">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="67dda-142">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="67dda-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="67dda-143">TextStyle</span></span>  <br/> |<span data-ttu-id="67dda-144">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="67dda-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="67dda-145">可选</span><span class="sxs-lookup"><span data-stu-id="67dda-145">optional</span></span>  <br/> |<span data-ttu-id="67dda-146">指定要从中继承文本格式设置的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="67dda-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="67dda-147">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="67dda-148">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="67dda-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="67dda-149">UniqueID</span></span>  <br/> |<span data-ttu-id="67dda-150">xsd: string</span><span class="sxs-lookup"><span data-stu-id="67dda-150">xsd:string</span></span>  <br/> |<span data-ttu-id="67dda-151">可选</span><span class="sxs-lookup"><span data-stu-id="67dda-151">optional</span></span>  <br/> |<span data-ttu-id="67dda-152">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="67dda-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="67dda-153">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="67dda-153">Values of the xsd:string type.</span></span>  <br/> |
   

