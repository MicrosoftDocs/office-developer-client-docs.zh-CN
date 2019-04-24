---
title: Colors 元素 (VisioDocument_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3f439c2d-78be-5f2e-fa5a-f3feb83a0234
description: 包含文档的颜色表。
ms.openlocfilehash: bd46f58dfbb8a596717662b9a0524d59bb508270
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358756"
---
# <a name="colors-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="e6778-103">Colors 元素 (VisioDocument_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e6778-103">Colors element (VisioDocument_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="e6778-104">包含文档的颜色表。</span><span class="sxs-lookup"><span data-stu-id="e6778-104">Contains the document's color table.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e6778-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e6778-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e6778-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e6778-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e6778-107">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="e6778-107">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e6778-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e6778-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e6778-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e6778-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e6778-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e6778-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e6778-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e6778-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e6778-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="e6778-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e6778-113">定义</span><span class="sxs-lookup"><span data-stu-id="e6778-113">Definition</span></span>

```XML
< xs:element name="Colors" type="Colors_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e6778-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e6778-114">Elements and attributes</span></span>

<span data-ttu-id="e6778-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e6778-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e6778-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e6778-116">Parent elements</span></span>

|<span data-ttu-id="e6778-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e6778-117">**Element**</span></span>|<span data-ttu-id="e6778-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e6778-118">**Type**</span></span>|<span data-ttu-id="e6778-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6778-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e6778-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="e6778-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="e6778-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="e6778-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e6778-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="e6778-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e6778-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e6778-123">Child elements</span></span>

|<span data-ttu-id="e6778-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="e6778-124">**Element**</span></span>|<span data-ttu-id="e6778-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="e6778-125">**Type**</span></span>|<span data-ttu-id="e6778-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="e6778-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e6778-127">ColorEntry</span><span class="sxs-lookup"><span data-stu-id="e6778-127">ColorEntry</span></span>](colorentry-element-colors_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e6778-128">ColorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="e6778-128">ColorEntry_Type</span></span>](colorentry_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e6778-129">包含颜色表项。</span><span class="sxs-lookup"><span data-stu-id="e6778-129">Contains a color table entry.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="e6778-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="e6778-130">Attributes</span></span>

<span data-ttu-id="e6778-131">无。</span><span class="sxs-lookup"><span data-stu-id="e6778-131">None.</span></span>
  

