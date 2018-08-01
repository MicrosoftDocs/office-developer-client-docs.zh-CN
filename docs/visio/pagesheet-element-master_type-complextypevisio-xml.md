---
title: PageSheet 元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定绘图页主控形状相关联的属性。
ms.openlocfilehash: ab20cfe4561cd5fd0eeb6edad0b3a608428b0e8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780877"
---
# <a name="pagesheet-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="57023-103">PageSheet 元素 （Master_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="57023-103">PageSheet element (Master_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="57023-104">指定绘图页主控形状相关联的属性。</span><span class="sxs-lookup"><span data-stu-id="57023-104">Specifies the properties of the drawing page associated with the master.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="57023-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="57023-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="57023-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="57023-106">**Element type**</span></span> <br/> |[<span data-ttu-id="57023-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="57023-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="57023-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="57023-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="57023-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="57023-109">**Schema file**</span></span> <br/> |<span data-ttu-id="57023-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="57023-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="57023-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="57023-111">**Document parts**</span></span> <br/> |<span data-ttu-id="57023-112">masters.xml</span><span class="sxs-lookup"><span data-stu-id="57023-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="57023-113">定义</span><span class="sxs-lookup"><span data-stu-id="57023-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="57023-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="57023-114">Elements and attributes</span></span>

<span data-ttu-id="57023-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="57023-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="57023-116">父元素</span><span class="sxs-lookup"><span data-stu-id="57023-116">Parent elements</span></span>

|<span data-ttu-id="57023-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="57023-117">**Element**</span></span>|<span data-ttu-id="57023-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="57023-118">**Type**</span></span>|<span data-ttu-id="57023-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="57023-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="57023-120">Master</span><span class="sxs-lookup"><span data-stu-id="57023-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="57023-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="57023-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="57023-122">指定与绘图中的主控形状。</span><span class="sxs-lookup"><span data-stu-id="57023-122">Specifies a master in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="57023-123">子元素</span><span class="sxs-lookup"><span data-stu-id="57023-123">Child elements</span></span>

<span data-ttu-id="57023-124">无。</span><span class="sxs-lookup"><span data-stu-id="57023-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="57023-125">属性</span><span class="sxs-lookup"><span data-stu-id="57023-125">Attributes</span></span>

|<span data-ttu-id="57023-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="57023-126">**Attribute**</span></span>|<span data-ttu-id="57023-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="57023-127">**Type**</span></span>|<span data-ttu-id="57023-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="57023-128">**Required**</span></span>|<span data-ttu-id="57023-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="57023-129">**Description**</span></span>|<span data-ttu-id="57023-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="57023-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57023-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="57023-131">FillStyle</span></span>  <br/> |<span data-ttu-id="57023-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="57023-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="57023-133">可选</span><span class="sxs-lookup"><span data-stu-id="57023-133">optional</span></span>  <br/> |<span data-ttu-id="57023-134">指定从中继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="57023-134">specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="57023-135">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="57023-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="57023-136">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57023-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="57023-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="57023-137">LineStyle</span></span>  <br/> |<span data-ttu-id="57023-138">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="57023-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="57023-139">可选</span><span class="sxs-lookup"><span data-stu-id="57023-139">optional</span></span>  <br/> |<span data-ttu-id="57023-140">指定从中继承线条格式样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="57023-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="57023-141">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="57023-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="57023-142">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57023-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="57023-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="57023-143">TextStyle</span></span>  <br/> |<span data-ttu-id="57023-144">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="57023-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="57023-145">可选</span><span class="sxs-lookup"><span data-stu-id="57023-145">optional</span></span>  <br/> |<span data-ttu-id="57023-146">指定从中继承文本格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="57023-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="57023-147">它必须与绘图中**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="57023-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="57023-148">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57023-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="57023-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="57023-149">UniqueID</span></span>  <br/> |<span data-ttu-id="57023-150">xsd: string</span><span class="sxs-lookup"><span data-stu-id="57023-150">xsd:string</span></span>  <br/> |<span data-ttu-id="57023-151">可选</span><span class="sxs-lookup"><span data-stu-id="57023-151">optional</span></span>  <br/> |<span data-ttu-id="57023-152">其父元素中的元素的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="57023-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="57023-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="57023-153">Values of the xsd:string type.</span></span>  <br/> |
   

