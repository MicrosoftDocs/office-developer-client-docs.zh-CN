---
title: SnapSettings 元素 （Window_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b87a244-b331-7e93-d304-239f8ca77061
description: 指定形状对齐时对齐位于活动窗口的对象。
ms.openlocfilehash: 55558301b1f85f70f723d4282b438e4883d90c25
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781395"
---
# <a name="snapsettings-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="77248-103">SnapSettings 元素 （Window_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="77248-103">SnapSettings element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="77248-104">指定形状对齐时对齐位于活动窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="77248-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="77248-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="77248-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="77248-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="77248-106">**Element type**</span></span> <br/> |[<span data-ttu-id="77248-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="77248-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="77248-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="77248-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="77248-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="77248-109">**Schema file**</span></span> <br/> |<span data-ttu-id="77248-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="77248-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="77248-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="77248-111">**Document parts**</span></span> <br/> |<span data-ttu-id="77248-112">windows.xml</span><span class="sxs-lookup"><span data-stu-id="77248-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="77248-113">定义</span><span class="sxs-lookup"><span data-stu-id="77248-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="77248-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="77248-114">Elements and attributes</span></span>

<span data-ttu-id="77248-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="77248-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="77248-116">父元素</span><span class="sxs-lookup"><span data-stu-id="77248-116">Parent elements</span></span>

|<span data-ttu-id="77248-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="77248-117">**Element**</span></span>|<span data-ttu-id="77248-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="77248-118">**Type**</span></span>|<span data-ttu-id="77248-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="77248-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="77248-120">Window</span><span class="sxs-lookup"><span data-stu-id="77248-120">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="77248-121">Window_Type</span><span class="sxs-lookup"><span data-stu-id="77248-121">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="77248-122">代表 Microsoft Visio 实例中打开的窗口。
</span><span class="sxs-lookup"><span data-stu-id="77248-122">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="77248-123">子元素</span><span class="sxs-lookup"><span data-stu-id="77248-123">Child elements</span></span>

<span data-ttu-id="77248-124">无。</span><span class="sxs-lookup"><span data-stu-id="77248-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="77248-125">属性</span><span class="sxs-lookup"><span data-stu-id="77248-125">Attributes</span></span>

<span data-ttu-id="77248-126">无。</span><span class="sxs-lookup"><span data-stu-id="77248-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="77248-127">说明</span><span class="sxs-lookup"><span data-stu-id="77248-127">Remarks</span></span>

<span data-ttu-id="77248-128">值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="77248-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="77248-129">**值**</span><span class="sxs-lookup"><span data-stu-id="77248-129">**Value**</span></span>|<span data-ttu-id="77248-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="77248-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77248-131">0</span><span class="sxs-lookup"><span data-stu-id="77248-131">0</span></span>  <br/> |<span data-ttu-id="77248-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="77248-133">1</span><span class="sxs-lookup"><span data-stu-id="77248-133">1</span></span>  <br/> |<span data-ttu-id="77248-134">与标尺细分线对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="77248-135">2</span><span class="sxs-lookup"><span data-stu-id="77248-135">2</span></span>  <br/> |<span data-ttu-id="77248-136">与网格对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="77248-137">4</span><span class="sxs-lookup"><span data-stu-id="77248-137">4</span></span>  <br/> |<span data-ttu-id="77248-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="77248-139">8</span><span class="sxs-lookup"><span data-stu-id="77248-139">8</span></span>  <br/> |<span data-ttu-id="77248-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="77248-141">16</span><span class="sxs-lookup"><span data-stu-id="77248-141">16</span></span>  <br/> |<span data-ttu-id="77248-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="77248-143">32</span><span class="sxs-lookup"><span data-stu-id="77248-143">32</span></span>  <br/> |<span data-ttu-id="77248-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="77248-145">256</span><span class="sxs-lookup"><span data-stu-id="77248-145">256</span></span>  <br/> |<span data-ttu-id="77248-146">与形状可见边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="77248-147">512</span><span class="sxs-lookup"><span data-stu-id="77248-147">512</span></span>  <br/> |<span data-ttu-id="77248-148">与对齐框对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="77248-149">1024</span><span class="sxs-lookup"><span data-stu-id="77248-149">1024</span></span>  <br/> |<span data-ttu-id="77248-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="77248-151">32768</span><span class="sxs-lookup"><span data-stu-id="77248-151">32768</span></span>  <br/> |<span data-ttu-id="77248-152">禁用的管理单元。</span><span class="sxs-lookup"><span data-stu-id="77248-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="77248-153">65536</span><span class="sxs-lookup"><span data-stu-id="77248-153">65536</span></span>  <br/> |<span data-ttu-id="77248-154">与交点对齐。</span><span class="sxs-lookup"><span data-stu-id="77248-154">Snap to intersections.</span></span>  <br/> |
   

