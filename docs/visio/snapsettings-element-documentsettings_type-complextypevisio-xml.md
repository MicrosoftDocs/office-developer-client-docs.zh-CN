---
title: SnapSettings 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e86e943-bd29-0a7b-3d6a-d91281f98777
description: 指定形状对齐时对齐位于活动窗口的对象。
ms.openlocfilehash: 0e784ddf9d5e04dae20a6a811557455c476b11a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781394"
---
# <a name="snapsettings-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="ef9f2-103">SnapSettings 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ef9f2-103">SnapSettings element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="ef9f2-104">指定形状对齐时对齐位于活动窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="ef9f2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ef9f2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ef9f2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ef9f2-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="ef9f2-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ef9f2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ef9f2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ef9f2-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="ef9f2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ef9f2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ef9f2-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="ef9f2-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ef9f2-113">定义</span><span class="sxs-lookup"><span data-stu-id="ef9f2-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ef9f2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ef9f2-114">Elements and attributes</span></span>

<span data-ttu-id="ef9f2-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ef9f2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ef9f2-116">Parent elements</span></span>

|<span data-ttu-id="ef9f2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-117">**Element**</span></span>|<span data-ttu-id="ef9f2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-118">**Type**</span></span>|<span data-ttu-id="ef9f2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ef9f2-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="ef9f2-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="ef9f2-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="ef9f2-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ef9f2-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="ef9f2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ef9f2-123">Child elements</span></span>

<span data-ttu-id="ef9f2-124">无。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ef9f2-125">属性</span><span class="sxs-lookup"><span data-stu-id="ef9f2-125">Attributes</span></span>

<span data-ttu-id="ef9f2-126">无。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ef9f2-127">备注</span><span class="sxs-lookup"><span data-stu-id="ef9f2-127">Remarks</span></span>

<span data-ttu-id="ef9f2-128">值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="ef9f2-129">**值**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-129">**Value**</span></span>|<span data-ttu-id="ef9f2-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="ef9f2-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef9f2-131">0</span><span class="sxs-lookup"><span data-stu-id="ef9f2-131">0</span></span>  <br/> |<span data-ttu-id="ef9f2-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-133">1</span><span class="sxs-lookup"><span data-stu-id="ef9f2-133">1</span></span>  <br/> |<span data-ttu-id="ef9f2-134">与标尺细分线对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-135">2</span><span class="sxs-lookup"><span data-stu-id="ef9f2-135">2</span></span>  <br/> |<span data-ttu-id="ef9f2-136">与网格对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-137">4</span><span class="sxs-lookup"><span data-stu-id="ef9f2-137">4</span></span>  <br/> |<span data-ttu-id="ef9f2-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-139">8</span><span class="sxs-lookup"><span data-stu-id="ef9f2-139">8</span></span>  <br/> |<span data-ttu-id="ef9f2-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-141">16</span><span class="sxs-lookup"><span data-stu-id="ef9f2-141">16</span></span>  <br/> |<span data-ttu-id="ef9f2-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-143">32</span><span class="sxs-lookup"><span data-stu-id="ef9f2-143">32</span></span>  <br/> |<span data-ttu-id="ef9f2-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-145">256</span><span class="sxs-lookup"><span data-stu-id="ef9f2-145">256</span></span>  <br/> |<span data-ttu-id="ef9f2-146">与形状可见边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-147">512</span><span class="sxs-lookup"><span data-stu-id="ef9f2-147">512</span></span>  <br/> |<span data-ttu-id="ef9f2-148">与对齐框对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-149">1024</span><span class="sxs-lookup"><span data-stu-id="ef9f2-149">1024</span></span>  <br/> |<span data-ttu-id="ef9f2-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-151">32768</span><span class="sxs-lookup"><span data-stu-id="ef9f2-151">32768</span></span>  <br/> |<span data-ttu-id="ef9f2-152">禁用的管理单元。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="ef9f2-153">65536</span><span class="sxs-lookup"><span data-stu-id="ef9f2-153">65536</span></span>  <br/> |<span data-ttu-id="ef9f2-154">与交点对齐。</span><span class="sxs-lookup"><span data-stu-id="ef9f2-154">Snap to intersections.</span></span>  <br/> |
   

