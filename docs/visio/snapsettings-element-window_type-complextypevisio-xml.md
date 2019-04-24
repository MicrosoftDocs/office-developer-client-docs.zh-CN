---
title: SnapSettings 元素 (Window_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b87a244-b331-7e93-d304-239f8ca77061
description: 指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。
ms.openlocfilehash: b4793c6d9c13a922db4d3ed9504a3a08e933230a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334501"
---
# <a name="snapsettings-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="31e30-103">SnapSettings 元素 (Window_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="31e30-103">SnapSettings element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="31e30-104">指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。</span><span class="sxs-lookup"><span data-stu-id="31e30-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="31e30-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="31e30-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="31e30-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="31e30-106">**Element type**</span></span> <br/> |[<span data-ttu-id="31e30-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="31e30-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="31e30-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="31e30-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="31e30-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="31e30-109">**Schema file**</span></span> <br/> |<span data-ttu-id="31e30-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="31e30-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="31e30-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="31e30-111">**Document parts**</span></span> <br/> |<span data-ttu-id="31e30-112">windows .xml</span><span class="sxs-lookup"><span data-stu-id="31e30-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="31e30-113">定义</span><span class="sxs-lookup"><span data-stu-id="31e30-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="31e30-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="31e30-114">Elements and attributes</span></span>

<span data-ttu-id="31e30-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="31e30-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="31e30-116">父元素</span><span class="sxs-lookup"><span data-stu-id="31e30-116">Parent elements</span></span>

|<span data-ttu-id="31e30-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="31e30-117">**Element**</span></span>|<span data-ttu-id="31e30-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="31e30-118">**Type**</span></span>|<span data-ttu-id="31e30-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="31e30-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="31e30-120">Window</span><span class="sxs-lookup"><span data-stu-id="31e30-120">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="31e30-121">Window_Type</span><span class="sxs-lookup"><span data-stu-id="31e30-121">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="31e30-122">代表 Microsoft Visio 实例中打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="31e30-122">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="31e30-123">子元素</span><span class="sxs-lookup"><span data-stu-id="31e30-123">Child elements</span></span>

<span data-ttu-id="31e30-124">无。</span><span class="sxs-lookup"><span data-stu-id="31e30-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="31e30-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="31e30-125">Attributes</span></span>

<span data-ttu-id="31e30-126">无。</span><span class="sxs-lookup"><span data-stu-id="31e30-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="31e30-127">注解</span><span class="sxs-lookup"><span data-stu-id="31e30-127">Remarks</span></span>

<span data-ttu-id="31e30-128">该值可以是下表中的值的总和。</span><span class="sxs-lookup"><span data-stu-id="31e30-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="31e30-129">**Value**</span><span class="sxs-lookup"><span data-stu-id="31e30-129">**Value**</span></span>|<span data-ttu-id="31e30-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="31e30-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="31e30-131">0</span><span class="sxs-lookup"><span data-stu-id="31e30-131">0</span></span>  <br/> |<span data-ttu-id="31e30-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="31e30-133">1</span><span class="sxs-lookup"><span data-stu-id="31e30-133">1</span></span>  <br/> |<span data-ttu-id="31e30-134">与标尺细分线对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="31e30-135">双面</span><span class="sxs-lookup"><span data-stu-id="31e30-135">2</span></span>  <br/> |<span data-ttu-id="31e30-136">与网格对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="31e30-137">4</span><span class="sxs-lookup"><span data-stu-id="31e30-137">4</span></span>  <br/> |<span data-ttu-id="31e30-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="31e30-139">utf-8</span><span class="sxs-lookup"><span data-stu-id="31e30-139">8</span></span>  <br/> |<span data-ttu-id="31e30-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="31e30-141">位</span><span class="sxs-lookup"><span data-stu-id="31e30-141">16</span></span>  <br/> |<span data-ttu-id="31e30-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="31e30-143">32</span><span class="sxs-lookup"><span data-stu-id="31e30-143">32</span></span>  <br/> |<span data-ttu-id="31e30-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="31e30-145">256</span><span class="sxs-lookup"><span data-stu-id="31e30-145">256</span></span>  <br/> |<span data-ttu-id="31e30-146">与形状的可见边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="31e30-147">512</span><span class="sxs-lookup"><span data-stu-id="31e30-147">512</span></span>  <br/> |<span data-ttu-id="31e30-148">与对齐框对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="31e30-149">1024</span><span class="sxs-lookup"><span data-stu-id="31e30-149">1024</span></span>  <br/> |<span data-ttu-id="31e30-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="31e30-151">32768</span><span class="sxs-lookup"><span data-stu-id="31e30-151">32768</span></span>  <br/> |<span data-ttu-id="31e30-152">已禁用快照。</span><span class="sxs-lookup"><span data-stu-id="31e30-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="31e30-153">65536</span><span class="sxs-lookup"><span data-stu-id="31e30-153">65536</span></span>  <br/> |<span data-ttu-id="31e30-154">与相交的部分对齐。</span><span class="sxs-lookup"><span data-stu-id="31e30-154">Snap to intersections.</span></span>  <br/> |
   

