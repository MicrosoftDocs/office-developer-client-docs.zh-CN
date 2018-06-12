---
title: SnapExtensions 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d55b6676-125f-7cf1-509d-21dee548f5a1
description: 指定是否启用或禁用活动窗口的特定管理单元扩展设置。
ms.openlocfilehash: 4c00d8d45c1eb33f57f727779db91e358a83a969
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781385"
---
# <a name="snapextensions-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="af810-103">SnapExtensions 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="af810-103">SnapExtensions element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="af810-104">指定是否启用或禁用活动窗口的特定管理单元扩展设置。</span><span class="sxs-lookup"><span data-stu-id="af810-104">Specifies whether a specific snap extension setting is enabled or disabled for the active window.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="af810-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="af810-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="af810-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="af810-106">**Element type**</span></span> <br/> |[<span data-ttu-id="af810-107">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="af810-107">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="af810-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="af810-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="af810-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="af810-109">**Schema file**</span></span> <br/> |<span data-ttu-id="af810-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="af810-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="af810-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="af810-111">**Document parts**</span></span> <br/> |<span data-ttu-id="af810-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="af810-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="af810-113">定义</span><span class="sxs-lookup"><span data-stu-id="af810-113">Definition</span></span>

```XML
<xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="af810-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="af810-114">Elements and attributes</span></span>

<span data-ttu-id="af810-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="af810-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="af810-116">父元素</span><span class="sxs-lookup"><span data-stu-id="af810-116">Parent elements</span></span>

|<span data-ttu-id="af810-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="af810-117">**Element**</span></span>|<span data-ttu-id="af810-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="af810-118">**Type**</span></span>|<span data-ttu-id="af810-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="af810-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="af810-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="af810-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="af810-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="af810-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="af810-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="af810-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="af810-123">子元素</span><span class="sxs-lookup"><span data-stu-id="af810-123">Child elements</span></span>

<span data-ttu-id="af810-124">无。</span><span class="sxs-lookup"><span data-stu-id="af810-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="af810-125">属性</span><span class="sxs-lookup"><span data-stu-id="af810-125">Attributes</span></span>

<span data-ttu-id="af810-126">无。</span><span class="sxs-lookup"><span data-stu-id="af810-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="af810-127">备注</span><span class="sxs-lookup"><span data-stu-id="af810-127">Remarks</span></span>

<span data-ttu-id="af810-128">**SnapExtensions**元素的值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="af810-128">The value of the **SnapExtensions** element can be a sum of the values in the following table.</span></span> 
  
|<span data-ttu-id="af810-129">**值**</span><span class="sxs-lookup"><span data-stu-id="af810-129">**Value**</span></span>|<span data-ttu-id="af810-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="af810-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af810-131">0</span><span class="sxs-lookup"><span data-stu-id="af810-131">0</span></span>  <br/> |<span data-ttu-id="af810-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="af810-133">1</span><span class="sxs-lookup"><span data-stu-id="af810-133">1</span></span>  <br/> |<span data-ttu-id="af810-134">与对齐框延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-134">Snap to alignment box extension.</span></span>  <br/> |
|<span data-ttu-id="af810-135">2</span><span class="sxs-lookup"><span data-stu-id="af810-135">2</span></span>  <br/> |<span data-ttu-id="af810-136">与中心轴扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-136">Snap to center axis extension.</span></span>  <br/> |
|<span data-ttu-id="af810-137">4</span><span class="sxs-lookup"><span data-stu-id="af810-137">4</span></span>  <br/> |<span data-ttu-id="af810-138">与曲线切线扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-138">Snap to curve tangent extension.</span></span>  <br/> |
|<span data-ttu-id="af810-139">8</span><span class="sxs-lookup"><span data-stu-id="af810-139">8</span></span>  <br/> |<span data-ttu-id="af810-140">与终结点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-140">Snap to endpoint extension.</span></span>  <br/> |
|<span data-ttu-id="af810-141">16</span><span class="sxs-lookup"><span data-stu-id="af810-141">16</span></span>  <br/> |<span data-ttu-id="af810-142">与中点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-142">Snap to midpoint extension.</span></span>  <br/> |
|<span data-ttu-id="af810-143">32</span><span class="sxs-lookup"><span data-stu-id="af810-143">32</span></span>  <br/> |<span data-ttu-id="af810-144">与直线延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-144">Snap to linear extension.</span></span>  <br/> |
|<span data-ttu-id="af810-145">64</span><span class="sxs-lookup"><span data-stu-id="af810-145">64</span></span>  <br/> |<span data-ttu-id="af810-146">与曲线扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-146">Snap to curve extension.</span></span>  <br/> |
|<span data-ttu-id="af810-147">128</span><span class="sxs-lookup"><span data-stu-id="af810-147">128</span></span>  <br/> |<span data-ttu-id="af810-148">终结点的垂直扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-148">Snap to endpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="af810-149">256</span><span class="sxs-lookup"><span data-stu-id="af810-149">256</span></span>  <br/> |<span data-ttu-id="af810-150">与中点 perpendicular 扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-150">Snap to midpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="af810-151">512</span><span class="sxs-lookup"><span data-stu-id="af810-151">512</span></span>  <br/> |<span data-ttu-id="af810-152">终结点的水平扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-152">Snap to endpoint horizontal extension.</span></span>  <br/> |
|<span data-ttu-id="af810-153">1024</span><span class="sxs-lookup"><span data-stu-id="af810-153">1024</span></span>  <br/> |<span data-ttu-id="af810-154">终结点的垂直扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-154">Snap to endpoint vertical extension.</span></span>  <br/> |
|<span data-ttu-id="af810-155">2048</span><span class="sxs-lookup"><span data-stu-id="af810-155">2048</span></span>  <br/> |<span data-ttu-id="af810-156">椭圆中心扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-156">Snap to ellipse center extension.</span></span>  <br/> |
|<span data-ttu-id="af810-157">4096</span><span class="sxs-lookup"><span data-stu-id="af810-157">4096</span></span>  <br/> |<span data-ttu-id="af810-158">与扩展等角对齐。</span><span class="sxs-lookup"><span data-stu-id="af810-158">Snap to isometric angles extension.</span></span>  <br/> |
   

