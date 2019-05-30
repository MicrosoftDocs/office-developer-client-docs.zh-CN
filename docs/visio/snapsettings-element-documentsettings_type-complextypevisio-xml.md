---
title: SnapSettings 元素 (DocumentSettings_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e86e943-bd29-0a7b-3d6a-d91281f98777
description: 指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。
ms.openlocfilehash: 8d4be35a4cd66a1d3914dbda8162f4acb3d05bfa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540292"
---
# <a name="snapsettings-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="d3085-103">SnapSettings 元素 (DocumentSettings_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d3085-103">SnapSettings element (DocumentSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="d3085-104">指定在窗口中的 "对齐" 处于活动状态时, 形状将对齐到的对象。</span><span class="sxs-lookup"><span data-stu-id="d3085-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="d3085-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="d3085-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d3085-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="d3085-106">**Element type**</span></span> <br/> |[<span data-ttu-id="d3085-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="d3085-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="d3085-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d3085-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="d3085-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d3085-109">**Schema file**</span></span> <br/> |<span data-ttu-id="d3085-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="d3085-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="d3085-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="d3085-111">**Document parts**</span></span> <br/> |<span data-ttu-id="d3085-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="d3085-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d3085-113">定义</span><span class="sxs-lookup"><span data-stu-id="d3085-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="d3085-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d3085-114">Elements and attributes</span></span>

<span data-ttu-id="d3085-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d3085-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="d3085-116">父元素</span><span class="sxs-lookup"><span data-stu-id="d3085-116">Parent elements</span></span>

|<span data-ttu-id="d3085-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="d3085-117">**Element**</span></span>|<span data-ttu-id="d3085-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="d3085-118">**Type**</span></span>|<span data-ttu-id="d3085-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="d3085-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d3085-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="d3085-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="d3085-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="d3085-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="d3085-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="d3085-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="d3085-123">子元素</span><span class="sxs-lookup"><span data-stu-id="d3085-123">Child elements</span></span>

<span data-ttu-id="d3085-124">无。</span><span class="sxs-lookup"><span data-stu-id="d3085-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="d3085-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="d3085-125">Attributes</span></span>

<span data-ttu-id="d3085-126">无。</span><span class="sxs-lookup"><span data-stu-id="d3085-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d3085-127">注解</span><span class="sxs-lookup"><span data-stu-id="d3085-127">Remarks</span></span>

<span data-ttu-id="d3085-128">该值可以是下表中的值的总和。</span><span class="sxs-lookup"><span data-stu-id="d3085-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="d3085-129">**值**</span><span class="sxs-lookup"><span data-stu-id="d3085-129">**Value**</span></span>|<span data-ttu-id="d3085-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="d3085-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3085-131">0</span><span class="sxs-lookup"><span data-stu-id="d3085-131">0</span></span>  <br/> |<span data-ttu-id="d3085-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="d3085-133">1</span><span class="sxs-lookup"><span data-stu-id="d3085-133">1</span></span>  <br/> |<span data-ttu-id="d3085-134">与标尺细分线对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="d3085-135">双面</span><span class="sxs-lookup"><span data-stu-id="d3085-135">2</span></span>  <br/> |<span data-ttu-id="d3085-136">与网格对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="d3085-137">4</span><span class="sxs-lookup"><span data-stu-id="d3085-137">4</span></span>  <br/> |<span data-ttu-id="d3085-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="d3085-139">utf-8</span><span class="sxs-lookup"><span data-stu-id="d3085-139">8</span></span>  <br/> |<span data-ttu-id="d3085-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="d3085-141">位</span><span class="sxs-lookup"><span data-stu-id="d3085-141">16</span></span>  <br/> |<span data-ttu-id="d3085-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="d3085-143">32</span><span class="sxs-lookup"><span data-stu-id="d3085-143">32</span></span>  <br/> |<span data-ttu-id="d3085-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="d3085-145">256</span><span class="sxs-lookup"><span data-stu-id="d3085-145">256</span></span>  <br/> |<span data-ttu-id="d3085-146">与形状的可见边缘对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="d3085-147">512</span><span class="sxs-lookup"><span data-stu-id="d3085-147">512</span></span>  <br/> |<span data-ttu-id="d3085-148">与对齐框对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="d3085-149">1024</span><span class="sxs-lookup"><span data-stu-id="d3085-149">1024</span></span>  <br/> |<span data-ttu-id="d3085-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="d3085-151">32768</span><span class="sxs-lookup"><span data-stu-id="d3085-151">32768</span></span>  <br/> |<span data-ttu-id="d3085-152">已禁用快照。</span><span class="sxs-lookup"><span data-stu-id="d3085-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="d3085-153">65536</span><span class="sxs-lookup"><span data-stu-id="d3085-153">65536</span></span>  <br/> |<span data-ttu-id="d3085-154">与相交的部分对齐。</span><span class="sxs-lookup"><span data-stu-id="d3085-154">Snap to intersections.</span></span>  <br/> |
   

