---
title: VisioDocument 元素 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5954685-3a2d-7848-388f-5dd7e536551c
description: Microsoft Visio 文档的根元素。
ms.openlocfilehash: 9829fa8960d78777e0fff4306b96978da90a647d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285311"
---
# <a name="visiodocument-element-visio-xml"></a><span data-ttu-id="bf26c-103">VisioDocument 元素 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="bf26c-103">VisioDocument element ('Visio XML')</span></span>

<span data-ttu-id="bf26c-104">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="bf26c-104">The root element of a Microsoft Visio document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="bf26c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="bf26c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bf26c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="bf26c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="bf26c-107">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-107">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="bf26c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="bf26c-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="bf26c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="bf26c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="bf26c-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="bf26c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="bf26c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="bf26c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="bf26c-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="bf26c-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="bf26c-113">定义</span><span class="sxs-lookup"><span data-stu-id="bf26c-113">Definition</span></span>

```XML
< xs:element name="VisioDocument" type="VisioDocument_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="bf26c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="bf26c-114">Elements and attributes</span></span>

<span data-ttu-id="bf26c-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="bf26c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="bf26c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="bf26c-116">Parent elements</span></span>

<span data-ttu-id="bf26c-117">无。</span><span class="sxs-lookup"><span data-stu-id="bf26c-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="bf26c-118">子元素</span><span class="sxs-lookup"><span data-stu-id="bf26c-118">Child elements</span></span>

|<span data-ttu-id="bf26c-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="bf26c-119">**Element**</span></span>|<span data-ttu-id="bf26c-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="bf26c-120">**Type**</span></span>|<span data-ttu-id="bf26c-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="bf26c-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bf26c-122">Colors</span><span class="sxs-lookup"><span data-stu-id="bf26c-122">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-123">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-123">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-124">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="bf26c-124">Contains the document's color table.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="bf26c-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="bf26c-127">Contains elements that specify document settings.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-128">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="bf26c-128">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-129">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-129">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-130">指定文档的**ShapeSheet**结构。</span><span class="sxs-lookup"><span data-stu-id="bf26c-130">Specifies a document's **ShapeSheet** structure.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-131">EventList</span><span class="sxs-lookup"><span data-stu-id="bf26c-131">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-132">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-132">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-133">包含对象应响应的每个事件的**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="bf26c-133">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-134">FaceNames</span><span class="sxs-lookup"><span data-stu-id="bf26c-134">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-135">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-135">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-136">包含**FaceName**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="bf26c-136">Contains a collection of **FaceName** elements.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-137">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="bf26c-137">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-138">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-138">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-139">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="bf26c-139">Contains elements for a document's header and footer.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-140">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="bf26c-140">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-141">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-141">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-142">指定可查看的一组绘图页, 以及在绘图中可刷新的一组记录集。</span><span class="sxs-lookup"><span data-stu-id="bf26c-142">Specifies the set of drawing pages that are viewable and set of recordsets that are refreshable in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="bf26c-143">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="bf26c-143">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="bf26c-144">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="bf26c-144">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="bf26c-145">包含文档的样式表元素的集合。</span><span class="sxs-lookup"><span data-stu-id="bf26c-145">Contains a collection of StyleSheet elements for the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="bf26c-146">Attributes</span><span class="sxs-lookup"><span data-stu-id="bf26c-146">Attributes</span></span>

<span data-ttu-id="bf26c-147">无。</span><span class="sxs-lookup"><span data-stu-id="bf26c-147">None.</span></span>
  

