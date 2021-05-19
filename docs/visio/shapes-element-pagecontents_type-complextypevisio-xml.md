---
title: 'Shapes 元素 (PageContents_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f9d51d7-e2b7-bc68-dede-c79fb9dbcf60
description: 包含 Shape 元素的集合。
ms.openlocfilehash: 5d248dd2683a1ccc153d15477c888e1b13d24d0f
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542119"
---
# <a name="shapes-element-pagecontents_type-complextype-visio-xml"></a><span data-ttu-id="4ec5c-103">Shapes 元素 (PageContents_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="4ec5c-103">Shapes element (PageContents_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="4ec5c-104">包含 Shape 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4ec5c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4ec5c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4ec5c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4ec5c-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="4ec5c-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4ec5c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4ec5c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4ec5c-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="4ec5c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4ec5c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4ec5c-112">page#.xml，master#.xml</span><span class="sxs-lookup"><span data-stu-id="4ec5c-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4ec5c-113">定义</span><span class="sxs-lookup"><span data-stu-id="4ec5c-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4ec5c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4ec5c-114">Elements and attributes</span></span>

<span data-ttu-id="4ec5c-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4ec5c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4ec5c-116">Parent elements</span></span>

|<span data-ttu-id="4ec5c-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-117">**Element**</span></span>|<span data-ttu-id="4ec5c-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-118">**Type**</span></span>|<span data-ttu-id="4ec5c-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4ec5c-120">MasterContents</span><span class="sxs-lookup"><span data-stu-id="4ec5c-120">MasterContents</span></span>](mastercontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="4ec5c-121">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="4ec5c-121">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ec5c-122">指定有关 Web 绘图中主控形状中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-122">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
|[<span data-ttu-id="4ec5c-123">PageContents</span><span class="sxs-lookup"><span data-stu-id="4ec5c-123">PageContents</span></span>](pagecontents-elementvisio-xml.md) <br/> |[<span data-ttu-id="4ec5c-124">PageContents_Type</span><span class="sxs-lookup"><span data-stu-id="4ec5c-124">PageContents_Type</span></span>](pagecontents_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ec5c-125">指定有关 Web 绘图中主控形状中的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-125">Specifies information about the shapes in a master in a Web drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4ec5c-126">子元素</span><span class="sxs-lookup"><span data-stu-id="4ec5c-126">Child elements</span></span>

|<span data-ttu-id="4ec5c-127">**元素**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-127">**Element**</span></span>|<span data-ttu-id="4ec5c-128">**类型**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-128">**Type**</span></span>|<span data-ttu-id="4ec5c-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="4ec5c-129">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4ec5c-130">Shape</span><span class="sxs-lookup"><span data-stu-id="4ec5c-130">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4ec5c-131">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="4ec5c-131">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4ec5c-132">包含定义 **Master、Page** 或 **组合** 形状元素中形状的元素。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-132">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="4ec5c-133">Attributes</span><span class="sxs-lookup"><span data-stu-id="4ec5c-133">Attributes</span></span>

<span data-ttu-id="4ec5c-134">无。</span><span class="sxs-lookup"><span data-stu-id="4ec5c-134">None.</span></span>
  

