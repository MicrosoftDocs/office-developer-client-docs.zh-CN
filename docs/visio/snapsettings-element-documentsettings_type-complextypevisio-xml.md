---
title: 'SnapSettings 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6e86e943-bd29-0a7b-3d6a-d91281f98777
description: 指定当窗口中的对齐处于活动状态时形状所对齐的对象。
ms.openlocfilehash: 8d4be35a4cd66a1d3914dbda8162f4acb3d05bfa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540292"
---
# <a name="snapsettings-element-documentsettings_type-complextype-visio-xml"></a><span data-ttu-id="10569-103">SnapSettings 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="10569-103">SnapSettings element (DocumentSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="10569-104">指定当窗口中的对齐处于活动状态时形状所对齐的对象。</span><span class="sxs-lookup"><span data-stu-id="10569-104">Specifies the objects that shapes snap to when snap is active in the window.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="10569-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="10569-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="10569-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="10569-106">**Element type**</span></span> <br/> |[<span data-ttu-id="10569-107">SnapSettings_Type</span><span class="sxs-lookup"><span data-stu-id="10569-107">SnapSettings_Type</span></span>](snapsettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="10569-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="10569-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="10569-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="10569-109">**Schema file**</span></span> <br/> |<span data-ttu-id="10569-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="10569-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="10569-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="10569-111">**Document parts**</span></span> <br/> |<span data-ttu-id="10569-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="10569-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="10569-113">定义</span><span class="sxs-lookup"><span data-stu-id="10569-113">Definition</span></span>

```XML
< xs:element name="SnapSettings" type="SnapSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="10569-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="10569-114">Elements and attributes</span></span>

<span data-ttu-id="10569-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="10569-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="10569-116">父元素</span><span class="sxs-lookup"><span data-stu-id="10569-116">Parent elements</span></span>

|<span data-ttu-id="10569-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="10569-117">**Element**</span></span>|<span data-ttu-id="10569-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="10569-118">**Type**</span></span>|<span data-ttu-id="10569-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="10569-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="10569-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="10569-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="10569-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="10569-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="10569-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="10569-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="10569-123">子元素</span><span class="sxs-lookup"><span data-stu-id="10569-123">Child elements</span></span>

<span data-ttu-id="10569-124">无。</span><span class="sxs-lookup"><span data-stu-id="10569-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="10569-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="10569-125">Attributes</span></span>

<span data-ttu-id="10569-126">无。</span><span class="sxs-lookup"><span data-stu-id="10569-126">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="10569-127">说明</span><span class="sxs-lookup"><span data-stu-id="10569-127">Remarks</span></span>

<span data-ttu-id="10569-128">该值可能是下表中值的总和。</span><span class="sxs-lookup"><span data-stu-id="10569-128">The value may be a sum of the values in the following table.</span></span>
  
|<span data-ttu-id="10569-129">**值**</span><span class="sxs-lookup"><span data-stu-id="10569-129">**Value**</span></span>|<span data-ttu-id="10569-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="10569-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10569-131">0</span><span class="sxs-lookup"><span data-stu-id="10569-131">0</span></span>  <br/> |<span data-ttu-id="10569-132">不与任何内容对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-132">Snap to nothing.</span></span>  <br/> |
|<span data-ttu-id="10569-133">1</span><span class="sxs-lookup"><span data-stu-id="10569-133">1</span></span>  <br/> |<span data-ttu-id="10569-134">贴靠标尺细分线。</span><span class="sxs-lookup"><span data-stu-id="10569-134">Snap to ruler subdivisions.</span></span>  <br/> |
|<span data-ttu-id="10569-135">2</span><span class="sxs-lookup"><span data-stu-id="10569-135">2</span></span>  <br/> |<span data-ttu-id="10569-136">贴靠网格。</span><span class="sxs-lookup"><span data-stu-id="10569-136">Snap to grid.</span></span>  <br/> |
|<span data-ttu-id="10569-137">4 </span><span class="sxs-lookup"><span data-stu-id="10569-137">4</span></span>  <br/> |<span data-ttu-id="10569-138">与参考线对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-138">Snap to guides.</span></span>  <br/> |
|<span data-ttu-id="10569-139">8 </span><span class="sxs-lookup"><span data-stu-id="10569-139">8</span></span>  <br/> |<span data-ttu-id="10569-140">与选择手柄对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-140">Snap to selection handles.</span></span>  <br/> |
|<span data-ttu-id="10569-141">16 </span><span class="sxs-lookup"><span data-stu-id="10569-141">16</span></span>  <br/> |<span data-ttu-id="10569-142">与顶点对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-142">Snap to vertices.</span></span>  <br/> |
|<span data-ttu-id="10569-143">32</span><span class="sxs-lookup"><span data-stu-id="10569-143">32</span></span>  <br/> |<span data-ttu-id="10569-144">与连接点对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-144">Snap to connection points.</span></span>  <br/> |
|<span data-ttu-id="10569-145">256</span><span class="sxs-lookup"><span data-stu-id="10569-145">256</span></span>  <br/> |<span data-ttu-id="10569-146">贴靠形状的可见边缘。</span><span class="sxs-lookup"><span data-stu-id="10569-146">Snap to visible edges of shapes.</span></span>  <br/> |
|<span data-ttu-id="10569-147">512</span><span class="sxs-lookup"><span data-stu-id="10569-147">512</span></span>  <br/> |<span data-ttu-id="10569-148">贴靠对齐框。</span><span class="sxs-lookup"><span data-stu-id="10569-148">Snap to alignment box.</span></span>  <br/> |
|<span data-ttu-id="10569-149">1024</span><span class="sxs-lookup"><span data-stu-id="10569-149">1024</span></span>  <br/> |<span data-ttu-id="10569-150">与形状延长线选项对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-150">Snap to shape extensions options.</span></span>  <br/> |
|<span data-ttu-id="10569-151">32768</span><span class="sxs-lookup"><span data-stu-id="10569-151">32768</span></span>  <br/> |<span data-ttu-id="10569-152">贴靠禁用。</span><span class="sxs-lookup"><span data-stu-id="10569-152">Snap disabled.</span></span>  <br/> |
|<span data-ttu-id="10569-153">65536</span><span class="sxs-lookup"><span data-stu-id="10569-153">65536</span></span>  <br/> |<span data-ttu-id="10569-154">与相交的部分对齐。</span><span class="sxs-lookup"><span data-stu-id="10569-154">Snap to intersections.</span></span>  <br/> |
   

