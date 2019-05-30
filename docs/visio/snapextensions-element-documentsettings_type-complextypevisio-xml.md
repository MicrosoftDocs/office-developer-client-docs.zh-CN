---
title: SnapExtensions 元素 (DocumentSettings_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d55b6676-125f-7cf1-509d-21dee548f5a1
description: 指定是否为活动窗口启用或禁用特定的快照扩展设置。
ms.openlocfilehash: 86ff7f32d6e12b2f0d7a8387d8e5b7ae9870b5fa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540376"
---
# <a name="snapextensions-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="17481-103">SnapExtensions 元素 (DocumentSettings_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="17481-103">SnapExtensions element (DocumentSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="17481-104">指定是否为活动窗口启用或禁用特定的快照扩展设置。</span><span class="sxs-lookup"><span data-stu-id="17481-104">Specifies whether a specific snap extension setting is enabled or disabled for the active window.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="17481-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="17481-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="17481-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="17481-106">**Element type**</span></span> <br/> |[<span data-ttu-id="17481-107">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="17481-107">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="17481-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="17481-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="17481-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="17481-109">**Schema file**</span></span> <br/> |<span data-ttu-id="17481-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="17481-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="17481-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="17481-111">**Document parts**</span></span> <br/> |<span data-ttu-id="17481-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="17481-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="17481-113">定义</span><span class="sxs-lookup"><span data-stu-id="17481-113">Definition</span></span>

```XML
<xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="17481-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="17481-114">Elements and attributes</span></span>

<span data-ttu-id="17481-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="17481-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="17481-116">父元素</span><span class="sxs-lookup"><span data-stu-id="17481-116">Parent elements</span></span>

|<span data-ttu-id="17481-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="17481-117">**Element**</span></span>|<span data-ttu-id="17481-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="17481-118">**Type**</span></span>|<span data-ttu-id="17481-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="17481-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="17481-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="17481-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="17481-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="17481-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="17481-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="17481-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="17481-123">子元素</span><span class="sxs-lookup"><span data-stu-id="17481-123">Child elements</span></span>

<span data-ttu-id="17481-124">无。</span><span class="sxs-lookup"><span data-stu-id="17481-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="17481-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="17481-125">Attributes</span></span>

<span data-ttu-id="17481-126">无。</span><span class="sxs-lookup"><span data-stu-id="17481-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="17481-127">注解</span><span class="sxs-lookup"><span data-stu-id="17481-127">Remarks</span></span>

<span data-ttu-id="17481-128">**SnapExtensions**元素的值可以是下表中的值的总和。</span><span class="sxs-lookup"><span data-stu-id="17481-128">The value of the **SnapExtensions** element can be a sum of the values in the following table.</span></span> 
  
|<span data-ttu-id="17481-129">**值**</span><span class="sxs-lookup"><span data-stu-id="17481-129">**Value**</span></span>|<span data-ttu-id="17481-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="17481-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="17481-131">0</span><span class="sxs-lookup"><span data-stu-id="17481-131">0</span></span>  <br/> |<span data-ttu-id="17481-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="17481-133">1</span><span class="sxs-lookup"><span data-stu-id="17481-133">1</span></span>  <br/> |<span data-ttu-id="17481-134">与对齐框的延伸对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-134">Snap to alignment box extension.</span></span>  <br/> |
|<span data-ttu-id="17481-135">双面</span><span class="sxs-lookup"><span data-stu-id="17481-135">2</span></span>  <br/> |<span data-ttu-id="17481-136">居中轴延长线。</span><span class="sxs-lookup"><span data-stu-id="17481-136">Snap to center axis extension.</span></span>  <br/> |
|<span data-ttu-id="17481-137">4</span><span class="sxs-lookup"><span data-stu-id="17481-137">4</span></span>  <br/> |<span data-ttu-id="17481-138">与曲线相切延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-138">Snap to curve tangent extension.</span></span>  <br/> |
|<span data-ttu-id="17481-139">utf-8</span><span class="sxs-lookup"><span data-stu-id="17481-139">8</span></span>  <br/> |<span data-ttu-id="17481-140">与终结点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-140">Snap to endpoint extension.</span></span>  <br/> |
|<span data-ttu-id="17481-141">位</span><span class="sxs-lookup"><span data-stu-id="17481-141">16</span></span>  <br/> |<span data-ttu-id="17481-142">与中点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-142">Snap to midpoint extension.</span></span>  <br/> |
|<span data-ttu-id="17481-143">32</span><span class="sxs-lookup"><span data-stu-id="17481-143">32</span></span>  <br/> |<span data-ttu-id="17481-144">与线性延伸对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-144">Snap to linear extension.</span></span>  <br/> |
|<span data-ttu-id="17481-145">64</span><span class="sxs-lookup"><span data-stu-id="17481-145">64</span></span>  <br/> |<span data-ttu-id="17481-146">与曲线延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-146">Snap to curve extension.</span></span>  <br/> |
|<span data-ttu-id="17481-147">128</span><span class="sxs-lookup"><span data-stu-id="17481-147">128</span></span>  <br/> |<span data-ttu-id="17481-148">与终结点垂直扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-148">Snap to endpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="17481-149">256</span><span class="sxs-lookup"><span data-stu-id="17481-149">256</span></span>  <br/> |<span data-ttu-id="17481-150">与中点垂直延伸对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-150">Snap to midpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="17481-151">512</span><span class="sxs-lookup"><span data-stu-id="17481-151">512</span></span>  <br/> |<span data-ttu-id="17481-152">对齐终结点水平扩展。</span><span class="sxs-lookup"><span data-stu-id="17481-152">Snap to endpoint horizontal extension.</span></span>  <br/> |
|<span data-ttu-id="17481-153">1024</span><span class="sxs-lookup"><span data-stu-id="17481-153">1024</span></span>  <br/> |<span data-ttu-id="17481-154">与终结点垂直扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-154">Snap to endpoint vertical extension.</span></span>  <br/> |
|<span data-ttu-id="17481-155">2048</span><span class="sxs-lookup"><span data-stu-id="17481-155">2048</span></span>  <br/> |<span data-ttu-id="17481-156">与椭圆中心延伸对齐。</span><span class="sxs-lookup"><span data-stu-id="17481-156">Snap to ellipse center extension.</span></span>  <br/> |
|<span data-ttu-id="17481-157">4096</span><span class="sxs-lookup"><span data-stu-id="17481-157">4096</span></span>  <br/> |<span data-ttu-id="17481-158">对齐等角扩展。</span><span class="sxs-lookup"><span data-stu-id="17481-158">Snap to isometric angles extension.</span></span>  <br/> |
   

