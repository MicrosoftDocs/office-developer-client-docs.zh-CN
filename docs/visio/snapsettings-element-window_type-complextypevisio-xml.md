---
title: SnapSettings 元素 （Window_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b87a244-b331-7e93-d304-239f8ca77061
description: 指定形状对齐时对齐位于活动窗口的对象。
ms.openlocfilehash: b4793c6d9c13a922db4d3ed9504a3a08e933230a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385205"
---
# <a name="snapsettings-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="14374-103">SnapSettings 元素 （Window_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="14374-103">SnapSettings element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="14374-104">指定形状对齐时对齐位于活动窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="14374-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="14374-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="14374-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="14374-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="14374-106">**Element type**</span></span> <br/> |[<span data-ttu-id="14374-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="14374-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="14374-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="14374-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="14374-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="14374-109">**Schema file**</span></span> <br/> |<span data-ttu-id="14374-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="14374-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="14374-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="14374-111">**Document parts**</span></span> <br/> |<span data-ttu-id="14374-112">windows.xml</span><span class="sxs-lookup"><span data-stu-id="14374-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="14374-113">定义</span><span class="sxs-lookup"><span data-stu-id="14374-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="14374-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="14374-114">Elements and attributes</span></span>

<span data-ttu-id="14374-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="14374-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="14374-116">父元素</span><span class="sxs-lookup"><span data-stu-id="14374-116">Parent elements</span></span>

|<span data-ttu-id="14374-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="14374-117">**Element**</span></span>|<span data-ttu-id="14374-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="14374-118">**Type**</span></span>|<span data-ttu-id="14374-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="14374-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="14374-120">Window</span><span class="sxs-lookup"><span data-stu-id="14374-120">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="14374-121">Window_Type</span><span class="sxs-lookup"><span data-stu-id="14374-121">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="14374-122">代表 Microsoft Visio 实例中打开的窗口。
</span><span class="sxs-lookup"><span data-stu-id="14374-122">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="14374-123">子元素</span><span class="sxs-lookup"><span data-stu-id="14374-123">Child elements</span></span>

<span data-ttu-id="14374-124">无。</span><span class="sxs-lookup"><span data-stu-id="14374-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="14374-125">属性</span><span class="sxs-lookup"><span data-stu-id="14374-125">Attributes</span></span>

<span data-ttu-id="14374-126">无。</span><span class="sxs-lookup"><span data-stu-id="14374-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="14374-127">说明</span><span class="sxs-lookup"><span data-stu-id="14374-127">Remarks</span></span>

<span data-ttu-id="14374-128">值可以是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="14374-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="14374-129">**值**</span><span class="sxs-lookup"><span data-stu-id="14374-129">**Value**</span></span>|<span data-ttu-id="14374-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="14374-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14374-131">0</span><span class="sxs-lookup"><span data-stu-id="14374-131">0</span></span>  <br/> |<span data-ttu-id="14374-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="14374-133">1</span><span class="sxs-lookup"><span data-stu-id="14374-133">1</span></span>  <br/> |<span data-ttu-id="14374-134">与标尺细分线对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="14374-135">2</span><span class="sxs-lookup"><span data-stu-id="14374-135">2</span></span>  <br/> |<span data-ttu-id="14374-136">与网格对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="14374-137">4</span><span class="sxs-lookup"><span data-stu-id="14374-137">4</span></span>  <br/> |<span data-ttu-id="14374-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="14374-139">8</span><span class="sxs-lookup"><span data-stu-id="14374-139">8</span></span>  <br/> |<span data-ttu-id="14374-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="14374-141">16</span><span class="sxs-lookup"><span data-stu-id="14374-141">16</span></span>  <br/> |<span data-ttu-id="14374-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="14374-143">32</span><span class="sxs-lookup"><span data-stu-id="14374-143">32</span></span>  <br/> |<span data-ttu-id="14374-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="14374-145">256</span><span class="sxs-lookup"><span data-stu-id="14374-145">256</span></span>  <br/> |<span data-ttu-id="14374-146">与形状可见边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="14374-147">512</span><span class="sxs-lookup"><span data-stu-id="14374-147">512</span></span>  <br/> |<span data-ttu-id="14374-148">与对齐框对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="14374-149">1024</span><span class="sxs-lookup"><span data-stu-id="14374-149">1024</span></span>  <br/> |<span data-ttu-id="14374-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="14374-151">32768</span><span class="sxs-lookup"><span data-stu-id="14374-151">32768</span></span>  <br/> |<span data-ttu-id="14374-152">禁用的管理单元。</span><span class="sxs-lookup"><span data-stu-id="14374-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="14374-153">65536</span><span class="sxs-lookup"><span data-stu-id="14374-153">65536</span></span>  <br/> |<span data-ttu-id="14374-154">与交点对齐。</span><span class="sxs-lookup"><span data-stu-id="14374-154">Snap to intersections.</span></span>  <br/> |
   

