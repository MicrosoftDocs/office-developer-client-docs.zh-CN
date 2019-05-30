---
title: Data3 元素 (ShapeSheet_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 63493467-af55-fa62-6c39-6b5896895952
description: 包含用于提供有关形状的其他信息的任意字符串值。
ms.openlocfilehash: 1ce286c0c8db53305f78def465ac31a3ef3afdec
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541251"
---
# <a name="data3-element-shapesheettype-complextype-visio-xml"></a><span data-ttu-id="f53d6-103">Data3 元素 (ShapeSheet_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f53d6-103">Data3 element (ShapeSheet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="f53d6-104">包含用于提供有关形状的其他信息的任意字符串值。</span><span class="sxs-lookup"><span data-stu-id="f53d6-104">Contains an arbitrary string value that is used to supply additional information about a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f53d6-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f53d6-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f53d6-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f53d6-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f53d6-107">Data_Type</span><span class="sxs-lookup"><span data-stu-id="f53d6-107">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f53d6-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f53d6-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f53d6-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f53d6-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f53d6-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="f53d6-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f53d6-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f53d6-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f53d6-112">页面 # .xml、master # .xml</span><span class="sxs-lookup"><span data-stu-id="f53d6-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f53d6-113">定义</span><span class="sxs-lookup"><span data-stu-id="f53d6-113">Definition</span></span>

```XML
< xs:element name="Data3" type="Data_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f53d6-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f53d6-114">Elements and attributes</span></span>

<span data-ttu-id="f53d6-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f53d6-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f53d6-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f53d6-116">Parent elements</span></span>

|<span data-ttu-id="f53d6-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f53d6-117">**Element**</span></span>|<span data-ttu-id="f53d6-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f53d6-118">**Type**</span></span>|<span data-ttu-id="f53d6-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f53d6-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f53d6-120">Shape</span><span class="sxs-lookup"><span data-stu-id="f53d6-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f53d6-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="f53d6-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f53d6-122">包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。</span><span class="sxs-lookup"><span data-stu-id="f53d6-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f53d6-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f53d6-123">Child elements</span></span>

<span data-ttu-id="f53d6-124">无。</span><span class="sxs-lookup"><span data-stu-id="f53d6-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f53d6-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="f53d6-125">Attributes</span></span>

<span data-ttu-id="f53d6-126">无。</span><span class="sxs-lookup"><span data-stu-id="f53d6-126">None.</span></span>
  

