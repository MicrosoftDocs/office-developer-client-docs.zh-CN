---
title: VisioDocument 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5954685-3a2d-7848-388f-5dd7e536551c
description: Microsoft Visio 文档的根元素。
ms.openlocfilehash: 9829fa8960d78777e0fff4306b96978da90a647d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391302"
---
# <a name="visiodocument-element-visio-xml"></a><span data-ttu-id="93783-103">VisioDocument 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="93783-103">VisioDocument element ('Visio XML')</span></span>

<span data-ttu-id="93783-104">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="93783-104">The root element of a Microsoft Visio document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="93783-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="93783-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="93783-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="93783-106">**Element type**</span></span> <br/> |[<span data-ttu-id="93783-107">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="93783-107">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="93783-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="93783-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="93783-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="93783-109">**Schema file**</span></span> <br/> |<span data-ttu-id="93783-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="93783-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="93783-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="93783-111">**Document parts**</span></span> <br/> |<span data-ttu-id="93783-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="93783-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="93783-113">定义</span><span class="sxs-lookup"><span data-stu-id="93783-113">Definition</span></span>

```XML
< xs:element name="VisioDocument" type="VisioDocument_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="93783-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="93783-114">Elements and attributes</span></span>

<span data-ttu-id="93783-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="93783-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="93783-116">父元素</span><span class="sxs-lookup"><span data-stu-id="93783-116">Parent elements</span></span>

<span data-ttu-id="93783-117">无。</span><span class="sxs-lookup"><span data-stu-id="93783-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="93783-118">子元素</span><span class="sxs-lookup"><span data-stu-id="93783-118">Child elements</span></span>

|<span data-ttu-id="93783-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="93783-119">**Element**</span></span>|<span data-ttu-id="93783-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="93783-120">**Type**</span></span>|<span data-ttu-id="93783-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="93783-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="93783-122">颜色</span><span class="sxs-lookup"><span data-stu-id="93783-122">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-123">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="93783-123">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-124">包含文档颜色表。</span><span class="sxs-lookup"><span data-stu-id="93783-124">Contains the document's color table.</span></span>  <br/> |
|[<span data-ttu-id="93783-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="93783-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="93783-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="93783-127">Contains elements that specify document settings.</span></span>  <br/> |
|[<span data-ttu-id="93783-128">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="93783-128">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-129">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="93783-129">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-130">指定文档的**ShapeSheet**结构。</span><span class="sxs-lookup"><span data-stu-id="93783-130">Specifies a document's **ShapeSheet** structure.</span></span>  <br/> |
|[<span data-ttu-id="93783-131">EventList</span><span class="sxs-lookup"><span data-stu-id="93783-131">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-132">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="93783-132">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-133">包含与对象应响应每个事件**EventItem**元素。</span><span class="sxs-lookup"><span data-stu-id="93783-133">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
|[<span data-ttu-id="93783-134">FaceNames</span><span class="sxs-lookup"><span data-stu-id="93783-134">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-135">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="93783-135">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-136">包含**FaceName**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="93783-136">Contains a collection of **FaceName** elements.</span></span>  <br/> |
|[<span data-ttu-id="93783-137">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="93783-137">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-138">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="93783-138">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-139">包含文档的页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="93783-139">Contains elements for a document's header and footer.</span></span>  <br/> |
|[<span data-ttu-id="93783-140">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="93783-140">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-141">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="93783-141">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-142">指定一组的绘图页可查看和设置是可刷新绘图中的记录集。</span><span class="sxs-lookup"><span data-stu-id="93783-142">Specifies the set of drawing pages that are viewable and set of recordsets that are refreshable in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="93783-143">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="93783-143">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="93783-144">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="93783-144">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="93783-145">包含文档的样式表元素的集合。</span><span class="sxs-lookup"><span data-stu-id="93783-145">Contains a collection of StyleSheet elements for the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="93783-146">Attributes</span><span class="sxs-lookup"><span data-stu-id="93783-146">Attributes</span></span>

<span data-ttu-id="93783-147">无。</span><span class="sxs-lookup"><span data-stu-id="93783-147">None.</span></span>
  

