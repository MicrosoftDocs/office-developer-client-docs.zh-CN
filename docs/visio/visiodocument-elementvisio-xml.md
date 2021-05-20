---
title: 'VisioDocument 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f5954685-3a2d-7848-388f-5dd7e536551c
description: Microsoft 文档库Visio元素。
ms.openlocfilehash: acb0a4e8ef1efb6d6d5872118241e36bb4e9630c
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538485"
---
# <a name="visiodocument-element-visio-xml"></a><span data-ttu-id="772de-103">VisioDocument 元素 (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="772de-103">VisioDocument element (Visio XML)</span></span>

<span data-ttu-id="772de-104">Microsoft 文档库Visio元素。</span><span class="sxs-lookup"><span data-stu-id="772de-104">The root element of a Microsoft Visio document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="772de-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="772de-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="772de-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="772de-106">**Element type**</span></span> <br/> |[<span data-ttu-id="772de-107">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="772de-107">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="772de-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="772de-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="772de-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="772de-109">**Schema file**</span></span> <br/> |<span data-ttu-id="772de-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="772de-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="772de-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="772de-111">**Document parts**</span></span> <br/> |<span data-ttu-id="772de-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="772de-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="772de-113">定义</span><span class="sxs-lookup"><span data-stu-id="772de-113">Definition</span></span>

```XML
< xs:element name="VisioDocument" type="VisioDocument_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="772de-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="772de-114">Elements and attributes</span></span>

<span data-ttu-id="772de-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="772de-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="772de-116">父元素</span><span class="sxs-lookup"><span data-stu-id="772de-116">Parent elements</span></span>

<span data-ttu-id="772de-117">无。</span><span class="sxs-lookup"><span data-stu-id="772de-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="772de-118">子元素</span><span class="sxs-lookup"><span data-stu-id="772de-118">Child elements</span></span>

|<span data-ttu-id="772de-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="772de-119">**Element**</span></span>|<span data-ttu-id="772de-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="772de-120">**Type**</span></span>|<span data-ttu-id="772de-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="772de-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="772de-122">Colors</span><span class="sxs-lookup"><span data-stu-id="772de-122">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-123">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="772de-123">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-124">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="772de-124">Contains the document's color table.</span></span>  <br/> |
|[<span data-ttu-id="772de-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="772de-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="772de-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="772de-127">Contains elements that specify document settings.</span></span>  <br/> |
|[<span data-ttu-id="772de-128">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="772de-128">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-129">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="772de-129">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-130">指定文档的 **ShapeSheet** 结构。</span><span class="sxs-lookup"><span data-stu-id="772de-130">Specifies a document's **ShapeSheet** structure.</span></span>  <br/> |
|[<span data-ttu-id="772de-131">EventList</span><span class="sxs-lookup"><span data-stu-id="772de-131">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-132">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="772de-132">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-133">包含对象应响应的每个事件的 **EventItem** 元素。</span><span class="sxs-lookup"><span data-stu-id="772de-133">Contains an **EventItem** element for each event to which an object should respond.</span></span>  <br/> |
|[<span data-ttu-id="772de-134">FaceNames</span><span class="sxs-lookup"><span data-stu-id="772de-134">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-135">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="772de-135">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-136">包含 **FaceName 元素** 的集合。</span><span class="sxs-lookup"><span data-stu-id="772de-136">Contains a collection of **FaceName** elements.</span></span>  <br/> |
|[<span data-ttu-id="772de-137">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="772de-137">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-138">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="772de-138">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-139">包含文档页眉和页脚的元素。</span><span class="sxs-lookup"><span data-stu-id="772de-139">Contains elements for a document's header and footer.</span></span>  <br/> |
|[<span data-ttu-id="772de-140">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="772de-140">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-141">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="772de-141">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-142">指定可查看的绘图页集和在绘图中可刷新的记录集集。</span><span class="sxs-lookup"><span data-stu-id="772de-142">Specifies the set of drawing pages that are viewable and set of recordsets that are refreshable in a drawing.</span></span>  <br/> |
|[<span data-ttu-id="772de-143">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="772de-143">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="772de-144">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="772de-144">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="772de-145">包含文档的 StyleSheet 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="772de-145">Contains a collection of StyleSheet elements for the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="772de-146">Attributes</span><span class="sxs-lookup"><span data-stu-id="772de-146">Attributes</span></span>

<span data-ttu-id="772de-147">无。</span><span class="sxs-lookup"><span data-stu-id="772de-147">None.</span></span>
  

