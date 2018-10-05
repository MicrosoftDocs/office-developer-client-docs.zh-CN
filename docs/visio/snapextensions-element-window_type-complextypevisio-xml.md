---
title: SnapExtensions 元素 （Window_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7a12ae10-6aa4-c845-5ede-1c14c6dac80f
description: 指定是否启用或禁用活动窗口的特定管理单元扩展设置。 值可以是下表中值的总和。
ms.openlocfilehash: 57fde520d3dc8e0582c0062a599d5f38a73169b4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394403"
---
# <a name="snapextensions-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="11d55-104">SnapExtensions 元素 （Window_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="11d55-104">SnapExtensions element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="11d55-105">指定是否启用或禁用活动窗口的特定管理单元扩展设置。</span><span class="sxs-lookup"><span data-stu-id="11d55-105">Specifies whether a specific snap extension setting is enabled or disabled for the active window.</span></span> <span data-ttu-id="11d55-106">值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="11d55-106">The value can be a sum of the values in the following table.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="11d55-107">元素信息</span><span class="sxs-lookup"><span data-stu-id="11d55-107">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11d55-108">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="11d55-108">**Element type**</span></span> <br/> |[<span data-ttu-id="11d55-109">SnapExtensions_Type</span><span class="sxs-lookup"><span data-stu-id="11d55-109">SnapExtensions_Type</span></span>](snapextensions_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="11d55-110">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="11d55-110">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="11d55-111">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="11d55-111">**Schema file**</span></span> <br/> |<span data-ttu-id="11d55-112">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="11d55-112">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="11d55-113">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="11d55-113">**Document parts**</span></span> <br/> |<span data-ttu-id="11d55-114">windows.xml</span><span class="sxs-lookup"><span data-stu-id="11d55-114">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="11d55-115">定义</span><span class="sxs-lookup"><span data-stu-id="11d55-115">Definition</span></span>

```XML
< xs:element name="SnapExtensions" type="SnapExtensions_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="11d55-116">元素和属性</span><span class="sxs-lookup"><span data-stu-id="11d55-116">Elements and attributes</span></span>

<span data-ttu-id="11d55-117">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="11d55-117">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="11d55-118">父元素</span><span class="sxs-lookup"><span data-stu-id="11d55-118">Parent elements</span></span>

|<span data-ttu-id="11d55-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="11d55-119">**Element**</span></span>|<span data-ttu-id="11d55-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="11d55-120">**Type**</span></span>|<span data-ttu-id="11d55-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="11d55-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="11d55-122">Window</span><span class="sxs-lookup"><span data-stu-id="11d55-122">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="11d55-123">Window_Type</span><span class="sxs-lookup"><span data-stu-id="11d55-123">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> ||
   
### <a name="child-elements"></a><span data-ttu-id="11d55-124">子元素</span><span class="sxs-lookup"><span data-stu-id="11d55-124">Child elements</span></span>

<span data-ttu-id="11d55-125">无。</span><span class="sxs-lookup"><span data-stu-id="11d55-125">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="11d55-126">属性</span><span class="sxs-lookup"><span data-stu-id="11d55-126">Attributes</span></span>

<span data-ttu-id="11d55-127">无。</span><span class="sxs-lookup"><span data-stu-id="11d55-127">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="11d55-128">说明</span><span class="sxs-lookup"><span data-stu-id="11d55-128">Remarks</span></span>

<span data-ttu-id="11d55-129">**SnapExtensions**元素的值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="11d55-129">The value of the **SnapExtensions** element can be a sum of the values in the following table.</span></span> 
  
|<span data-ttu-id="11d55-130">**值**</span><span class="sxs-lookup"><span data-stu-id="11d55-130">**Value**</span></span>|<span data-ttu-id="11d55-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="11d55-131">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="11d55-132">0</span><span class="sxs-lookup"><span data-stu-id="11d55-132">0</span></span>  <br/> |<span data-ttu-id="11d55-133">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-133">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="11d55-134">1</span><span class="sxs-lookup"><span data-stu-id="11d55-134">1</span></span>  <br/> |<span data-ttu-id="11d55-135">与对齐框延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-135">Snap to alignment box extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-136">2</span><span class="sxs-lookup"><span data-stu-id="11d55-136">2</span></span>  <br/> |<span data-ttu-id="11d55-137">与中心轴扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-137">Snap to center axis extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-138">4</span><span class="sxs-lookup"><span data-stu-id="11d55-138">4</span></span>  <br/> |<span data-ttu-id="11d55-139">与曲线切线扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-139">Snap to curve tangent extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-140">8</span><span class="sxs-lookup"><span data-stu-id="11d55-140">8</span></span>  <br/> |<span data-ttu-id="11d55-141">与终结点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-141">Snap to endpoint extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-142">16</span><span class="sxs-lookup"><span data-stu-id="11d55-142">16</span></span>  <br/> |<span data-ttu-id="11d55-143">与中点扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-143">Snap to midpoint extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-144">32</span><span class="sxs-lookup"><span data-stu-id="11d55-144">32</span></span>  <br/> |<span data-ttu-id="11d55-145">与直线延长线对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-145">Snap to linear extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-146">64</span><span class="sxs-lookup"><span data-stu-id="11d55-146">64</span></span>  <br/> |<span data-ttu-id="11d55-147">与曲线扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-147">Snap to curve extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-148">128</span><span class="sxs-lookup"><span data-stu-id="11d55-148">128</span></span>  <br/> |<span data-ttu-id="11d55-149">终结点的垂直扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-149">Snap to endpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-150">256</span><span class="sxs-lookup"><span data-stu-id="11d55-150">256</span></span>  <br/> |<span data-ttu-id="11d55-151">与中点 perpendicular 扩展对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-151">Snap to midpoint perpendicular extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-152">512</span><span class="sxs-lookup"><span data-stu-id="11d55-152">512</span></span>  <br/> |<span data-ttu-id="11d55-153">终结点的水平扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-153">Snap to endpoint horizontal extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-154">1024</span><span class="sxs-lookup"><span data-stu-id="11d55-154">1024</span></span>  <br/> |<span data-ttu-id="11d55-155">终结点的垂直扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-155">Snap to endpoint vertical extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-156">2048</span><span class="sxs-lookup"><span data-stu-id="11d55-156">2048</span></span>  <br/> |<span data-ttu-id="11d55-157">椭圆中心扩展名与对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-157">Snap to ellipse center extension.</span></span>  <br/> |
|<span data-ttu-id="11d55-158">4096</span><span class="sxs-lookup"><span data-stu-id="11d55-158">4096</span></span>  <br/> |<span data-ttu-id="11d55-159">与扩展等角对齐。</span><span class="sxs-lookup"><span data-stu-id="11d55-159">Snap to isometric angles extension.</span></span>  <br/> |
   

