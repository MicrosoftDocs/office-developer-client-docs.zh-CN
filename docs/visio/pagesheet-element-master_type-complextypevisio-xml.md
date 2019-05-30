---
title: PageSheet 元素 (Master_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 824fbeb0-1a2f-35a0-50e3-c57143dc21ab
description: 指定与主控形状相关联的绘图页的属性。
ms.openlocfilehash: 94fde64b130c2a05c4bd70c97552fe4218171ce7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540614"
---
# <a name="pagesheet-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="8ae8a-103">PageSheet 元素 (Master_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8ae8a-103">PageSheet element (Master_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="8ae8a-104">指定与主控形状相关联的绘图页的属性。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-104">Specifies the properties of the drawing page associated with the master.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="8ae8a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="8ae8a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8ae8a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="8ae8a-107">PageSheet_Type</span><span class="sxs-lookup"><span data-stu-id="8ae8a-107">PageSheet_Type</span></span>](pagesheet_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="8ae8a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="8ae8a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="8ae8a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="8ae8a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="8ae8a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="8ae8a-112">主控 xml</span><span class="sxs-lookup"><span data-stu-id="8ae8a-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8ae8a-113">定义</span><span class="sxs-lookup"><span data-stu-id="8ae8a-113">Definition</span></span>

```XML
< xs:element name="PageSheet" type="PageSheet_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8ae8a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8ae8a-114">Elements and attributes</span></span>

<span data-ttu-id="8ae8a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="8ae8a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8ae8a-116">Parent elements</span></span>

|<span data-ttu-id="8ae8a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-117">**Element**</span></span>|<span data-ttu-id="8ae8a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-118">**Type**</span></span>|<span data-ttu-id="8ae8a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8ae8a-120">Master</span><span class="sxs-lookup"><span data-stu-id="8ae8a-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8ae8a-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="8ae8a-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="8ae8a-122">指定绘图中的主控形状。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-122">Specifies a master in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="8ae8a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="8ae8a-123">Child elements</span></span>

<span data-ttu-id="8ae8a-124">无。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8ae8a-125">属性</span><span class="sxs-lookup"><span data-stu-id="8ae8a-125">Attributes</span></span>

|<span data-ttu-id="8ae8a-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-126">**Attribute**</span></span>|<span data-ttu-id="8ae8a-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-127">**Type**</span></span>|<span data-ttu-id="8ae8a-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-128">**Required**</span></span>|<span data-ttu-id="8ae8a-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-129">**Description**</span></span>|<span data-ttu-id="8ae8a-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8ae8a-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ae8a-131">FillStyle</span><span class="sxs-lookup"><span data-stu-id="8ae8a-131">FillStyle</span></span>  <br/> |<span data-ttu-id="8ae8a-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8ae8a-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8ae8a-133">可选</span><span class="sxs-lookup"><span data-stu-id="8ae8a-133">optional</span></span>  <br/> |<span data-ttu-id="8ae8a-134">指定要从中继承填充格式的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-134">specifies the ID of the style sheet from which to inherit fill formatting.</span></span> <span data-ttu-id="8ae8a-135">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-135">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8ae8a-136">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-136">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8ae8a-137">LineStyle</span><span class="sxs-lookup"><span data-stu-id="8ae8a-137">LineStyle</span></span>  <br/> |<span data-ttu-id="8ae8a-138">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8ae8a-138">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8ae8a-139">可选</span><span class="sxs-lookup"><span data-stu-id="8ae8a-139">optional</span></span>  <br/> |<span data-ttu-id="8ae8a-140">指定要从中继承行格式设置的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-140">Specifies the ID of the style sheet from which to inherit line formatting.</span></span> <span data-ttu-id="8ae8a-141">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-141">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8ae8a-142">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-142">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8ae8a-143">TextStyle</span><span class="sxs-lookup"><span data-stu-id="8ae8a-143">TextStyle</span></span>  <br/> |<span data-ttu-id="8ae8a-144">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8ae8a-144">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8ae8a-145">可选</span><span class="sxs-lookup"><span data-stu-id="8ae8a-145">optional</span></span>  <br/> |<span data-ttu-id="8ae8a-146">指定要从中继承文本格式设置的样式表的 ID。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-146">Specifies the ID of the style sheet from which to inherit text formatting.</span></span> <span data-ttu-id="8ae8a-147">它必须是与绘图中的**StyleSheet_Type**相关联的**ID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-147">It MUST be the value of the **ID** attribute associated with a **StyleSheet_Type** in the drawing.</span></span>  <br/> |<span data-ttu-id="8ae8a-148">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-148">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="8ae8a-149">UniqueID</span><span class="sxs-lookup"><span data-stu-id="8ae8a-149">UniqueID</span></span>  <br/> |<span data-ttu-id="8ae8a-150">xsd: string</span><span class="sxs-lookup"><span data-stu-id="8ae8a-150">xsd:string</span></span>  <br/> |<span data-ttu-id="8ae8a-151">可选</span><span class="sxs-lookup"><span data-stu-id="8ae8a-151">optional</span></span>  <br/> |<span data-ttu-id="8ae8a-152">元素在其父元素中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-152">The unique ID of the element within its parent element.</span></span>  <br/> |<span data-ttu-id="8ae8a-153">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8ae8a-153">Values of the xsd:string type.</span></span>  <br/> |
   

