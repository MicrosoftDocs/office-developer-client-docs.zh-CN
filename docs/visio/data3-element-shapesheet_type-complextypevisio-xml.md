---
title: 'Data3 元素 (ShapeSheet_Type COMPLEXType)  (Visio XML) '
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
# <a name="data3-element-shapesheet_type-complextype-visio-xml"></a><span data-ttu-id="6c5dc-103">Data3 元素 (ShapeSheet_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="6c5dc-103">Data3 element (ShapeSheet_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="6c5dc-104">包含用于提供有关形状的其他信息的任意字符串值。</span><span class="sxs-lookup"><span data-stu-id="6c5dc-104">Contains an arbitrary string value that is used to supply additional information about a shape.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6c5dc-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6c5dc-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6c5dc-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6c5dc-107">Data_Type</span><span class="sxs-lookup"><span data-stu-id="6c5dc-107">Data_Type</span></span>](data_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6c5dc-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6c5dc-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6c5dc-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6c5dc-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6c5dc-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6c5dc-112">page#.xml，master#.xml</span><span class="sxs-lookup"><span data-stu-id="6c5dc-112">page#.xml, master#.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6c5dc-113">定义</span><span class="sxs-lookup"><span data-stu-id="6c5dc-113">Definition</span></span>

```XML
< xs:element name="Data3" type="Data_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6c5dc-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6c5dc-114">Elements and attributes</span></span>

<span data-ttu-id="6c5dc-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6c5dc-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6c5dc-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6c5dc-116">Parent elements</span></span>

|<span data-ttu-id="6c5dc-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-117">**Element**</span></span>|<span data-ttu-id="6c5dc-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-118">**Type**</span></span>|<span data-ttu-id="6c5dc-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c5dc-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6c5dc-120">Shape</span><span class="sxs-lookup"><span data-stu-id="6c5dc-120">Shape</span></span>](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6c5dc-121">ShapeSheet_Type</span><span class="sxs-lookup"><span data-stu-id="6c5dc-121">ShapeSheet_Type</span></span>](shapesheet_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6c5dc-122">包含定义 **Master、Page** 或 **组合** 形状元素中形状的元素。</span><span class="sxs-lookup"><span data-stu-id="6c5dc-122">Contains elements that define a shape in a **Master**, **Page**, or group shape element.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6c5dc-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6c5dc-123">Child elements</span></span>

<span data-ttu-id="6c5dc-124">无。</span><span class="sxs-lookup"><span data-stu-id="6c5dc-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6c5dc-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="6c5dc-125">Attributes</span></span>

<span data-ttu-id="6c5dc-126">无。</span><span class="sxs-lookup"><span data-stu-id="6c5dc-126">None.</span></span>
  

