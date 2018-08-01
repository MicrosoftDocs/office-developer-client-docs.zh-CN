---
title: Data2 元素 （ShapeSheet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e823797e-dde9-6ee7-b5e4-9e57cef90b08
description: 包含用于提供有关形状的其他信息的任意字符串值。
ms.openlocfilehash: 9533f4b92cb73a6fc99ba82e2221eba40fb917b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780023"
---
# <a name="data2-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="b39e7-103">Data2 元素 （ShapeSheet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b39e7-103">Data2 element (ShapeSheet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="b39e7-104">包含用于提供有关形状的其他信息的任意字符串值。</span><span class="sxs-lookup"><span data-stu-id="b39e7-104">Contains an arbitrary string value that is used to supply additional information about a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="b39e7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="b39e7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b39e7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="b39e7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="b39e7-107">Data_Type</span><span class="sxs-lookup"><span data-stu-id="b39e7-107">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="b39e7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b39e7-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="b39e7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b39e7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="b39e7-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="b39e7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="b39e7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="b39e7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="b39e7-112">页面 #.xml、 母版页 #.xml</span><span class="sxs-lookup"><span data-stu-id="b39e7-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b39e7-113">定义</span><span class="sxs-lookup"><span data-stu-id="b39e7-113">Definition</span></span>

```XML
< xs:element name="Data2" type="Data_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="b39e7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b39e7-114">Elements and attributes</span></span>

<span data-ttu-id="b39e7-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b39e7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="b39e7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b39e7-116">Parent elements</span></span>

|<span data-ttu-id="b39e7-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="b39e7-117">**Element**</span></span>|<span data-ttu-id="b39e7-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="b39e7-118">**Type**</span></span>|<span data-ttu-id="b39e7-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="b39e7-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b39e7-120">Shape</span><span class="sxs-lookup"><span data-stu-id="b39e7-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b39e7-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="b39e7-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="b39e7-122">包含定义形状的**主控形状**、**页面**或组形状元素中的元素。</span><span class="sxs-lookup"><span data-stu-id="b39e7-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="b39e7-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b39e7-123">Child elements</span></span>

<span data-ttu-id="b39e7-124">无。</span><span class="sxs-lookup"><span data-stu-id="b39e7-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b39e7-125">属性</span><span class="sxs-lookup"><span data-stu-id="b39e7-125">Attributes</span></span>

<span data-ttu-id="b39e7-126">无。</span><span class="sxs-lookup"><span data-stu-id="b39e7-126">None.</span></span>
  

