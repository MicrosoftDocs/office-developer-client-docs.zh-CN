---
title: Shapes 元素 (ShapeSheet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 85aa7df3-d9bd-acb3-61b3-2bd5fa256435
description: 包含 Shape 元素的集合。
ms.openlocfilehash: e9f45d1f61b83339274d24aea2c0473adf282bac
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542098"
---
# <a name="shapes-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="af93a-103">Shapes 元素 (ShapeSheet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="af93a-103">Shapes element (ShapeSheet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="af93a-104">包含 Shape 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="af93a-104">Contains a collection of Shape elements.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="af93a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="af93a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="af93a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="af93a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="af93a-107">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="af93a-107">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="af93a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="af93a-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="af93a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="af93a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="af93a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="af93a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="af93a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="af93a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="af93a-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="af93a-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="af93a-113">定义</span><span class="sxs-lookup"><span data-stu-id="af93a-113">Definition</span></span>

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="af93a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="af93a-114">Elements and attributes</span></span>

<span data-ttu-id="af93a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="af93a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="af93a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="af93a-116">Parent elements</span></span>

|<span data-ttu-id="af93a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="af93a-117">**Element**</span></span>|<span data-ttu-id="af93a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="af93a-118">**Type**</span></span>|<span data-ttu-id="af93a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="af93a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="af93a-120">Shape</span><span class="sxs-lookup"><span data-stu-id="af93a-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="af93a-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="af93a-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="af93a-122">指定与形状关联的属性的集合。</span><span class="sxs-lookup"><span data-stu-id="af93a-122">Specifies a collection of properties associated with a shape.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="af93a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="af93a-123">Child elements</span></span>

|<span data-ttu-id="af93a-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="af93a-124">**Element**</span></span>|<span data-ttu-id="af93a-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="af93a-125">**Type**</span></span>|<span data-ttu-id="af93a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="af93a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="af93a-127">Shape</span><span class="sxs-lookup"><span data-stu-id="af93a-127">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="af93a-128">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="af93a-128">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="af93a-129">包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。</span><span class="sxs-lookup"><span data-stu-id="af93a-129">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="af93a-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="af93a-130">Attributes</span></span>

<span data-ttu-id="af93a-131">无。</span><span class="sxs-lookup"><span data-stu-id="af93a-131">None.</span></span>
  

